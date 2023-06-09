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
0 ≤ i ≤ H-1  
0 ≤ j ≤ W-1  
a<sub>i,j</sub> = <castle_area> | <pool_area> | <flat_area>  
2 ≤ A, E ≤ 6  
A = E  
0 ≤ k ≤ A-1,E-1  
i ≤ p<sub>k</sub> ≤ H  
i ≤ q<sub>k</sub> ≤ W

> <castle_area> = 'c'  
<pool_area> = 'p'  
<flat_area> = 'f'  

#### 一般例
> H W  
> a<sub>0,0</sub> … a<sub>0,W-1</sub>  
> …  
> a<sub>H-1,0</sub> … a<sub>H-1,W-1</sub>  

> A  
> p<sub>0</sub> q<sub>0</sub>  
> …  
> p<sub>A-1</sub> q<sub>A-1</sub>  

> E  
> p<sub>0</sub> q<sub>0</sub>  
> …  
> p<sub>E-1</sub> q<sub>E-1</sub>  
