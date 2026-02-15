# BatteryCollector (UE5.4 Upgrade)

## Branches

- main  
  Upgraded from UE4.21 to UE5.4 (build and runtime verified)

- legacy/ue4.21  
  Original implementation (UE4.21)

## Implementation

- C++を主体に実装
- SphereComponentによる取得判定
- Tickでバッテリー残量を管理
- Blueprint内でSetVectorParameterValueを使用し、BodyColorを動的に変更
- バッテリー残量に応じて移動速度およびキャラクターの体色を変更
- UE4.21からUE5.4へ移行対応済み

## Overview

BatteryCollectorは、Unreal Engineを用いて制作したアクションゲームです。
プレイヤーはフィールド上に出現するバッテリーを収集し、エネルギーを維持しながらクリアを目指します。

クリア条件
・バッテリーを取得して画面下部にあるゲージを満タンにする

ゲームオーバー条件
・画面下部にあるバッテリーゲージが空になり、キャラクターの電力がなくなった場合

キャラ操作・仕様
・移動: W,A,S,D
・周辺のバッテリーを拾う: c
・ジャンプ: スペースキー
・バッテリーゲージ: 時間経過で減少していく
・バッテリー取得時: バッテリーとキャラクターの間に電撃エフェクトが発生し、ゲージを増加させる

バッテリー増減に伴うキャラクター仕様
・バッテリー残量高: 体色がオレンジ色に近づき、移動が速くなる
・バッテリー残量低: 体色が青くなり、移動が遅くなる