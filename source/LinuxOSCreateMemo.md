---
title: LinuxOS構築Memo
date: 2021-04-14
---

# VirtualBox上でのLinuxOS構築自分用メモ

 ## ViertualBox version 6.1.18
 ![versionpng](https://github.com/rika-9240/boilerplate/blob/master\path\Linux\ViertualBoxVersion.png?raw=true)

 ## CentOS7のisoを用意
  * 公式サイトからダウンロードする
  「CentOS-7-x86_64-DVD-2009.iso」
  

 ## 新規作成
  * 仮想マシン（M)から新規を選択
  ![new create](https://github.com/rika-9240/boilerplate/blob/master\path\Linux\NewCreate.png?raw=true)
   * 名前・マシンフォルダー・タイプ・バージョンを設定<br>
   名前：CentOS7_Test<br>
   マシンフォルダー：デフォルト<br>
   タイプ（T):Linux<br>
   ※タイプは名前入力時にLinuxとわかる名称は自動で変わる<br>
   バージョン（V):デフォルト<br>
   --> 次へ（N)
   * メモリサイズ
    何がしたいかによって変わる<br>
    特別重い処理がないなら1024~2048でいいと思う<br>
   --> 次へ（N)
   * ハードディスク
    仮想ハードディスクを作成する
    --> 次へ（N)
   * ハードディスクのファイルタイプ
    VDI(ViertualBox Disk Image)<br>
    --> 次へ（N)
   * 物理ハードディスクにあるストレージ
    固定を選ぶときはOSのサイズを確認する必要あり<br>
    今回は可変サイズ（D)でいく<br>
    --> 次へ（N)
   * ファイルの場所とサイズ
     ここもOSサイズ要確認、OSによってはデフォルトでは不足することがある<br>
     16GB<br>
    --> 次へ（N)

    * ログファイルが見つからないと出た
    ...isoデータ指定タイミングなかったな？<br>
    --> 設定のストレージからisoﾌｧｲﾙ指定<br>
    --> 起動<br>
   　![start up](https://github.com/rika-9240/boilerplate/blob/master\path\Linux\startUp.png?raw=true)
    ...isoﾌｧｲﾙここで指定で来たっぽい<br>
    isoﾌｧｲﾙ指定して起動<br>
    ※ここで仮想画面にカーソルを合わせてしまうと仮想のcui画面からカーソルが出られなくなる<br>
    その時は　右のCtrl　でホストOSに戻ります。
 ## OSの設定
   * 言語設定
    日本語<br>
    --> 続行（C)
   * !マークのある　システム/インストール先（D)を設定
    ![setUp](https://github.com/rika-9240/boilerplate/blob/master\path\Linux\setUp.png?raw=true)
    今回はテストなのでデフォルトで完了
   * ソフトウェアの選択（！ここがLinuxの醍醐味だと思う）
    今回は最小限のインストールを選択(デフォルト)<br>
   * インストール中にユーザ設定
     ROOT パスワード（R)-->****test
     ユーザの作成（U)-->rika user****test
     ...セットアップ作業待ち
 ## CentOS7のソフトウェア選択デフォルト
    

