# Webアプリ開発 開発環境設定ファイル

これはWebアプリ開発の授業で使用する[Flask](https://flask.palletsprojects.com/)開発環境用設定ファイルです。LinuxやMacでは展開しても何も無いように見えますが、隠しフォルダになっているVisual Studio CodeのRemote developmentの設定フォルダ`.devcontainer`と`.vscode`があります。

linuxのコマンドで確認する場合は、`ls -la`のようにlsコマンドにaオプションを付けて実行します。

## 使い方

1. [Docker](https://www.docker.com/)、または[Docker Desktop](https://www.docker.com/products/docker-desktop/)をインストールする
    * [Install Docker Engine on Debian | Docker Documentation](https://docs.docker.com/engine/install/debian/)
    * [Install Docker Engine on Ubuntu | Docker Documentation](https://docs.docker.com/engine/install/ubuntu/)
2. [Visual Studio Code](https://code.visualstudio.com/)をインストールして、[Remote development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)拡張機能をインストールする
3. Visual Studio Codeから、このリポジトリのzipファイルを展開、またはクローンしたフォルダを開く
4. Dockerがビルドされて、開発環境が設定される

## ファイル一覧

```
├── .devcontainer
│   ├── Dockerfile ... 開発環境Dockerfile 
│   └── devcontainer.json ... Dev containerの設定
├── .vscode
│   └── launch.json ... VS codeデバッガーの設定
├── LICENSE
└── README.md
```

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.ja)
