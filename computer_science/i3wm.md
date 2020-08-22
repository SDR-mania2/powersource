# 2020年2月時点のi3インストールメモ

CUIで起動できる状態とする。Xサーバの導入から。いきなりi3入れても動かない(多分フォントの問題で)。twmを入れてテストしてから入れる。

1.xorg-server/xorg-xinit入れる。

2.xf86-video-fbdev/dbus入れる。

3.xorg-twm/xterm/otf-ipafont入れる。

4.ここでtwmの起動テストをする。(startxの前に.xinitrc、.twmrcをコピーしないと起動できない)twmが起動できたらi3入れる。

5.i3/dmenu/rxvt-unicode入れる。

これでi3が起動できるはず。

6.ranger/feh/archlinux-wallpaper入れる。

7.ufw/firefox/scrot/htopなど入れる。

8.ALSAドライバ入れてconfig.txt追加。

あとはufwやDNS設定とか適当に。「/」は単なる区切り記号でディレクトリではありません。

フォントの問題というのは、コンソールフォントだとi3がうまく表示されないということ。適当なので推測だが。あと.twmrcは/usr/shareフォルダからコピーした。この情報は2月の話なので現在は変更があるかも。arch使いなら分かるでしょう。

i3wm+zramでラズパイは爆速になる。固まる回数は激減するはず。使うには知識がいるけど。

