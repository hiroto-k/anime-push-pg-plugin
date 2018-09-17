# anime-push-pg-plugin

anime-pushでPostgreSQLを扱うプラグイン。

## Install

``ap-dir``は``anime-push``をインストールしたディレクトリに読み替えて実行します。

最初にGitHubよりclone。ディレクトリ名は``ap-pg-plugin``を指定します。

```bash
cd [ap-dir]/plugin
git clone git@github.com:hiroto-k/anime-push-pg-plugin.git ap-pg-plugin
```

anime-pushをインストールしたディレクトリに戻り、``bundle install``を実行します。PostgreSQLを使う上で必要なgemがインストールされます。

```bash
cd [ap-dir]
bundle install
```

## Configure

``config.yml``の``db``フィールドに接続を追加し、指定します。

```yaml
env : postgresql

db :
  postgresql :
    adapter  : postgresql
    encoding : unicode
    host     : localhost
    username : username
    password : password
```

設定が完了したらデータベースの初期化を行います。

```bash
ruby app.rb migrate
```

## License

[MIT License](https://github.com/hiroto-k/anime-push-pg-plugin/blob/master/LICENSE "MIT License")
