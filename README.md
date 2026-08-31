# Portfolio Website

UI設計・フロントエンド実装・低コストDX推進を目的としたポートフォリオWebサイトです。
Google スプレッドシートをデータベースとして活用し、Google Apps Script (GAS) 経由で GitHub へ `data.json` を自動同期・配信する**完全サーバーレス・維持費0円**の構成で運用しています。

🔗 **公開URL**: https://nr-works-dev.github.io/portfolio/

---

## 🛠 システムアーキテクチャ

```text
[ Google スプレッドシート ] (Master DB)
         │
         ▼ (トリガー / 手動同期)
[ Google Apps Script (server.gs) ]
         │
         ▼ (GitHub REST API経由でコミット & プッシュ)
[ GitHub Repository ] (data.json & assets)
         │
         ▼ (ホスティング)
[ GitHub Pages (index.html) ]```

✨ 主な特徴・設計のこだわり
サーバーレス＆維持費0円運用
専用バックエンドサーバーを立てず、Google スプレッドシート ＋ GAS ＋ GitHub Pages の組み合わせにより、固定費を完全ゼロに抑えて運用。

スキーマ駆動による柔軟なデータ管理
schema.yaml に定義された構造に従い、スプレッドシートの各シート（About, TechStack, Works, Strengths, Contact, asset）を data.json へ構造化パース。

モダンでレスポンシブなUI/UX

すりガラス効果（backdrop-filter）を採用した画面上部追従ヘッダー。

Noto Sans JP を最優先とした鮮明なタイポグラフィ設計。

実績をスムーズに確認できる横スクロール＋左右ナビゲーション付きカルーセルスライダー。

モバイル端末（スマートフォン・タブレット）に完全対応したレスポンシブデザイン。

きめ細やかなContact導線
メーラー自動起動（件名・本文プリセット）に加え、メーラー非対応環境向けのメールアドレスフォールバック案内や、X・外部リンクの視認性に優れたボタンスタイリング。

💻 技術スタック
フロントエンド: HTML5, CSS3 (CSS Variables, Flexbox, Grid), JavaScript (Vanilla ES6+)

バックエンド / API: Google Apps Script (GAS)

データベース / 管理: Google Sheets (Google スプレッドシート)

インフラ / ホスティング: GitHub Pages, GitHub REST API

フォント・アイコン: Google Fonts (Noto Sans JP, Poppins, Outfit, Fredoka), FontAwesome 6

📂 リポジトリ構成
├── index.html        # ポートフォリオ本体（フロントエンド）
├── schema.yaml       # データ構造定義ファイル
├── server.gs         # スプレッドシート ➔ GitHub JSON同期用GASスクリプト
├── data.json         # スプレッドシートから生成されたサイトデータ
├── assets/           # バナー、背景、UIアセット画像格納フォルダ
└── README.md         # プロジェクト説明ドキュメント

📄 ライセンス
Copyright (c) 2026 NR-Works. All rights reserved.
