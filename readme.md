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

## 実行方法

### 方法1: PsychoPyから直接実行（推奨）

1. PsychoPyで`C4-2AFC.psyexp`ファイルを開く
2. メニューから「Run online」または「Online」ボタンをクリック
3. 自動的にブラウザが開き、実験が開始されます

**注意**: PsychoPyは`html/`ディレクトリをルートとしてHTTPサーバーを起動します。

### 方法2: 手動でHTTPサーバーを起動

PsychoPyのオンライン実験はES6モジュールを使用しているため、**必ずHTTPサーバー経由でアクセスする必要があります**。HTMLファイルをダブルクリックして開くだけでは動作しません。

#### html/ディレクトリから実行する場合（PsychoPyの動作と同じ）

```bash
cd "/Users/waka/Desktop/Grad School/26_Spring/IST_CI-lab/Exps/C4/html"
python3 -m http.server 8000
```

ブラウザで以下のURLにアクセス：
```
http://localhost:8000/index.html
```

#### ルートディレクトリから実行する場合

```bash
cd "/Users/waka/Desktop/Grad School/26_Spring/IST_CI-lab/Exps/C4"
python3 -m http.server 8000
```

ブラウザで以下のURLにアクセス：
```
http://localhost:8000/html/index.html
```

## トラブルシューティング

### PsychoPyから実行するとディレクトリリスティングが表示される

- 必要なファイル（`index.html`、`C4-2AFC.js`等）が`html/`ディレクトリにあることを確認してください
- ルートディレクトリのファイルを`html/`ディレクトリにコピーしてください：
  ```bash
  cp index.html C4-2AFC.js C4-2AFC-legacy-browsers.js html/
  cp -r resources html/
  ```

### `ERR_EMPTY_RESPONSE` エラーが表示される

- HTTPサーバーが起動していない可能性があります
- 上記の「実行方法」に従ってサーバーを起動してください

### モジュールのインポートエラーが表示される

- ファイルパスが正しいか確認してください
- `html/lib/`ディレクトリにpsychojsファイルが存在するか確認してください

### データが保存されない

- ローカルで実行する場合、データは`html/data/`ディレクトリに保存されます
- サーバーの書き込み権限を確認してください

## 対応ブラウザ

- Chrome（推奨）
- Firefox
- Safari
- Edge

古いブラウザの場合、自動的にlegacy版のJavaScriptファイルが読み込まれます。

## PsychoJSバージョン

このプロジェクトは **PsychoJS 2022.1.4** を使用しています。
