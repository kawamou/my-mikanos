# my-mikanos
## my-mikanosとは
- 後で書く
## セットアップ
- 手順は[こちらの通り](https://zenn.dev/karaage0703/articles/1bdb8930182c6c)に実施
- Mac用の[.devcontainer](https://github.com/sarisia/mikanos-devcontainer)をclone
    - ちなみに[大元のDockerfile](https://github.com/sarisia/mikanos-docker)をこの階層に入れるのでもOK
- XQuartzをインストール`brew install xquartz`
    - XQuartzは画面表示のために必要
    - ゲスト環境であるDockerがXプロトコルで画面描画を求めてくるからキャッチして表示するためのXサーバーという認識
    - QEMUがXクライアントみたいになってるはず（...はず）
    - 以下、[引用](https://blog.goo.ne.jp/nhh0/e/a070a9b0edde6a52c1ace2b351ced261)だが分かりやすい
```foo.md
X Window Systemでは、クライアントサーバー方式でGUIが実現されていて、
1. 画面を描画するソフトウェア（Xサーバ。画面に絵を描く以外に、キーボードやマウスなどの入力デバイスの面倒も見る）
2. こんなの描画してね、と指示をするソフトウェア（Xクライアント。ようするにXのアプリケーション。xtermとかfirefoxとか全部そう）
```
- XQuarz立ち上げ > 設定 > セキュリティ > ネットワーククライアントからの接続を許可
- ターミナルでXQuarz立ち上げるたびに右記を実行`xhost + 127.0.0.1`
```foo.md
alice上で、「xhost +bob」と実行すると、bob上で実行したXクライアントがaliceのXサーバに接続できるようになります
```
- `code .`でVSCode起動
- `Remote - Containers`拡張を導入
- コマンドパレットで`Remote-Containers: Open Folder in Container...`
    - これで.evcontainer以下のDockerfileが勝手に読み込まれる
    - ※ 謎に数回立ち上げてこけてコンテナ & イメージ消すのを繰り返した。Dockerバージョンアップと再起動で入れるように
- Hello, World!

