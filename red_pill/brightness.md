# zorin12.4での画面輝度設定方法。

***ターミナルでxrandrを実行してconnectedなディスプレイ名を探す。***

***LVDS-1 connected 1024x768+0+0*** のような表示をさがす。 LVDSではなくEDPなどとなっているかもしれません。

***xrandr --output LVDS-1 --brightness 0.5*** のように実行すれば調整可能。

0から1.0の幅で調整可能らしい。以上。

# ついでにsshとtelnetの停止方法

SSHやtelnetは外部からLnuxに接続するためのプロトコルです。Windows10でもSSHが使えるらしいので、分からない方は調べてください。サーバーとして外部に公開する場合を除いて、セキュリティ上侵入経路になるため、サービスを停止するのが鉄則です。SSHに限らず不要なサービスを止めることはLinux使いへの第一歩です。

## systemctlの使い方

*systemctl list-unit-files --type=service*

でサービス一覧見れる。

*systemctl status ssh*

で状態表示する。

*systemctl stop ssh*

で停止する。

*systemctl disable ssh*

で自動起動の無効化。これだけでは停止しない。stopが必要らしい。xenialではserviceコマンドもまだ使えるようだ。 */var/log/* 以下にログを配置しているのはsyslogdというサービスです。syslogdは今後systemdへと移行していく予定で、systemdではログはjournalctlコマンドで表示されます。また再起動ごとにログは消去されて残りません。systemctlはsystemdのコマンドなので、systemd移行後も使えます。Ubuntuなど多くのディストリビューションでは、現在syslogdもsystemdも併用している状態です。



