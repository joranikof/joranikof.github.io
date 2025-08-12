# Node使い方

### 基本的な使い方

**1. JavaScriptファイルの実行**
```bash
node app.js
```
**2. 簡単なHTTPサーバーの例**
```javascript
const http = require('http');

const server = http.createServer((req, res) => {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello World!');
});

server.listen(3000, () => {
  console.log('Server running at http://localhost:3000/');
});
```

## npmコマンドの基本

npmはNode Package Managerの略で、JavaScriptのパッケージ管理ツールです。

### 主要なnpmコマンド

#### プロジェクトの初期化
```bash
npm init                # 対話形式でpackage.jsonを作成
npm init -y             # デフォルト設定でpackage.jsonを作成
```

#### パッケージのインストール
```bash
npm install express          # expressをインストール
npm install -g nodemon       # グローバルインストール（-g）
npm install --save-dev jest  # 開発環境用（devDependencies）
npm install                  # package.jsonの依存関係をすべてインストール
```

#### パッケージの削除
```bash
npm uninstall express        # パッケージを削除
```

#### スクリプトの実行
```bash
npm start                    # package.jsonのstartスクリプトを実行
npm test                     # testスクリプトを実行
npm run build                # 任意のスクリプトを実行
```

#### パッケージ情報の確認
```bash
npm list                     # インストール済みパッケージ一覧
npm outdated                 # 古いパッケージの確認
npm update                   # パッケージの更新
```

### package.jsonの重要性

package.jsonはプロジェクトの設定ファイルで、以下の情報を管理します：

- プロジェクトの基本情報
- 依存関係（dependencies）
- 開発環境用の依存関係（devDependencies）
- 実行可能なスクリプト

### 実践的な流れ

#### 1. 新しいプロジェクトを始める
```bash
mkdir my-project
cd my-project
npm init -y
```

#### 2. 必要なパッケージをインストール
```bash
npm install express
```

#### 3. 開発環境用ツールをインストール
```bash
npm install --save-dev nodemon
```

#### 4. package.jsonにスクリプトを追加
```json
{
  "scripts": {
    "start": "node app.js",
    "dev": "nodemon app.js"
  }
}
```

#### 5. アプリケーションを実行
```bash
npm run dev
```

## よく使用されるnpmオプション

| オプション | 説明 |
|-----------|------|
| `-g` | グローバルインストール |
| `--save` | dependenciesに追加（デフォルト） |
| `--save-dev` | devDependenciesに追加 |
| `-y` | 全ての質問にyesで回答 |
| `--production` | devDependenciesを除外してインストール |

## 便利なnpmコマンド

```bash
npm search <package-name>    # パッケージを検索
npm info <package-name>      # パッケージの詳細情報を表示
npm audit                    # セキュリティ脆弱性をチェック
npm audit fix               # 脆弱性を自動修正
npm cache clean --force     # npmキャッシュをクリア
```

これらの基本を押さえておけば、Node.jsでの開発を効率的に進めることができます。