# Neovim インストール

## 経緯

- UbuntuのVSCodeでVimエクステンションを入れたところ、日本語変換後にreturnキーが効かない事象が発生。
- いろいろ試したが解決できないので、ホストにneovimをインストールし、neovimのエクステンション試してみることにした。

## 手順

- これに従い、インストール
  - https://github.com/neovim/neovim/blob/master/INSTALL.md#linux
  
- VSCode Neovim　エクステンションを追加
  - https://marketplace.visualstudio.com/items?itemName=asvetliakov.vscode-neovim

- VSCodeの設定で、Neovimのpathを追加
  - vscode-neovim.neovimExecutablePaths.linux

- 成功。
  - insert modeでの日本語変換も問題なく行えるようになった。

## 失敗した方法

- aptでneovimを入れると、vscodeのneovimエクステンションのエラーが発生したため、最新のneovimを入れることにした。
