# Tauriセットアップ

## 手順

### 1. prerequisitionのインストール

- https://v2.tauri.app/start/prerequisites/#linux


### 2. プロジェクトの作成
 
- https://v2.tauri.app/start/prerequisites/#linux

  ```
  #プロジェクト作成
  $ npm create tauri-app@latest my-app
  
  # (もしくは以下でもプロジェクト作成できる。)
  #$ sh <(curl https://create.tauri.app/sh)
  
  # プロジェクトディクトリに移動
  $ cd my-app
  
  # nodeパッケージをインストール
  $ npm install
  
  # デスクトップアプリを実行
  $ npm run tauri dev
  ```

### Tips

- npmとnpxの違い、npm createについて
  - npmはパッケージをダウンロードするのに対し、npxはそのまま実行する
  - npm create tauri-app は、npx create-tauri-appのエイリアス


## プロジェクトの構造

```bash
.
├── node_modules
│   ├── typescript
│   ├── vite
│   ├── vitefu
|   :
|   :
│   └── zimmerframe
├── package.json
├── package-lock.json
├── README.md
├── src
│   ├── app.html
│   └── routes
│       ├── +layout.ts
│       └── +page.svelte
├── src-tauri
│   ├── build.rs
│   ├── capabilities
│   ├── Cargo.toml
│   ├── icons
│   ├── src
│   └── tauri.conf.json
├── static
├── svelte.config.js
├── tsconfig.json
└── vite.config.js
```

## サンプル機能
