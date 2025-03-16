# Slidev Presentation on GitHub Pages

このリポジトリは、Slidevで作成したプレゼンテーションをGitHub Pagesでホストするためのテンプレートです。

## 🚀 デプロイ済みスライド

https://sssshun664.github.io/contents/

## 📝 セットアップ手順

### 1. プロジェクトの初期化

```bash
# プロジェクトの作成
npm init slidev@latest

# 依存関係のインストール
npm install
```

### 2. 必要なファイルの設定

#### 2.1 `.gitignore`の作成

```
node_modules
.DS_Store
dist
*.local
.idea
*.log
```

#### 2.2 GitHub Actionsワークフローの設定

`.github/workflows/deploy.yml`を作成:

```yaml
name: Deploy pages

on:
  push:
    branches: [main]
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment
concurrency:
  group: pages
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: 'lts/*'
          cache: npm

      - name: Setup Pages
        uses: actions/configure-pages@v4

      - name: Install dependencies
        run: npm install

      - name: Install Playwright
        run: npx playwright install chromium

      - name: Build
        run: npm run build -- --base /${{ github.event.repository.name }}/

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: dist

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    
    needs: build
    runs-on: ubuntu-latest
    
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

#### 2.3 PDFエクスポート用の依存関係追加

`package.json`に以下を追加:

```json
{
  "devDependencies": {
    "playwright-chromium": "^1.42.1"
  }
}
```

### 3. スライドの設定

`slides.md`のフロントマターにPDFダウンロードオプションを追加:

```yaml
---
theme: seriph
# ... 他の設定 ...
download: true
---
```

### 4. GitHub上での設定

1. リポジトリの "Settings" に移動

2. "Pages" セクションで:
   - "Build and deployment" の Source を "GitHub Actions" に設定

3. "Actions" > "General" で:
   - "Workflow permissions" を "Read and write permissions" に設定
   - "Allow GitHub Actions to create and approve pull requests" にチェック
   - "Actions permissions" を "Allow all actions and reusable workflows" に設定

### 5. デプロイ

```bash
# 変更をコミット
git add .
git commit -m "Initial commit"

# GitHubにプッシュ
git push origin main
```

## 🔧 開発

```bash
# 開発サーバーの起動
npm run dev

# ビルド
npm run build

# PDFエクスポート
npm run export
```

## 📚 参考リンク

- [Slidev Documentation](https://sli.dev/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

## 🤝 コントリビューション

1. このリポジトリをフォーク
2. 新しいブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add amazing feature'`)
4. ブランチをプッシュ (`git push origin feature/amazing-feature`)
5. プルリクエストを作成

## 📄 ライセンス

MITライセンスの下で公開されています。詳細は[LICENSE](LICENSE)ファイルを参照してください。
