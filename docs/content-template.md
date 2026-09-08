# 作品集 · 内容模板（Content Template）

> **用途**：记录 Portfolio 首页（Index）的全部文案，方便你后续更新内容。
> **规则**：**以中文为准（Source），英文围绕中文进行更新（English follows Chinese）。**
> 改中文 → 再同步英文，保持两边语义一致、长度相近。

---

## 0. 内容存放位置

网站是纯 HTML + 一个 JS 字典，**所有文案集中在一个地方**，改起来很省事：

| 改什么 | 去哪里改 |
|---|---|
| 页面文案（导航/首页/关于/技能/联系/表单） | `portfolio/index.html` 里的 **`I18N = { zh:{...}, en:{...} }`** |
| 作品卡片 | `portfolio/index.html` 里的 **`PROJECTS` 数组** |
| 语言默认值 | `let lang = "zh"`（`zh` 或 `en`） |

改完 `index.html` 直接保存即可——当前 `index.html` 已是**自包含单文件**（图片内嵌）。如需保留一套引用 `assets/` 的源码版，可另存为 `index.source.html`。

---

## 1. 内容清单（中文源 → 英文）

每项字段格式：`key` = 中文字符串 | 英文字符串

### 1.1 品牌 / 导航
| key | 中文 | 英文 |
|---|---|---|
| brand | 魏彤 | Vista Wei |
| brand.portfolio | · 作品集 | · Portfolio |
| nav.about | 关于我 | Who am I |
| nav.skills | 技能 | Skills |
| nav.portfolio | 作品 | Portfolio |
| nav.contact | 联系 | Contact |
| lang | 🌐 中文 | 🌐 EN |

### 1.2 Hero 首屏
| key | 中文 | 英文 |
|---|---|---|
| hero.greet | 你好，我是 | Hi, I'm |
| hero.name | 魏彤 | Vista Wei |
| hero.sub | UI/UX Designer。B端设计；设计系统构建；产品用户体验设计；数据可视化设计... | Designing accessible, data-driven product experiences for global enterprise teams. Specializing in design systems, B2B analytics, and AI-first products — always exploring what's next. |
| hero.cta | 了解更多（primary） | Read more |

> Hero 按钮：`hero.viewResume` 为 outlined 按钮，跳转在线简历 `../魏彤_简历_阅读版.html`；`hero.cta` 为 primary 按钮，滚动到关于我。**「下载 PDF」按钮放在在线简历页（`魏彤_简历_阅读版.html`）右上角**，链接 `魏彤_简历_阅读版.pdf`。
| hero.viewResume | 查看在线简历 | View My Resume |

### 1.3 关于我（Who am I）
| key | 中文 | 英文 |
|---|---|---|
| about.eyebrow | 关于 | About |
| about.title | 我是谁 | Who am I |
| about.desc | 我是一名驻地上海的UI/UX 设计师。长期负责包括B端设计、网页设计、设计系统构建等工作内容，十多年来与团队相互合作，将复杂抽象的业务流程与交互逻辑进行梳理重构，以直观友好的操作界面呈现给用户。 | I'm a UI/UX designer based in Shanghai. Over the past decade-plus, I've led B2B design, web design, and design system building — partnering with teams to reframe complex, abstract business flows and interaction logic into intuitive, friendly interfaces. |
| about.f1.t / f1.d | 设计系统 / Token 驱动的组件化设计系统，让大型多产品生态保持一致、可维护。 | Design Systems / Token-driven, component-first systems keep large multi-product ecosystems consistent and maintainable. |
| about.f2.t / f2.d | B端设计 / 长期负责产品部门的 B 端与网页设计，将复杂业务流程重构为直观友好的界面。 | B2B Design / Long-running product-org B2B & web design that reframes complex workflows into intuitive, friendly interfaces. |
| about.f3.t / f3.d | AI 工作流 / 将 AI 工具融入设计流程，与团队协作提升交付效率与质量。 | AI Workflow / Weave AI tools into the design flow and collaborate with teams to boost efficiency and delivery quality. |

### 1.4 技能（Skills）
| key | 中文 | 英文 |
|---|---|---|
| skills.eyebrow | 能力 | Capabilities |
| skills.title | 技能 | Skills |
| skills.desc | 从 UI 起步的 PS 时代逐步成长为以 Figma 作为主流工具的 UI/UX 设计师，并结合前端知识与原型工具，辅助团队推进项目落地。AI 时代，依旧不断学习，合理利用 Figma MCP / Harness Agent 等 AI 工具，结合不同能力的 AI 模型提升设计工作效率与质量。 | I started in the Photoshop era of UI design and grew into a UI/UX designer whose primary tool is Figma — combining front-end knowledge with prototyping tools to help teams ship products. In the AI era, I keep learning and use AI tools like Figma MCP and Harness Agent with diverse AI models to improve design efficiency and quality. |


> 技能区是**图标卡 + 熟练度星级**，数据在 `index.html` 的 **`SKILLS` 数组**：每条 `{ name:{zh,en}, level:1–5, icon:"data:image/svg+xml;base64,…" }`。
> - `level` 为熟练度（1–5 星）。
> - `icon` 为 `portfolio/assets/Skill-*.svg`（Figma / XD / PS / Ai / Axure / CSS 六个圆形徽章图标）。
> 新增技能：复制一条并给出 `name / level / icon` 即可（把图标 PNG 放入 `assets/`，`icon` 写相对路径）。

[技能熟练度对照]
| 技能 | 星级 |
|---|---|
| Figma | 4 / 5 |
| Adobe XD | 4 / 5 |
| Photoshop | 4 / 5 |
| Illustrator | 3 / 5 |
| Axure | 3 / 5 |
| CSS3 | 3 / 5 |

### 1.5 工作经验（Work Experience）
| key | 中文 | 英文 |
|---|---|---|
| nav.exp | 履历 | Resume |
| exp.eyebrow | 履历 | Resume |
| exp.title | 工作经验 | Work Experience |


> 时间线内容在 `index.html` 的 **`EXPERIENCE` 数组**里，每条含 `period / company / role / points`（均为 `{zh, en}`）。
> 新增一段经历：往 `EXPERIENCE` 数组 push 一条即可，`points` 为要点数组（每条 `{zh, en}`）。

```js
{
  period:  { zh:"2016.10 – 至今", en:"2016.10 – Present" },
  company: { zh:"公司名", en:"Company Name" },
  role:    { zh:"职位", en:"Role" },
  points:  [ { zh:"要点中文", en:"Point in English" } ]
}
```

### 1.6 作品（Portfolio）
| key | 中文 | 英文 |
|---|---|---|
| portfolio.eyebrow | 精选作品 | Selected Work |
| portfolio.title | 作品 | Portfolio |
| portfolio.desc | 一组代表性项目。在下方 PROJECTS 数组中追加即可持续收录新作品。 | A collection of representative projects. Append to the PROJECTS array below to publish more. |

### 1.7 联系（Contact）
| key | 中文 | 英文 |
|---|---|---|
| contact.title | 联系我 | Contact me |
| contact.desc | 如果你有设计系统、B2B 产品或 AI 产品的挑战，欢迎与我聊合作、机会与新想法。 | Have a design system, B2B product, or AI product challenge? Let's talk about collaboration, opportunities, and new ideas. |
| form.name | 姓名 | Name |
| form.namePh | 你的姓名 | Your name |
| form.email | 邮箱 | Email |
| form.emailPh | you@example.com | you@example.com |
| form.message | 留言 | Message |
| form.messagePh | 在这里输入你的留言 | Type your message here |
| form.submit | 联系 | Contact |
| footer | © 2026 魏彤 · 由我设计与构建 | © 2026 Vista Wei · Designed & built by me |
| footer.resume | 查看简历 | View resume |

---

## 2. 新增/更新作品的模板

在 `PROJECTS` 数组里加一条（`title` / `sub` 都给 `zh` 和 `en`）：

```js
{
  title: { zh:"作品中文名", en:"Project Name" },
  sub:   { zh:"分类 · 公司 · 年份", en:"Category · Company · 2026" },
  href:  "projects/xxx/index.html",        // 案例详情页链接
  cover: "assets/projects/xxx-cover.png",  // 封面图(4:3)
  // 若还没完成，改成空 case 且加 soon:true
}
```

- 每个作品建议做成独立的案例详情页（结构：Hero → 背景 → 我的角色 → 过程 → 交付 → 数据 → 反思）。
- 封面图放进 `assets/projects/`，尺寸建议宽 ≥1200、4:3。

---

## 3. 更新流程（Copy → English）

1. **先改 `zh`**：在 `I18N.zh` 里更新对应中文文案。
2. **再同步 `en`**：在 `I18N.en` 里按相同 `key` 更新英文，确保语义一致。
3. 若新增字段：在 `zh` 和 `en` **同时**加同名的 `key`，并在 HTML 里加 `data-i18n="key"`（或 `data-ph="key"` 用于占位符）。
4. 涉及作品：更新 `PROJECTS` 数组的 `title/sub`、`href`、`cover`。
5. 重新生成单文件版（如需）。

> 提示：`data-i18n` 负责文本，`data-ph` 负责 `<input>/<textarea>` 的占位符；两者都要在 `zh`/`en` 里补全，否则切语言会留空。
