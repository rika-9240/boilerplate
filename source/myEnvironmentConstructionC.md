---
title: C言語自分用学習環境
date: 2021-04-23
tags: ["ポートフォリオ"]
excerpt: 自分用メモ
---

# 2か所以上の場所で作業したいのでUSBにGCCを入れて使った

  ## 用意した物・したこと
  - gcc (公式からダウンロード・USBに保存)
  - パソコン毎にpathを通す<br>
  設定/システム/詳細情報（右）/システムの詳細設定/システムのプロパティ/環境変数（N)のシステム環境変数の「Path」にF:\myGcc\mingw32\binを追加（F:はエクスプローラーで確認する)<br>
  - printf表示の文字化け対策<br>
    - コマンドプロンプトの設定を変更する場合<br>
    \>chcp 65001 //UTF-8モード<br>
    \>chcp 932 //SHIFT-JISモード（デフォルト）<br>
    ※chcp.comFileはC:\Windows\system32にある（なきゃ探して）のでここにPathが通ってる必要がある
    - 入出力使用時SHIFT-JISモードでコンパイラ<br>
    \>gcc -fexec-charet=CP932 -o fileName fileName.c<br>
    面倒なのでバッチファイル作る<br>
    io-m.bat<br>
    中身　gcc -fexec-charset=CP932 -o %1 %1.c<br>
    使い方　>io-m fileName<br>
  - 試したｃﾌｧｲﾙ・exeﾌｧｲﾙをｃＢｏｘﾌｫﾙﾀﾞに自作batコマンドで移動<br>
    m.bat<br>
    中身　move %1.* cBox
    使い方　>m fileName
# コマンド
  ## コマンドプロンプトを立ち上げたらまず移動
  - \>f: //USBのドライブに移動<br>
  - \>cd ~mingw32/bin //ｇｃｃのmingw32/binへ移動<br>
  ※ここでメモ帳を使ってソースを保存＋コンパイルしていく<br>
  ## コンパイル
  - C言語のコンパイル　>gcc<br>
  - C++のコンパイル　>g++<br>
  - 実行ファイル名付き　>gcc fileName.c -o exeName.exe<br>
  <br>
  ## ライブラリ
  - 算術ライブラリとリンク　<br>
    \>gcc fileName.c -m<br>
    (#include <math.h>のsin(),cos()等関数)<br>
    >\gcc -lstdc++ -o fileName fileName.cpp<br>
    (Einclude <iostream>のstd::cout,std::endl,oerride<<演算子)<br>
  <br>
  - ライブラリリンク不要関数・Memo<br>
    <stdio.h>(sprintf(boxStr,"%s%s%d",str1,str2,intI)<br>
    ※printfで表示する場合sprintfで既に表示できる状態なので<br>
    変数のみ(boxStr)でOK指定子をつける場合は%s<br>
    <string.h>(memcpy(inCp,outCp,sizeof(outCp)配列のコピー<br>
    strcpy(char inStr,char outStr)文字列のコピー)<br>
    strncpy(char inStr,char outStr,コピーする文字数)<br>
    ※EOSの付け忘れ注意 inStr[コピーする文字数] = '\0';<br>
    strcat(mainStr,addStr);<br>
    <ctype.h>(isalnum(char c)...etc char判定関数)<br>
    <stdlib.h>(atoi(char str[])...数字を数値に変換)<br>
  メモリアドレス　％ｐ<br>
  アドレスを求める演算子　＆<br>
  引数は値渡し（コピー）<br>
  アドレスを渡すことで変数の中身を変更できる<br>
  配列名のアドレスは配列[0]<br>
  C++マニュアル<br>
  GNU：https://gcc.gnu.org/onlinedocs/libstdc++/index.html<br>
  C++ include <br>
  <bits/stdc++.h>(https://qiita.com/hakatashi/items/f9d9abf05a002b5c4dc5
  全ての標準ライブラリに含まれるヘッダがインクルードできるが基本使わない)
  <iostream>(using namespace std; cout << "hellowrold" << endl;)
