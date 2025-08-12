# Docker のセットアップ

## 参考URL

## install手順

- ここの既存のスクリプトを実行
  - https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script

- 実行できることを試す
  - sudo docker run hello-world

## rootless設定

- ここの手順に従う
https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user

- rootlessで実行できることを試す
  - docker run hello-world