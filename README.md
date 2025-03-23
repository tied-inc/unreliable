# unreliable
Unreliable – Because Most AI News Isn't.

## Zenn 記事執筆環境について

このリポジトリには、[Zenn CLI](https://zenn.dev/zenn/articles/zenn-cli-guide)を使用して記事を執筆するための開発環境が含まれています。VS Code の開発コンテナ機能を使用することで、簡単に一貫した環境で記事を書くことができます。

## 開発環境の機能

- Node.js 22 環境
- Zenn CLI のインストール済み
- マークダウン編集に便利な VS Code 拡張機能
- ポート 8000 の自動転送（プレビュー用）

## 開発コンテナの使い方

### 前提条件

- [Visual Studio Code](https://code.visualstudio.com/) がインストールされていること
- [Remote - Containers 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) がインストールされていること
- [Docker](https://www.docker.com/) がインストールされていること

### 開発コンテナの起動方法

1. VS Code でこのプロジェクトを開きます
2. 以下のいずれかの方法で開発コンテナを起動します：
   - コマンドパレット（`F1`キー）を開き、「Remote-Containers: Reopen in Container」を選択
   - 左下の緑色のアイコンをクリックし、「Reopen in Container」を選択
   - VS Code の下部ステータスバーの「><」アイコンをクリックし、「Reopen in Container」を選択
3. コンテナのビルドと起動が完了するまで待機します（初回は数分かかることがあります）

### 開発コンテナ内での作業

コンテナが起動すると、VS Code のウィンドウがコンテナ内の環境に接続されます。この環境では：

- Node.js 22 と npm が利用可能
- Zenn CLI がグローバルにインストール済み
- マークダウン編集用の拡張機能が有効化済み
- プロジェクトのファイルはコンテナ内にマウントされ、変更はホストマシンと同期

## Zenn 記事の作成と編集

```bash
# 新しい記事を作成
npx zenn new:article

# 新しい本を作成
npx zenn new:book

# プレビューを開始
npx zenn preview
```

または、package.json に定義されたスクリプトを使用：

```bash
# プレビューを開始
npm start

# 新しい記事を作成
npm run new:article

# 新しい本を作成
npm run new:book
```

プレビューは http://localhost:8000 で確認できます。

## 記事の公開

記事の編集が完了したら、通常の Git ワークフローでコミットしてプッシュしてください。
Zenn と連携されている GitHub リポジトリにプッシュすると、自動的に記事が公開されます。

## 開発コンテナの終了

VS Code を閉じるか、コマンドパレットから「Remote-Containers: Reopen Locally」を選択すると、コンテナから切断されます。
コンテナは停止しますが、削除されません。次回 VS Code で開く際に再利用できます。

## 開発環境のカスタマイズ

- `.devcontainer/devcontainer.json`: VS Code の設定や拡張機能を変更できます
- `.devcontainer/Dockerfile`: コンテナの環境をカスタマイズできます

## 参考リンク

- [Zenn CLIで記事・本を管理する方法](https://zenn.dev/zenn/articles/zenn-cli-guide)
- [Zenn のMarkdown記法](https://zenn.dev/zenn/articles/markdown-guide)
- [VS Code Remote Containers の詳細](https://code.visualstudio.com/docs/remote/containers)
