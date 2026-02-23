# atcoder用のrustプロジェクトの使い方

## 概要

- atcoderの場合、単体のコードファイルのビルドと実行が必要
- が、cargo runするとmain.rsが実行されてしまう

## 単体ファイルを実行する方法

- cargoに含まれているbinの機能を利用する

```bash
# プロジェクトを作成
cargo new test_prj

# binディクトリの作成
cd test_prj/src
mkdir bin

# 単体のコードファイルを作成
vim ./bin/tantai.rc

# buildと実行   ★　".rs"は不要
cargo run --bin tantai
```
