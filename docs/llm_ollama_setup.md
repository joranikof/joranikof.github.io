# ollamaでローカルLLMをセットアップ

## 環境
- docker
- ubuntu 25.04

## ollamaをdockerで実行してみる

- https://zenn.dev/toki_mwc/articles/d1ebbd634ff488
- 手順

```bash
$ docker pull ollama/ollama

# GPUを使わない方のコマンドを実行
$ docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama

# モデルを選択(１つのモデルの中に色んなサイズがあるので、小さめのものを選択)
$ docker exec -it ollama ollama run deepseek-r1:1.5b

# 適当になにか喋ってみる
```

## webUIも繋げてみる
-  open-webuiと繋げてみる
  - 参考: https://docs.openwebui.com/
-https://qiita.com/RyutoYoda/items/ecdfbef8c73aae64aa45


## docker composeによる立ち上げ

### 1.composeファイルを作成

```
version: '3.8'

services:
  ollama:
    image: ollama/ollama:latest
    container_name: ollama-qwen
    ports:
      - "11434:11434"
    volumes:
      - ollama_data:/root/.ollama
    environment:
      - OLLAMA_HOST=0.0.0.0
    restart: unless-stopped
    # GPUがある場合は以下のコメントアウトを外す
    # deploy:
    #   resources:
    #     reservations:
    #       devices:
    #         - driver: nvidia
    #           count: 1
    #           capabilities: [gpu]
    command: serve

  # Web UIを使いたい場合（オプション）
  ollama-webui:
    image: ghcr.io/open-webui/open-webui:main
    container_name: ollama-webui
    ports:
      - "3000:8080"
    environment:
      - OLLAMA_BASE_URL=http://ollama:11434
    volumes:
      - ollama_webui_data:/app/backend/data
    depends_on:
      - ollama
    restart: unless-stopped

volumes:
  ollama_data:
  ollama_webui_data:
```

### 2.起動

```bash
$ docker-compose up -d
```

### 3.コンテナ内でモデルのダウンロードと起動

- モデルはハードウェアしだいで良さそうなものを探す

```bash
# コンテナ内でモデルをダウンロード
docker exec -it ollama-qwen ollama pull qwen2.5:14b-instruct-q4_k_m
```

### 4.アクセスしてみる

- Ollama API: http://localhost:11434
- Web UI（含まれている場合）: http://localhost:3000