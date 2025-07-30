# 🌍 Learn Local

> 地域の事情を「教材」にして、学びの入り口に。
> Learn Agency と系列で連携する、最先線の「地域探索垂直型学習SaaS」。

## 🚀 概要

Learn Localは、地域情報を教材化し、AIとの対話や探索により学習モードを生み出すプラットフォームです。ミニマルなUIで、誰でも簡単に地域の情報を投稿し、AIと共に学ぶことができます。

## 🛠 技術スタック

- **フロントエンド**: Next.js 15 + TypeScript + Tailwind CSS
- **UI コンポーネント**: shadcn/ui + Framer Motion + lucide-react
- **状態管理**: Zustand (persist middleware)
- **バックエンド**: Supabase (DB + RLS + Edge Functions)
- **AI 機能**: GPT-4o (問い生成) + Perplexity (地域検索)
- **地図機能**: Leaflet

## 📁 プロジェクト構造

```
learnlocal/
├── learn-local-app/          # Next.jsアプリケーション
│   ├── app/                  # App Router
│   │   ├── learn-local/      # メインアプリケーション
│   │   │   ├── page.tsx      # トップページ
│   │   │   ├── new/          # 投稿作成
│   │   │   ├── me/           # マイページ
│   │   │   └── posts/[id]/   # 投稿詳細
│   ├── components/           # UIコンポーネント
│   ├── lib/                  # ユーティリティ
│   └── supabase/             # Supabase設定
│       ├── functions/        # Edge Functions
│       └── schema.sql        # データベーススキーマ
```

## 🚀 セットアップ

### 1. リポジトリのクローン

```bash
git clone https://github.com/saitoh-hideki/learnlocal.git
cd learnlocal/learn-local-app
```

### 2. 依存関係のインストール

```bash
npm install
```

### 3. 環境変数の設定

`.env.local`ファイルを作成し、以下を設定：

```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### 4. Supabaseの設定

1. Supabaseプロジェクトを作成
2. データベーススキーマを適用（`supabase/schema.sql`）
3. Edge Functionsをデプロイ
4. 環境変数を設定（Perplexity API、OpenAI API）

### 5. 開発サーバーの起動

```bash
npm run dev
```

## 🎯 主要機能

### 📝 投稿機能
- 地域情報の投稿
- カテゴリ・タグ付け
- 地図での位置指定
- 画像アップロード

### 🔍 検索機能
- リアルタイム検索
- Perplexity API連携
- AI生成問題

### 🤖 AI連携
- GPT-4oによる学習問題生成
- Perplexityによる地域情報検索
- 学びメモ機能

### 🗺️ 地図機能
- Leafletによるインタラクティブ地図
- 位置選択機能
- 座標表示

## 📱 ページ構成

- **トップページ** (`/learn-local`): 投稿一覧・検索機能
- **投稿作成** (`/learn-local/new`): 新規投稿フォーム
- **投稿詳細** (`/learn-local/posts/[id]`): Split View + AI連携
- **マイページ** (`/learn-local/me`): 投稿履歴・学習ログ

## 🔧 開発

### スクリプト

```bash
npm run dev      # 開発サーバー起動
npm run build    # プロダクションビルド
npm run start    # プロダクションサーバー起動
npm run lint     # リンター実行
```

### Edge Functions

```bash
npx supabase functions deploy generate-questions
npx supabase functions deploy perplexity-search
```

## 📄 ライセンス

MIT License

## 🤝 コントリビューション

プルリクエストやイシューの報告を歓迎します！

---

**Learn Local** - 地域の今を、学びに変える。 