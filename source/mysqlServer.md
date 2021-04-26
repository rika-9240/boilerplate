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
    有効状態
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
    - 
  ## 参考サイト
  https://www.rem-system.com/centos-install/
  https://www.rem-system.com/linux-first-setting/
  https://qiita.com/tz2i5i_ebinuma/items/a70fe0b6a718d79d12cf
  http://www.miloweb.net/mysql.html
