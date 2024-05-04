# Web アプリ開発 Visual Stuidio Code 開発環境設定ファイル

これはWebアプリ開発の授業で使用する[Flask](https://flask.palletsprojects.com/)開発環境用設定ファイルです。
LinuxやMacで展開しても何もないように見えますが、隠しフォルダーになっているVisual Studio Codeの設定フォルダー `.vscode` と
Python venv用の `.pyenv` があります。

linuxのコマンドで確認する場合は、 `ls -la` のように `ls` コマンドに `-a` オプションを付けて実行します。

## 使い方

1. [zip ファイル](https://github.com/nogajun/hdu-devcontainer/archive/refs/heads/main.zip)をダウンロードして適当な場所に展開します。
2. Visual Studio Codeを起動して、左下歯車アイコンの設定から新しいプロファイルを作成します。
3. VS Codeの「ファイル」→「ファイルでワークスペースを開く」を選び、展開したzipアーカイブ内の`webdev.code-workspace`を開きます。
4. ポップアップにしたがって拡張機能をインストールします。

### Flask のインストール

1. VS Codeから「ターミナル」を開いて`python -m venv .pyenv/`を実行する。
2. `source .pyenv/bin/activate`を実行する。
3. `pip install flask`を実行する。
4. ターミナルを閉じる

## ファイル一覧

```text
├── .pyenv
│   └── venvインストール用空フォルダ
├── .vscode
│   ├── argv.json ... ロケール
│   ├── extensions.json ... 拡張機能設定
│   ├── launch.json ... VS Codeデバッガー設定
│   └── settings.json ... VS Code設定
├── webdev.code-workspace ... VS Codeワークスペース設定
├── LICENSE
└── README.md
```

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.ja)
