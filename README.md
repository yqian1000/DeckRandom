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

## 部署到 Cloudflare

当前仓库按 **Workers 静态资源** 配置（控制台会执行 `npm run build`，再执行 `npx wrangler deploy`）。

### Git 连接

1. [Cloudflare Dashboard](https://dash.cloudflare.com/) → **Workers & Pages** → 连接本仓库。
2. 构建设置：
   - **Build command:** `npm run build`
   - **Deploy command:** `npx wrangler deploy`（新控制台默认值，保持即可）
   - **Node version:** `20` 或更高
3. 不要填写 Pages 的 Output directory，也不要把构建命令改成 `npm run deploy`。

`wrangler.toml` 里的 `[assets]` 指向 `dist/`，这样 `wrangler deploy` 会上传构建产物，而不需要 Worker 入口文件。

### 本机 Wrangler

```bash
npx wrangler login
npm run deploy
```
