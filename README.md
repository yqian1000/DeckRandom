# DeckRandom

会话级转盘抽奖：在当前标签页添加图片和/或文字，随机抽取且不放回。刷新或关闭页面会清空全部对象。

## 本地运行

```bash
npm install
npm run dev
```

## 构建

```bash
npm run build
```

产物在 `dist/`。

## 部署到 Cloudflare Pages

这个 Git 项目在 Cloudflare 里是 **Pages**（不是 Worker）。构建用 Vite，部署必须用 `wrangler pages deploy`。

### Git 连接

1. [Cloudflare Dashboard](https://dash.cloudflare.com/) 打开该 Pages 项目。
2. **Settings → Builds** 里改成：
   - **Build command:** `npm run build`
   - **Deploy command:** `npx wrangler pages deploy ./dist`
   - **Node version:** `20` 或更高
3. 不要用 `npx wrangler deploy`。那是 Worker 命令，在 Pages 项目上会直接报错。

### 本机 Wrangler

```bash
npx wrangler login
npm run deploy
```
