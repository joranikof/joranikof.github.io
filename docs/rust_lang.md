# Rust_文法

## study sources

れんしゅう


aaaaa


れんしゅうああaaaaaaaaaaafvoijefewefijasdfdsf
sdfwefsdsdfあaaaあ
https://rustlings.rust-lang.org/

## 不明点
- mutなしの場合との違いは？
- コンパイル過程のC言語見れないの？
  - これは見れなかった。cargo rustc -- --emit=llvm-ir

## 変数
- 宣言の仕方
  - let x           // 変更不可（immutalbe）
  - let mut x      // 変更可（mutable）
  - const x         // 変更不可

## コンパイル
- data型
  - 静的な型付け言語　→　コンパイル時に型が確定済み。
  - 型推論してくれるため、明示しなくて大体よろしくやってくれる
  - 型推論の確認方法
    - rust-analyzer（VScodeプラグイン）が表示してくれる

##