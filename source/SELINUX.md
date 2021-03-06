---
title: SELinuxMemo
date: 2021-05-03
---

# SELinuxについて
SELinux (Security Enhanced Linux)<br>
ファイル/ディレクトリのパーミッションを所有者が自由に設定できる任意アクセス制御（DAC:Discretionary Access Control）を<br>
一元的に管理する強制アクセス制御(MAC:Mandatory Access Control)にすることでシステム全体を統合的に管理するセキュリティ拡張のカーネルモジュール

## ポイント
* システムに侵入されても被害を最低限にするための受動的なセキュリティ機構<br>
### そのための仕組み
* Role Base Access Control(ロールベースアクセス制御)
  * root権限をロール(役割)に分割する
  * ユーザー、サービスに最小限の権限を付与する「最小特権」
  
* Type Enforcement
  * ファイル・ディレクトリ・デバイスのシステムリソースにタイプ(ラベル・識別子)を付ける
  * プロセスのタイプはドメイン

* ドメイン遷移
  * 生成されたプロセスに元プロセスより小さな権限のドメインを割り当てる


参考書籍　Linuxサーバーセキュリティ徹底入門オープンソースによるサーバー防衛の基本　中島能和　/著