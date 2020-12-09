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

で自動起動の無効化。これだけでは停止しない。*stop*が必要らしい。xenialでは*service*コマンドもまだ使えるようだ。

*/var/log/* 以下にログを配置しているのは*syslogd*というサービスです。最近のLinuxでは、今まで主流だった*init*という起動システムが*systemd*に移行しつつあります。これに伴ない*syslogd*は今後*systemd*へと移行していく予定です。この*systemd*(より詳しく言うと*systemd-journald*)ではログは*journalctl*コマンドで表示されます。また再起動ごとにログは消去されて残りません。*systemctl*は*systemd*のコマンドなので、*systemd*移行後も使えます。Ubuntuなど多くのディストリビューションでは、現在*syslogd*も*systemd*も併用している状態です。

# BIOS(UEFI)について

Intel-SA-00086やCSME問題など最近はファームウェアの脆弱性も多いので、BIOS(UEFI)もアップデートした方がいいです。UbuntuやArchでも可能ですが、失敗するリスクを考えるとWindowsからした方が安全です。ルータで防げるという意見もあるだろうし、どこまでやるかは価値観の問題になります。しかし最低限、Intel AMTのパスワードは変更しておくべきです。分からなければ、「Intel AMT　パスワード」で検索すればいろいろとヒットします。AMDにもPSPというシステムがあるので、AMDなら大丈夫とは断言できません。
