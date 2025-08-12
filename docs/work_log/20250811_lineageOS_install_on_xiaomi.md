# LineageOSをXaiomiにインストール

## 環境

- Xiaomi Redmi Note 9S
  - RAM 4.0+1.0GB
  - CPU オクタコア最大 2.32GHz
  - Androidバージョン 12 SKQ1.211019.001
  - Android セキュリティアップデート 2023-05-01
  - モデル M2003J6A1R
  - MIUIバージョン
    - MIUI Global
    - 14.0.4安定版
    - 14.0.4.0(SJWMIXM)
  - ベースバンド バージョン MPSS.AT.4.4.c6-00071-RENNELL_GEN_PACK-3
  - カーネル バージョン 4.14.190-perf-gd04947a26e35
- Ubuntu

## 手順

- 以下に従って作業
  - LineageOS デバイス別インストラクション　Xiaomi Redmi Note 9S
    - https://wiki.lineageos.org/devices/miatoll/variant2/

- adbインストール
  - 参考URL:　https://wiki.lineageos.org/adb_fastboot_guide#on-linux
  - 以下を実行したら、すでにインストール済みだった

  ```bash
  sudo apt install android-tools-adb android-tools-fastboot
  ```

- model numberの確認
  - 記載のものと適合しているか確認

- Xiaomi's websiteにてMi account作成とアンロック