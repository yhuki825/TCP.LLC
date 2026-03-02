# 有限会社テー・アンド・シーピー — コーポレートサイト

シングルページのコーポレートWebサイトです。

## ファイル構成

```
tcp-website/
├── index.html      # メインページ（全コンテンツ）
├── _headers        # Cloudflare Pages 用セキュリティ・キャッシュヘッダー
├── _redirects      # Cloudflare Pages 用リダイレクト設定
└── README.md       # 本ファイル
```

## Cloudflare Pages へのデプロイ手順

### 方法 A — GitHub 経由（推奨）

1. このフォルダの内容を GitHub リポジトリにプッシュする
2. [Cloudflare Dashboard](https://dash.cloudflare.com/) にログインし、**Workers & Pages** → **Create application** → **Pages** → **Connect to Git** を選択
3. リポジトリを選択し、以下の設定を行う

| 項目 | 値 |
|---|---|
| Framework preset | `None` |
| Build command | （空欄） |
| Build output directory | `/` または `.` |

4. **Save and Deploy** をクリック

### 方法 B — Direct Upload（Git 不要）

1. [Cloudflare Dashboard](https://dash.cloudflare.com/) → **Workers & Pages** → **Create application** → **Pages** → **Direct Upload**
2. プロジェクト名を入力し、`tcp-website` フォルダ内のファイルをすべてアップロード
3. **Deploy site** をクリック

## 注意事項

- `_headers` と `_redirects` は Cloudflare Pages の特殊ファイルです。必ずルートに配置してください。
- 外部リソース（Tailwind CDN / Google Fonts / Lucide Icons / Unsplash 画像）はインターネット接続が必要です。
- 本番運用では Tailwind CSS をビルドしてローカルに含めることを推奨します。
