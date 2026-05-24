# snapcart

Next.js 14 製のシンプルな Web アプリ。

## 必要環境

- Node.js 18.17 以上（ローカル実行する場合）
- もしくは Docker

## ローカルで起動

```bash
npm install
npm run dev          # 開発サーバー (http://localhost:3000)
```

本番ビルドを試す場合:

```bash
npm run build
npm start            # http://localhost:3000
```

## Docker で起動

プロジェクトルートで:

```bash
# イメージのビルド
docker build -t snapcart:latest .

# コンテナ起動（3000 番を公開）
docker run --rm -p 3000:3000 snapcart:latest
```

起動後、以下で動作確認:

- トップページ: <http://localhost:3000>
- ヘルスチェック: <http://localhost:3000/api/health>

バックグラウンドで動かす場合:

```bash
docker run -d --name snapcart -p 3000:3000 snapcart:latest
docker logs -f snapcart      # ログを見る
docker stop snapcart         # 停止
```

## 主なファイル

- `pages/index.js` — トップページ
- `pages/api/health.js` — ヘルスチェック API
- `data/products.js` — 商品データ
- `Dockerfile` — 本番用 Docker イメージ定義
