# Rust_使い方基本

## 便利ツール

- オンラインの実行環境
  - https://play.rust-lang.org/

## 基本操作

- ビルドと実行

  ```bash
  cargo new hello
  cd hello
  cargo run
  ```

- ビルドのみ

　```bash
  # 開発ビルド
  // バイナリは./target/debug/[ProjectName]として生成される。
  // デバッグ情報が得られるバイナリになっている。
　$ cargo build       

  # Releaseビルド
  // バイナリは./target/release/[ProjectName]として生成される。
  // 最適化が行われ、実行が早くなる
  $ cargo build --release
　```

- rustcについて
  - rustcがビルドを行うが、cargoを使っていれば単体のコマンドとして使うケースはなさそう

- その他のツールの利用
  
  ```
  $ cargo fmt       // 後で調べる
  $ cargp clippy    // 後で調べる
  ```

## projectの構造

```
./
├── Cargo.lock
├── Cargo.toml
├── src
│   └── main.rs
└── target
    ├── CACHEDIR.TAG
    └── debug
        ├── build
        ├── deps
        ├── examples
        ├── hello
        ├── hello.d
        └── incremental

```

## テスト

- コード内にテストを書く
　
```rust
#[test]
//テスト内容
```

- cargo --testでテスト実行


- 


## モジュールの使い方

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

- src/main.rs その1(moduleパスを書く)

```rust
mod module_1;

crate::module_1::func_a();  // func_a()を実行するには、モジュール情報を明示する
```

- src/main.rc その2（useを使ってmoduleパスを短縮化）

```rust
mod module_1;
use crate::module_1::func_a()        // 関数を指定

func_a();   // 前置き無しで実行
```

- src/main.rc その3（useを使ってmoduleパスを短縮化。複数の関数を対象にする）

```rust
mod module_1;
use crate::module_1::{func_a(), func_b()}     //複数の関数を指定

func_a();   // 前置き無しで実行
func_b();   // 前置き無しで実行
```



- モジュールの階層構造
  - わかりにくいので保留

- 