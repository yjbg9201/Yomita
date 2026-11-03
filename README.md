# 読み太
 [![Build Status](https://travis-ci.org/TukamotoRyuzo/Yomita.svg?branch=master)](https://travis-ci.org/TukamotoRyuzo/Yomita)

読み太はUSIプロトコル準拠の将棋エンジンです。  
主にチェスエンジンのStockfishをベースとし、  
学習部、評価関数のデータ構造はやねうら王を参考にしています。  
また、一部の処理はAperyを参考にしています。  
  
実行ファイル、評価関数バイナリはこちらからダウンロードできます。
https://github.com/TukamotoRyuzo/Yomita/releases/tag/SDT5  

付属している評価関数バイナリは、読み太でのみ使うことができます。  
付属しているbook.txtは局面に対する指し手が1手しか登録されていないので、毎回必ず同じ定跡を選択します。  
定跡を使用したくない場合、エンジン設定で「UseBook」のチェックを外してください。  



## 期待勝率の出力

USIオプションで、形勢判断を評価値(cp)の代わりに、または評価値と併せて期待勝率で出力できます。

| オプション | 既定値 | 説明 |
|---|---|---|
| `ScoreOutput` | `cp` | `cp`: 従来通り `info score cp x` / `winrate`: `info ... score winrate y` / `both`: 評価値の行に加えて `info depth d multipv n score winrate y` の行も出力 |
| `PonanzaConstant` | `600` | 変換式 y = 1 / (1 + exp(-x / P)) の定数 P (1〜100000) |

y は 0〜1 の小数(小数点以下4桁)で、詰みの場合は勝ちなら 1、負けなら 0 になります。
なお `score winrate` はUSIプロトコルの標準ではないため、GUIによっては表示できない場合があります。
