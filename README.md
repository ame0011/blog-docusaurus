# ウェブサイト

このWebサイトは [Docusaurus](https://docusaurus.io/) で作られています。

### インストール

```
$ pnpm install
```

### ローカルでの開発

```
$ pnpm start
```

このコマンドによりローカル開発サーバーが立ち上がりブラウザで開かれます。変更を行った際にサーバーの再起動は不要です。

### ビルド

```
$ pnpm build
```

このコマンドにより静的コンテンツが `build` ディレクトリに生成され、静的コンテンツホスティングサービスに展開できます。

### デプロイ

SSHを使用する場合:

```
$ USE_SSH=true pnpm deploy
```

SSHを使用しない場合:

```
$ GIT_USER=<Your GitHub username> pnpm deploy
```

GitHub pagesをホスティングに利用するならこのコマンドで簡単に `gh-pages` ブランチにプッシュできます。
