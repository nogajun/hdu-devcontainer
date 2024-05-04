# Pythonプログラミング関連授業用Visual Stuidio Code開発環境設定ファイル

これは、Pythonプログラミング関連授業で使用する、Pythonプログラミング開発環境設定ファイルです。

LinuxやMacで展開しても何もないように見えますが、隠しフォルダーになっているVisual Studio Codeの
設定フォルダー `.vscode` とPython venv用の `.pyenv` があります。

linuxのコマンドで確認する場合は、 `ls -la` のように `ls` コマンドに `-a` オプションを付けて実行します。

## 使い方

1. Visual Studio Codeを起動する。
2. 左下歯車アイコンの設定から「プロファイル」→「プロファイルの作成」から新しいプロファイルを作成する。
3. [zipファイル](https://github.com/nogajun/hdu-devcontainer/archive/refs/heads/main.zip)をダウンロードして適当な場所に展開する。
4. VS Codeの「ファイル」→「ファイルでワークスペースを開く」を選び、展開したzipアーカイブ内の`programming.code-workspace`を開く。
5. 設定に沿って拡張機能がインストールされて設置完了。

## 最初のvenvインストール

1. VS Codeから「ターミナル」を開く。
2. `python -m venv .env/`を実行する。
3. `source .pyenv/bin/activate`を実行する。
4. pipを使って必要なファイルをインストールする
5. ターミナルを閉じる

## ファイル一覧

```text
├── .env
│   └── venvインストール用空フォルダ
├── .vscode
│   ├── argv.json ... ロケール
│   ├── extensions.json ... 拡張機能設定
│   ├── launch.json ... VS Codeデバッガー設定
│   └── settings.json ... VS Code設定
├── gitignore ... gitを使う場合のgitignore
├── programming.code-workspace ... VS Codeワークスペース設定
├── LICENSE
└── README.md
```

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/deed.ja)
