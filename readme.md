# dockerでテスト環境作成プロジェクト

## Dockerアプリケーション導入
ホストOSがwindows環境を想定
WSL2のdocker desktopをダウンロードしインストール

## 基本概念

- 参考資料
https://www.youtube.com/watch?v=6kCZJLZBVpQ


## イメージ作成
### イメージ一覧確認
コマンドプロンプトを起動して以下を実行する
```
docker image ls
```
もしくは、docker desktopのイメージ一覧から確認する

### busyboxでunixコマンド実行
WindowsからとりあえずUnixコマンドを実行したい場合に便利なbusyboxを使ってみる

- ダウンロード
```
docker pull busybox
```

- 実行
```
docker run busybox echo "hello world"
docker run busybox sh

# ls
# echo hello world
# exit
```
上のダウンロードを行わなくても、イメージがローカルにない場合は勝手にダウンロードして実行してくれるみたい

### 使った後のお片付け
runした後にコンテナが残っているので、必要なければ削除を行う
```
docker ps -a
docker rm (container id)
```

### バックグラウンド実行
バックグラウンドで実行（コンテナのデーモン実行など）をするときは -d
起動ポートの指定は-P（ランダムポート）もしくは-Pに続いてポートを指定する
```
docker run -d -P --name static-site prakhar1989/static-site
```
上のものを実行すると、http://localhost:32769/ にテストページとしてアクセスできる。

### バックグラウンド実行
バックグラウンドで実行（コンテナのデーモン実行など）をするときは -d
起動ポートの指定は-P（ランダムポート）もしくは-Pに続いてポートを指定する
```
docker run -d -P --name static-site prakhar1989/static-site
```




- 参考資料
https://qiita.com/irico/items/4677334879da859a7c24
