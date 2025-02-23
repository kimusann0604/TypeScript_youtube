License
The source code is licensed MIT.

1.環境構築
1-1. Node環境の確認とインストール
Homebrewのバージョンを確認
brew --version
インストールされていなければ実行
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
nodebrewのインストール
brew install nodebrew
nodeの安定バージョンをインストール
nodebrew install stable
nodebrewのバージョン一覧を確認
nodebrew ls
インストールしたバージョンを指定して切り替える
nodebrew use v14.15.3
nodeのパスを通す
echo 'export PATH=$HOME/.nodebrew/current/bin:$PATH' >> ~/.zprofile'
ターミナルの再起動
nodeとnpmのバージョン確認
node -v
npm -v
1-2. TypeScript環境構築
開発用ディレクトリの作成
mkdir ~/<YOUR_DEV_DIR>/ts-basic
npmの初期化
npm init
関連パッケージのインストール(※)
npm install --save-dev typescript ts-loader webpack webpack-cli webpack-dev-server
webpack.config.jsの作成と設定
tsconfig.jsonの作成と設定
tsc --init
※ 実行時にgyp: No Xcode or CLT version detected!のエラーが出たら
Mac OSに入っているXCodeのバージョンと、コマンドラインツールのバージョンが合っていないという理由で怒られています。
以下手順でコマンドラインツールのバージョンをアップデートしましょう。

sudo付きのコマンドはMac OSのパスワード入力が必要です。 4.を実行すると、コマンドラインツールをインストールするか聞かれるので、同意して進めてください。

sudo rm -rf $(xcode-select -print-path)
sudo rm -rf /Library/Developer/CommandLineTools
sudo xcode-select --reset
xcode-select --install
xcode-select -p
5.の実行結果が/Library/Developer/CommandLineToolsでなければsudo xcode-select -switch /Library/Developer/CommandLineToolsを実行
インストールが完了したら、「3.関連パッケージのインストール」のコマンドを再実行してください。
