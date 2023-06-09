# 決戦! n乗谷城

## 構成
- battle_Njoudani_castle.cpp : ゲームのメインプログラム
- board.hpp : 盤面についてのクラス
- fortifier.hpp : 職人についてのクラス
- initial.txt : 初期盤面のデータファイル

---

### battle_Njoudani_castle.cpp
ゲームの流れ
1. 初期化(盤面と設定のロード)
1. ゲーム進行(ターンの許す限り)
    - 状況の提供
    - 行動の取得
    - 片方のターン
        - 職人の数だけループ
        - *職人の行動を選択(優先順位は[滞在，解体，建築，移動]の順)
    - *もう一方のターンは上記と同じ
1. 盤面状況から勝敗判定



---

### initial.txt
- マップ
- 味方職人初期位置
- 相手職人初期位置

#### 条件
> 11 ≤ H, W ≤ 25  
1 ≤ i ≤ H  
1 ≤ j ≤ W  
a<sub>i,j</sub> = <castle_area> | <pool_area> | <flat_area>  
2 ≤ A, E ≤ 6  
A = E  
1 ≤ k ≤ A,E  
i ≤ p<sub>k</sub> ≤ H  
i ≤ q<sub>k</sub> ≤ W

> <castle_area> = 'c'  
<pool_area> = 'p'  
<flat_area> = 'f'  

#### 一般例
> H W  
> a<sub>1,1</sub> … a<sub>1,W</sub>  
> …  
> a<sub>H,1</sub> … a<sub>H,W</sub>  

> A  
> p<sub>1</sub> q<sub>1</sub>  
> …  
> p<sub>A</sub> q<sub>A</sub>  

> E  
> p<sub>1</sub> q<sub>1</sub>  
> …  
> p<sub>E</sub> q<sub>E</sub>  
