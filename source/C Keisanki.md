 # C言語で計算機

  - 引数を計算する...おそらく一番簡単なタイプ　
    - それぞれ一つの演算子のみ対応
    - 引き算の場合...コード埋め込みで引数を渡すにはどうすればいいかわからない

```CPP
#include <stdio.h>
#include <stdlib.h>

int main(int argc , char *argv[] ){
    int i,n;
    int sum = 0;
    sum = atoi(argv[1]);
    printf("%d ",sum);
    for(i=2; i<argc; i++){
    n = atoi(argv[i]);
    sum -= n;
    printf("- %d  ",n);
    }    
    printf("= %d\n",sum);
    return 0;
}
```

  - scanfを使う＋入力内容は指示あり
    - 簡単になら演算子固定で数値のみ入力させる

  - scanfを使うがまとめて入力する
    - 記号を調べて計算する
