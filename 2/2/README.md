# 中1 2学期中間考査 対策サイト

中学1年 2学期中間考査（9/29・9/30）の対策用静的サイトです。

## 内容

- `index.html` … 対策サイト本体（カウントダウン／3日間プラン／教科別タブ／提出物チェック）
- `files.html` … 練習プリント集のファイルページ（教科→単元で整理、PDF・HTMLリンク）
- `prints/kokugo.html` … 国語 練習プリント（全50問・解答つき）
- `prints/shakai.html` … 社会 練習プリント（全40問・解答つき）
- `prints/sugaku.html` … 数学 練習プリント（全36問・解答つき）
- `prints/rika.html` … 理科 練習プリント（全40問・解答つき）
- `prints/eigo.html` … 英語 練習プリント（全40問・解答つき）

## 使い方

1. 各プリントをブラウザで開き、「印刷 / PDF保存」ボタンで印刷またはPDF保存します。
2. 「印刷に解答・解説を含める」にチェックを入れると、解答が別ページとして印刷されます（通常はオフのまま＝問題用紙のみ）。
3. チェックリストの状態はブラウザに保存されます（localStorage）。

## 技術

- ビルド不要の純粋な静的HTML/CSS/JS
- CSSスクロール駆動アニメーション（`animation-timeline: view()`）＋ IntersectionObserver フォールバック
- View Transitions API、`backdrop-filter`、`prefers-reduced-motion` 対応
- ダークモード自動対応、モバイルファースト

## GitHub Pages で公開する手順

```bash
cd ch1-midterm-site
git init
git add .
git commit -m "Add midterm study site"
git branch -M main
git remote add origin https://github.com/<ユーザー名>/<リポジトリ名>.git
git push -u origin main
```

その後、GitHub のリポジトリ → Settings → Pages → Source を「Deploy from a branch」、
Branch を `main` / `/ (root)` に設定すると公開されます。
（`prints/` 以下の相対リンクはそのまま動作します。）
