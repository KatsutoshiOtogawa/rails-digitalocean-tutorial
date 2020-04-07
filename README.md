# rails-digitalocean-tutorial
digitaloceanのチュートリアルです。

rails自体のユーザーがすでに作成してあり、
railsもサービスとして登録されている。
そのため、

railsは

```
$ systemctl start rails
```

と実行するとアプリケーションをスタートすることができる。

railsアプリケーションのインストール先
/home/rails/example
exampleプロジェクトという名称で入っているので、
exampleをrootユーザーで
```
# cp -a example example.org
```

exampleをコピーして控えをとり、
少人数ならexampleプロジェクトを直接
変更していく方法でもよい。
visual studio codeまたはcloud9でssh経由でプロジェクト開いて,,,

プロジェクが完成したら、
exampleプロジェクトをrenmae

railsユーザーに変更するときは
rootユーザー時に
```
# sudo -i -u rails
```

と実行するタイポではない。
rails,postgresのパスワード

/root/.digitalocean.passwords

Get Startedのところに  
「ufwを使って22,80,443以外のポートは必ず閉じておくこと!!!」  
と書かれているが、すでにufwを使って上記以外のポートは閉じられている。
めっちゃ親切。

20200407現在digitaloceanでrailsの
dropletをインストールすると、
rails6.0以上がインストールされます。

add the following to your environment configuration:
というエラーが表示されると思うので、

vi /home/rails/example/config/application.rb
として、
class Application < Rails::Applicationの中に
下記の設定を追加してください。

```
# example.comは適当なFQDNに変更してください。
config.hosts << "example.com"
```

## Refference
[railsのエラーについて](https://qiita.com/taiteam/items/a37c60fc15c1aa5bb606)
[railsプロジェクトのrenmae方法](https://qiita.com/ryoya-s/items/66e426f1a0dd5d87cd6f)
