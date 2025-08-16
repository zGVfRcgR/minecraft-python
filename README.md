# minecraft-python

Docker Compose を使って、Minecraft サーバーと JupyterLab を連携させ、Python から Minecraft の世界を操作できる環境を構築します。教育展示やプログラミング学習に最適です。

---

## システム構成

- **Minecraft サーバー**：Spigot + RaspberryJuice プラグイン
- **JupyterLab**：Python ノートブックで Minecraft を操作
- **Docker Compose**：サービスの一括起動・管理
- **mcpi**：Python から Minecraft を制御するライブラリ

---

## フォルダ構成

```
minecraft-python/
├── .devcontainer/
│   ├── docker-compose.yml     # JupyterLab と Minecraft サーバーを同時に起動するための構成ファイル
│   ├── Dockerfile             # JupyterLab 用の Python 環境を構築する Dockerfile（mcpi などをインストール）
│   └── requirements.txt       # JupyterLab コンテナで使用する Python ライブラリの一覧（mcpi, numpy など）
├── minecraft/
│   └── data/                  # Minecraft サーバーのワールドデータや設定ファイルを格納
│       └── plugins/           # RaspberryJuice.jar を配置するディレクトリ（Python 連携用）
├── notebooks/
│   └── demo.ipynb             # Python から Minecraft を操作するサンプルノートブック
├── README.md                  # プロジェクトの概要・使い方・構成を記載したドキュメント
```

## 🚀 利用方法

> このプロジェクトは **GitHub Codespaces** 上での利用を前提としています。

### 1. 起動方法

1. GitHub Codespaces を起動する
2. 以下のコマンドで Docker Compose を実行：

```bash
docker-compose -f .devcontainer/docker-compose.yml up -d
```

3. 	JupyterLab に Web ブラウザから接続する：

```bash
docker logs jupyterlab
```

ログに表示される URL（例：http://127.0.0.1:8888/lab?token=...）をコピーしてブラウザで開きます。


  ```log
  [I 2025-08-16 13:07:39.192 ServerApp] Jupyter Server 2.8.0 is running at:
  [I 2025-08-16 13:07:39.192 ServerApp] http://b698d43222bd:8888/lab?token=aac33483baee2a0f6d763fd7056abb884fcc82576991406c
  [I 2025-08-16 13:07:39.192 ServerApp]     http://127.0.0.1:8888/lab?token=aac33483baee2a0f6d763fd7056abb884fcc82576991406c
  ```

### 2. 接続確認

JupyterLab に Web ブラウザから接続できたら、JupyterLabからMinecraft サーバーに接続できるか確認する。

1. JupyterLabのWeb画面のnotebooksにある"check_mc_connection.jpynb"を実行する。
2. ✅ 接続成功！と表示されていればいい。

