# zorin12.4での画面輝度設定方法。

*** ターミナルでxrandrを実行してconnectedなディスプレイ名を探す。 ***

*** xrandr --output LVDS-1 --brightness 0.5 のように実行すれば調整可能。 ***

0から1.0の幅で調整可能らしい。以上。

# ついでにsshとtelnetの停止方法

## systemctlの使い方

systemctl list-unit-files --type=service

でサービス一覧見れる。

systemctl status ssh

で状態表示する。

systemctl stop sshも

で停止する。

systemctl disable ssh

で自動起動の無効化。これだけでは停止しない。stopが必要らしい。xenialではserviceコマンドもまだ使えるようだ。syslogも見れる。




