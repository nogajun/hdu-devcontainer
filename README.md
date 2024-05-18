# Webアプリ開発 開発環境設定ファイル

これは、Webアプリ開発の授業で使用する[Flask](https://flask.palletsprojects.com/)開発環境用設定ファイルです。LinuxやMacでは展開しても何もないように見えますが、Visual Studio Codeのの設定フォルダー `.devcontainer` 、 `.vscode` 、Python venv用設定フォルダー `.env` があります。

linuxのコマンドで確認する場合は、 `ls -la` のようにlsコマンドにaオプションを付けて実行します。

## 使い方

1. [Docker](https://www.docker.com/)、または[Docker Desktop](https://www.docker.com/products/docker-desktop/)をインストールする
    - [Install Docker Engine on Debian | Docker Documentation](https://docs.docker.com/engine/install/debian/)
    - [Install Docker Engine on Ubuntu | Docker Documentation](https://docs.docker.com/engine/install/ubuntu/)
2. [Visual Studio Code](https://code.visualstudio.com/)をインストールして、[Remote development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)拡張機能をインストールする
3. Visual Studio Codeから、このリポジトリのzipファイルを展開またはクローンしたフォルダーを開く
4. Dockerがビルドされて、開発環境が設定される

## ファイル一覧

```text
├── .devcontainer
│   ├── Dockerfile ... 開発環境 Dockerfile
│   ├── devcontainer.json ... 開発環境 DevContainer設定
│   └── pip
├── .env ... venv環境インストールフォルダー
│   └── .gitkeep
├── .vscode
│   ├── argv.json
│   ├── extensions.json ... VS Code拡張機能設定
│   ├── launch.json ... VS Codeデバッガーの設定
│   └── settings.json ... VS codeローカル設定
├── LICENSE
├── README.md
├── gitignore ... 開発環境用 .gitignoreファイル
├── programming.code-workspace ... VS Codeワークスペース設定
└── src ... ファイル保存用フォルダー
    └── .gitkeep
```

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.ja)
