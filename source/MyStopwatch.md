# 自分用の作業ストップウォッチを作る
   [ｿｰｽ](https://github.com/rika-9240/TimerF20210403)
   * 設計
    ![timer.drawio](https://github.com/rika-9240/boilerplate/blob/master\source\timer.drawio.png?raw=true)
   　

   * start/stop
   * 5分経過お知らせ -->3分間音が鳴るようにする
   　　　　　　      -->時間を設定できるようにする
   * reset

 ## 音ﾌｧｲﾙを時間で鳴らしたり止めたりする
   * wavFileの再生 --> SoundPlayerClass
   * wavFileの用意 --> 迷い中　自作するか？Freeを使うか？
    * 作業中 -->作業用の集中できる音（デフォルト：無音）
    * 休憩中 -->休憩用で気づくけどうるさくない音
 ## デフォルトとして3分後に音が鳴るタイマー
 ## デフォルトを編集可能にする
 ## 編集可能部分として
  * 最初の経過時間、アラームが鳴り続ける時間
  * それぞれの音源設定 --> デフォルトで無音＋アラーム音
  * リピート機能

 ## IDEについて
  * VSで作った後VScodeで動かす-->できたのでGitHubに乗せるWindowsアプリケーションはこれでいく

