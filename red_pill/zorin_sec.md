# なろうで公開するためのメモ

## Zorin OS 12.4Liteを入れてからの設定

### ブラウザにアドオンを追加する

- まずChromiumにAdblock→uMatrix入れる。

- 次にFirefoxにuBlock Origin→uMatrix入れる。

- さらにgufwをインストールしてオンにする。(インストール後メニューにアイコンが追加される)

広告ブロッカーの設定は一例です。他のアドオンでもかまいません。問題のある広告ブロッカーもあるので、調査してから入れるべきです。

### 画面輝度を調節する

画面輝度が明るすぎるので調整する。他にも設定や確認事項など。

- */sys/class/backlight/brightness* がない。仕方なくxrandrを使う。さくっと設定完了。

- *systemctl list-unit-files --type=service* や *service --status-all* などでsshやtelnetの停止を確認しておく。

- */var/log/ufw.log* は常にチェックする。journalctlも使う。一応aa-statusも確認しておく。(ただしauditは入ってない)

Linuxではログはたいてい */var/log/* にあります。初心者はここを見ましょう。ただし今後journalctlに移行していくと思われるので、使い方を知っておく必要があります。*aa-status* はAppArmorというセキュリティソフトのコマンドです。起動状態がenableか確認しておきましょう。

### VNCは暗号化されてない→パスワードが平文で流れる

Zorin OSとラズパイをVNC接続する場合の注意事項など。

- ラズパイとPCを接続→WAN側は遮断すること。VNC接続ではwiresharkでパスワードが丸見え。

- ssh-X使え→sshかますので問題なし。

### D-ShieldとwiresharkでLAN監視する。いずれsuricataへ移行したい

