# aeroboy.github.io
## 2015 1/22
### git でプロジェクト（ヴァージョン）管理
* git init あるいは git clone https://github.com/ユーザー名/プロジェクト名
* ローカル編集
* git add ファイル名
* git commit -m "コメント"
* git push originあるいはhttps//github.com/ユーザー名/プロジェクト名


### USBメモリーにDebian7.8をインストール  
  * DebianでUSBメモリーの中を２つのパーティションに分ける  
  * 頭にスワップパーティションをおいたら、GRUBをそのパーティションにインストールできない  
  * USBメモリーをPCのUSBに挿して、DVD-1 を起動  
  * インストール(/dev/sdb1)  
  * GRUBは/deb/sdbにインストール  
  
### ディユアルブートでWin7をデフォルトに   
* HDD(/dev/sda)のパーティションを 4つに分ける  
    1 swap     (4GB)  
    2 ext4  /  (10GB)  
    3 ext4  /home  (残り)  
    4 NTFS  Win7  
* HDD1,2にDebianインストール
* GRUBは /dev/sda にインストール
* 次にWin7を HDD4 にインストール
* ブートブロックがWinによって上書きされ、GRUBが起動しない
* DVD-1 から起動し、Advanced ---> Rescue boot ---> GRUB 再インストール(on /dev/sda)
* /dev/sda のGRUB起動。この時点でWindowsを認識できない。
* Debian 起動
* cd /etc/grub.d/
* # update-grub  ---> Win7がGRUBに加えられる
* /etc/grub.d 内でファルの番号順に起動される。30_os-proberがWin7に対応
* mv 30_os-prober 05_os-prober でWin7 が先頭ブートOSになる。

### Brix Command Center(BCC) for EV3
* 最新版のtestXXX.zipを開くとインストーラバイナリがある。それを実行。
* port:usb,  type: EV3,   firmware: linux を選ぶ。
### BCC for NXT
* 最新版でもNXTは認識する。
* LEGOソフトをインストールしないと、USB接続ができない。
