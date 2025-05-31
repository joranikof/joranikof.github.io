# docsifyを使ったgithub　pageセットアップ

## 概要
- github pageを利用
- ページのスタイルはdocsifyを利用（index.htmlを配置するだけ）

## 参考サイト
- https://qiita.com/YoshikiIto/items/1c6ae1da119aec3dbc57
- https://docsify.js.org/#/quickstart?id=manual-initialization

## 手順概要
- github pageセットアップ
- docsifyのページでindex.htmlを取得 (!!npmでdocsify-cliは入れなくてよい!!)
    - https://docsify.js.org/#/quickstart?id=manual-initialization
- ファイルの準備
    - index.html    // docsifyのファイル
    - README.md     // HOMEになる。ファイル名は固定、内容自由
    - xxx.md        // 記事
    - .nojekyll     // github pageでjekyllを使わず、静的サイトにするもの
- localで表示確認
    - python(or python3) -m http.server 3000
    - 以下urlでページ確認
        ```
        http://localhost:3000/#             // home
        http://localhost:3000/#/test1       // test1.md
        http://localhost:3000/#/docs/test1  // docs/test2.md
        ```
- giihub pageにデプロイ

## docsifyページのカスタマイズ
