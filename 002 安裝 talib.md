## 安裝 talib

手動執行以下指令
```
$ wget http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz
$ untar and cd
$ ./configure --prefix=/usr
$ make
$ sudo make install
假如之前用anaconda安裝過，需要將生成的庫替換到anaconda安裝的目錄
$ cp /usr/lib/libta_lib* /home/user/anaconda2/lib/
```
