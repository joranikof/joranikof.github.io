# Rust_環境セットアップ

## 概要$ 
- gccとビルドツールのインストール
- Wio Terminal用の開発環境は、下記作業完了後に、別資料を参考に構築する
    - 参照：[Wio Terminalの環境構築](/docs/wio-terminal_setup.md)

## 参考サイト
- 基礎から学ぶ組み込みRust

## 手順
```
# gccインストール
sudo apt install gcc

# Rustツールチェインのインストール/バージョン管理　https://rustup.rs/
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Wio Terminal用のクロスビルドツールチェイン
rustup target add thumbv7em-none-eabihf

# 確認
rustup --version
rustc --version
carge --version

# コンパイル/実行してみる
cargo new hello
cd ello
cargo run

# VScodeのプラグインインストール
rust-analyzer
```

## VScodeの設定

### Plugins

- rust-analyzer (language Server)

- CodeLLDB (debugger)