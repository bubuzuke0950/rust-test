# Rust のインストール

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

```
. $HOME/.cargo/env
```

バージョンが表示されたら OK

```
＄　cargo --version
cargo 1.78.0 (54d8815d0 2024-03-26)
＄　rustc --version
rustc 1.78.0 (9b00956e5 2024-04-29)
```

# cargo の使い方

## プロジェクト作成

```
cargo new プロジェクト名
```

こうなるはず
ソースコードはsrc/に
パッケージの管理はCargo.toml

```
$ cd project1/
$ tree
.
├── Cargo.toml
└── src
    └── main.rs

2 directories, 2 files
```

## ビルド

target/debug に実行ファイルが作成される。

```
cargo build
```

## run

プロジェクトのビルドと実行を１ステップでできる

```
cargo run
```

## チェック

コードがコンパイルできるか素早くチェックする。実行ファイルは生成しない。

```
cargo check
```

## リリース向けビルド

リリース向けに最適化された状態でコンパイルできる。コンパイルにかかる時間は長くなる。
target/release に実行ファイルが作成される。

```
cargo build --release
```

#　便利な開発ツール

## rustfmt

コードをフォーマットしてくれる。

### インストール方法

```
rustup component add rustfmt
```

### 使い方

```
cargo fmt
```

## cargo doc

すべての依存クレートが提供するドキュメントをローカルでビルドできる。

```
cargo doc --open
```

target/doc/プロジェクト名/index.html にできる
