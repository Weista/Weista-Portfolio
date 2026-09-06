# Weista Site

个人作品集 + 在线简历的静态网站。纯 HTML/CSS/JS，无框架，可直接托管到任意静态空间。

## 结构

```
Weista Resume Portfolio/
├─ index.html                     # 作品集首页（紫色/蓝色主题、中英切换、悬浮胶囊导航、视差滚动）
├─ assets/
│  ├─ hero-portrait.webp          # 首页半身头像
│  ├─ weista-logo.svg             # Weista logo（矢量）
│  ├─ Skill-*.svg                 # 6 个技能图标（Figma/XD/PS/Ai/Axure/CSS，矢量）
│  ├─ tokens.css / color-tokens.json / Color.zip   # 设计 tokens
│  └─ projects/companalyst-cover.webp  # CA 项目封面
├─ project/
│  └─ companalyst-design-system/
│     └─ index.html               # CompAnalyst 设计系统案例页（自包含单文件，图片内嵌）
├─ resume/
│  ├─ index.html                  # 在线简历页（右上下载 PDF、左上返回作品集）
│  ├─ Vista-Wei-Resume.pdf        # 简历 PDF（下载用）
│  └─ avatar.webp                  # 简历照片
├─ docs/
│  └─ content-template.md         # 内容模板（中文为准，英文对应）
└─ preview.png                    # 首页整页预览
```

## 页面导航

- 首页：关于我 / 履历（工作经验） / 技能 / 作品 / 联系 + 中英切换
- 首页 Hero「查看在线简历」→ `resume/index.html`；「了解更多」→ 关于我
- 首页作品「CompAnalyst 设计系统」→ `project/companalyst-design-system/index.html`
- 在线简历页：「下载 PDF」→ `Vista-Wei-Resume.pdf`；「返回作品集」→ `../index.html`

## 部署

1. 把本文件夹整体上传到托管平台（Netlify / Vercel / GitHub Pages / 任意主机）。
2. 入口文件为 `index.html`，无需构建。
3. 若在子路径部署，请保持相对目录结构不变（`assets/`、`project/`、`resume/`）。

## 内容更新

- 文案统一在 `index.html` 的 `I18N`（中文为主，英文对应）；作品在 `PROJECTS`；工作经历在 `EXPERIENCE`；技能在 `SKILLS`。
- 详情见 `docs/content-template.md`。

---

## 部署到 GitHub Pages（推荐，免费 + 自定义域名）

### 1) 建仓库并上传
1. GitHub → **＋ → New repository**，命名 `weista-site`，设为 **Public**，不勾 README → Create。
2. 把本文件夹**内容**（`index.html`、`assets/`、`project/`、`resume/`、`docs/`、`preview.png`、`.nojekyll`）上传到仓库根。
   - 网页版：**Add file → Upload files** 拖入。
   - 或命令行：
     ```bash
     git init
     git add .
     git commit -m "Weista Site"
     git branch -M main
     git remote add origin https://github.com/<你的用户名>/weista-site.git
     git push -u origin main
     ```

### 2) 开启 Pages
- 仓库 **Settings → Pages** → Source 选 **Deploy from a branch** → Branch 选 `main` / `/(root)` → Save。
- 等待约 1 分钟，得到：
  ```
  https://<你的用户名>.github.io/weista-site/
  ```
  > 全站用**相对路径**，放在 `/weista-site/` 子路径无需改任何代码即可访问。

### 3) 绑定自定义域名（可选）
- Settings → Pages → **Custom domain** 填你的域名 → Save。
- 到域名商添加 DNS：
  | 记录 | 主机 | 值 |
  |---|---|---|
  | CNAME | `www` | `<你的用户名>.github.io` |
  | A | `@` | `185.199.108.153` / `.109` / `.110` / `.111` |
- 回 Pages 勾选 **Enforce HTTPS**（自动签发证书）。

### 4) 部署后自测
- [ ] 首页正常（头像、按钮、导航、语言切换）
- [ ] 「查看在线简历」→ `resume/index.html`；下载 PDF → `Vista-Wei-Resume.pdf`
- [ ] 「CompAnalyst 设计系统」→ `project/companalyst-design-system/index.html`，返回正常
- [ ] 无外部依赖（本包已自包含，网断也能开）

### 说明
- 本文件夹轻量、零外链、纯静态，上传/推送即上线。
- 内容更新：改 `index.html` 里的 `I18N / PROJECTS / EXPERIENCE / SKILLS` 或 `docs/content-template.md` 后重新推送即可。
