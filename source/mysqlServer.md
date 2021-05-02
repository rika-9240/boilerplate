---
title: LinuxOSにMySQLサーバ構築
date: 2021-04-26
---
# MySQL 或いは　MariaSQL をゲストOSにサーバ構築する
  ## 目的
  - グループワークで作ったものを一人で再現するが在庫、顧客管理にＭｙＳＱＬを使った
  - 家計簿として使う

  ## 2021/04/26ゲストOＳにＭｙＳＱＬサーバを構築し、ホストＯＳから使える状態にする
  ![mysqlserver.drawio](https://github.com/rika-9240/boilerplate/blob/master\path\Linux\MySQLServer.drawio.png?raw=true)

  ### OS設定
  - ソフトウェア インフラストラクチャーサーバ　+　開発ツール
  - 管理者としてを選択してみたがログイン時は＄でルートパスワードで＃になる。。。どう違うかは後で調べる
  - ログイン後
    - selinuxを無効にする<br>
    有効状態<br>

    ```
    $ getenforce
    Enforcing
    ```
    vi で /etc/selinux/config を編集<br>
    ```
    SELINUXTYPE=enforcing
    編集
    SELINUXTYPE=disabled
    ```
    サーバ再起動<br>
    ```
    $ reboot
    ```
    確認<br>
    ```
    $ getenforce
    Disabled
    ```
    - systemctlをtabキー補完で使えるようにする
    ```
    # yum install bash-completion
    ```
    Error出た
    [error](https://github.com/rika-9240/boilerplate/blob/master\path\20210426ServerRen\installError.png)
    ネットワーク接続が確立してない模様

    # ネットワーク接続の確認
    ```
    # nmcli device status
    DEVICE TYPE     STATE        CONNECTION
    enp0s3 ethernet disconnected --
    lo     loopback unmanaged    --
    ```
    enp0s3をconnected にする
    ```
    # nmcli connection up enp0s3
    Connection successfully activated (....)
    ```
    もう一度確認
    ```
    # nmcli device status
    DEVICE TYPE     STATE        CONNECTION
    enp0s3 ethernet connected    enp0s3
    lo     loopback unmanaged    --
    ```
    さらに詳しく確認
    ```
    # nmcli con show enp0s3
    ...
    connection.autoconnect:    no
    ...
    ```
    これだと再起動で元に戻るので
    ```
    # nmcli con mod enp0s3 connection.autoconnect "yes"
    ```
    connection.autoconnect:    yes を確認
    これで起動事に自動で接続する

    この設定を反映させるためにネットワークインターフェイスを再起動
    ```
    # nmcli device disconnect enp0s3
    # nmcli device connect enp0s3
    ```
    そもそもアダプターを足し忘れてたことに気づいた
    一度ゲストの電源オフ
    VirtualBoxマネージャーのネットワークから
    アダプター１をNAT
    アダプター２をホストオンリーアダプターに設定

    これで繋がった！
    - ネット繋がったのでsystemctlをtabキー補完で使えるようにする
    ```
    # yum install bash-completion
    ```


    

  ## 参考サイト
  https://www.rem-system.com/centos-install/
  https://www.rem-system.com/linux-first-setting/
  https://qiita.com/tz2i5i_ebinuma/items/a70fe0b6a718d79d12cf
  http://www.miloweb.net/mysql.html
