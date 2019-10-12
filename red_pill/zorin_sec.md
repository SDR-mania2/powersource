# なろうで公開するためのメモ

## ZorinOS12.4Liteを入れてからの設定

### ブラウザにアドオンを追加する。

- まずchromiumにadblock→umatrix入れる。

- 次にfirefoxにublock origine→umatrix入れる。

- さらにgufwをオンにする。(インストール後メニューにアイコンが追加される)

### 画面輝度を調節する。

- /sys/class/backlight/brightnessがない。仕方なくxrandrを使う。さくっと設定完了。

- systemctl list-unit-files --type=service や service --status-allなどでsshやtelnetの停止を確認しておく。

- /var/log/ufw.logは常にチェックする。journalctlも使う。一応aa-statusも確認しておく。(ただしauditは入ってない)

### VNCは暗号化されてない→パスワードが平文で流れる。

- ラズパイと接続→LANは遮断すること。

- ssh-X使え→sshかますので問題なし。

### D-ShieldとwiresharkでLAN監視する。いずれsuricataへ移行したい。

