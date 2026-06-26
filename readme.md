# C4-2AFC PsychoPy実験（オンライン版）

このディレクトリには、PsychoPyで作成した2AFC（2肢強制選択）実験のオンライン版が含まれています。

## ファイル構造

```
C4/
├── C4-2AFC.psyexp                   # PsychoPy実験ファイル（元ファイル）
├── C4-2AFC_lastrun.py               # PsychoPythonスクリプト
├── html/                             # PsychoPyオンライン出力ディレクトリ
│   ├── index.html                   # メインHTMLファイル
│   ├── C4-2AFC.js                   # 実験のメインJavaScriptファイル
│   ├── C4-2AFC-legacy-browsers.js  # 古いブラウザ用のJavaScriptファイル
│   ├── lib/                         # PsychoJSライブラリ
│   │   ├── psychojs-2022.1.4.js
│   │   ├── psychojs-2022.1.4.iife.js
│   │   ├── psychojs-2022.1.4.css
│   │   └── ...
│   └── resources/                   # 実験で使用するリソースファイル
├── lib/                              # PsychoJSライブラリ（バックアップ）
└── readme.md                         # このファイル
```


## PsychoJSバージョン

このプロジェクトは **PsychoJS 2022.1.4** を使用しています。
