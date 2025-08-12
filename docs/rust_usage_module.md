# Rust モジュール使い方

## 概要

- モジュール名と分割ファイル名の関係
  - モジュール名 = 分割ファイル名になる
  - #[path]を使えば変えることも可能）

- モジュール内の関数の呼び出し
  - mod [モジュール名];               // 宣言
  - crate::[モジュール名]::[関数名];　　// 呼び出し

- 呼び出し時のモジュールパスの省略
  - mod [モジュール名];                 // 宣言
  - use crate::[モジュール名]::[関数名]; // useによるパス省略
  - [関数名];　　                       // 関数名のみで呼び出し

- モジュールの階層構造
  - わかりにくいので保留

## モジュール利用例

- src/module_1.rs

```rust
pub fn func_a()
{
  println!("hello world");
}

pub fn func_b()
{
  println!("hello world");
}
```

- src/main.rc

```rust
mod module_1;
use crate::module_1::func_a;        // これにより、コード内でmoduleパスを省略可

fn main() {
    // crate::module_1::func_a();   // useを使わない場合はmoduleパスを明示
    func_a();
}
```

## crate.ioからのクレート利用

- Cargo.tomlに以下のように書く。勝手にDLしてbuildしてくれる

```toml
[クレート名]="バージョン"
```

- 呼び出し時、modは不要


