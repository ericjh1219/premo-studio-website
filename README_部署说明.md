# Premo Studio 新网站 — 部署说明（不需要写代码）

这个资料夹里的文件就是完整的网站（首页 + 4 大服务 × KL/JB 共 8 个服务页 + About + Blog 共 11 大页，另外还有 10 篇 Blog 文章）。你已经有 GitHub 帐号了，所以**完全不需要再另外注册 Cloudflare 或任何其他服务**——GitHub 自己就有免费的网站托管功能（叫 GitHub Pages），全程只用一个帐号，一毛钱都不用付。

## 第一步：把文件放上 GitHub（约 5 分钟）

1. 登入你的 GitHub 帐号，点右上角 **+** → **New repository**
2. Repository name 填 `premo-studio-website`（或你喜欢的名字），**必须设成 Public**（GitHub Pages 免费版只支援公开的 repository），直接按 **Create repository**
3. 建好之后，页面上会有 **uploading an existing file** 的连结，点进去
4. 把这个资料夹里**全部的文件跟资料夹**（所有 `.html` 文件、`style.css`、`robots.txt`、`sitemap.xml`，以及整个 `assets` 资料夹——里面是你的品牌 logo、获奖图片、客户 logo、门店照片、客户成果照片）直接拖拉进网页上传区。GitHub 会自动保留资料夹结构，不用担心。
5. 拉到最下面，按绿色的 **Commit changes**

## 第二步：打开 GitHub Pages（免费，1 分钟，不用再注册任何东西）

1. 在这个 repository 页面，点上面的 **Settings**
2. 左边选单点 **Pages**
3. 在 **Build and deployment** → **Source**，选 **Deploy from a branch**
4. Branch 选 **main**，资料夹选 **/ (root)**，按 **Save**
5. 等大概 1 分钟，**回到这个 Pages 页面最上面**会出现一个绿色框，写着网址，类似 `https://你的帐号.github.io/premo-studio-website/`——打开看看是不是跟设计稿一样（如果还没出现，刷新页面等一下）

## 第三步：把 premostudio.my 域名指过来（等你确认新网站没问题再做）

1. 还是在 **Settings → Pages**，找到 **Custom domain** 栏位，输入 `premostudio.my`，按 **Save**
2. GitHub 会告诉你需要在域名的 DNS 设置里加几条纪录（通常是几条 A 记录指向 GitHub 的服务器 IP，加一条 CNAME）
3. 去你当初买 `premostudio.my` 这个域名的地方（如果是透过 Wix 买的，就在 Wix 的 Domains 设置里；如果是另外的注册商，就登入那边）把这几条纪录加上去
4. DNS 生效通常几分钟到几小时不等，生效后 premostudio.my 就会显示新网站，Wix 那边可以之后再考虑要不要保留或取消

## 之后要改内容怎么办？

把改好的文件传给我或直接问我，我改好后你只要回到 GitHub 那个 repository，把新版本的文件重新拖拉上传（一样 Commit changes）就好——GitHub Pages 会自动侦测到更新，几十秒到几分钟内就重新上线，不需要重新设置任何东西，也不需要再碰 Settings。

## 目前所有页面

**主要页面**（4 大服务，每个都拆成独立的 KL / JB 页面，方便 Google／AI 清楚辨认地点）
- 首页（index.html）— 含获奖记录、Headshot Portrait 主打
- KL 护照照片（passport-photo-kl.html）— 含真实客户评价与真实拍摄成果对比照
- JB 护照照片（passport-photo-jb.html）
- KL 形象照（headshot-kl.html）
- JB 形象照（headshot-jb.html）
- KL 毕业照（graduation-photo-kl.html）
- JB 毕业照（graduation-photo-jb.html）
- KL 全家福（family-portrait-kl.html）
- JB 全家福（family-portrait-jb.html）
- 关于我们 / 门店资讯，含奖项、曾服务客户 logo 墙、KL/JB 门店实景照（about.html）
- Blog 文章总览页（blog.html）

导航栏现在是**每个服务一个下拉选单**（滑鼠移到 Passport Photo / Headshot / Graduation / Family Portrait 上会跳出 KL 吉隆坡 / JB 新山 两个选项），不会再挤成一排。

**Blog 文章（毕业照小贴士 5 篇）**
- 毕业照价格指南（graduation-photo-cost-guide.html）
- 影棚 vs 户外拍摄（graduation-studio-vs-outdoor.html）
- 为什么毕业照重要（why-graduation-photos-matter.html）
- 学校 vs 专业影棚（graduation-studio-vs-school.html）
- 毕业照穿搭指南（graduation-outfit-guide.html）

**Blog 文章（形象照小贴士 5 篇）**
- 形象照价格指南（headshot-cost-guide.html）
- RM99 vs RM299 形象照（headshot-99-vs-299.html）
- 男生形象照需要化妆吗（headshot-makeup-for-men.html）
- 形象照拍摄前准备清单（headshot-preparation-checklist.html）
- 谁需要专业形象照（who-needs-a-headshot.html）

## assets 资料夹说明

- `logo-mark.png` / `favicon.png` — 品牌 logo 与网站图标（取自你提供的真实 logo）
- `awards-strip.png` — 真实获奖记录（Consumer Choice Award、WPPI Silver Award 2015 等）
- `clients-grid.png` — 曾服务客户 logo 墙（约 20 个真实客户）
- `usana-logo.png` — USANA 客户真实 logo（用于 about.html 客户墙）
- `store-kl.jpg` / `store-jb.jpg` — KL / JB 门店实景照
- `results-male.jpg` / `results-female.jpg` / `results-child.jpg` — 真实客户拍摄成果对比照（用于 KL 护照照片页）
- `pricing-headshot-male.jpg` / `pricing-headshot-female.jpg` / `pricing-headshot-express.png` — 真实形象照价格图（用于 headshot-jb.html 与相关 Blog 文章）
- `pricing-passport-49.png` / `pricing-passport-59.png` — 真实护照照片价格图（用于 KL/JB 护照照片页）
- `pricing-family-packages.png` — 真实全家福套餐价格表（用于 family-portrait-kl.html / family-portrait-jb.html）
- `gown-jb.png` — JB 分店真实毕业袍款式参考照（用于毕业照页面）
- `real-graduation-couple.jpg` / `real-graduation-family.jpg` — 真实客户毕业照成果（KL/JB 毕业照页共用）
- `real-family-group.jpg` / `real-family-fun.jpg` — 真实客户全家福成果（KL/JB 全家福页共用）
- `real-headshot-male.jpg` / `real-headshot-corporate-group.jpg` — 真实客户形象照成果（KL/JB 形象照页共用，企业团体照也用在 Blog「谁需要专业形象照」文章）
- `blog-illus-*.jpg`（共 7 张）— **AI 生成／网络示意图**，仅用于 7 篇 Blog 文章插图，页面上都清楚标注「示意图，非实际拍摄成果」，绝不会当作真实拍摄成果展示

## 这次更新的重点

- **修复导航问题**：Passport Photo、Headshot、Graduation、Family Portrait 现在每个都有独立的 KL 和 JB 页面（之前 Passport 只有 KL、Headshot 只有 JB、毕业照和全家福是 KL/JB 合并成一页），并且每个服务页都有自己的地址、营业时间、JSON-LD 结构化资料，方便 Google 与 AI（ChatGPT 等）清楚辨认这是哪个分店的页面。
- **导航改成下拉选单**：4 个服务变成下拉选单，滑鼠移上去会显示 KL / JB 两个选项，不再像之前那样一排挤十几个连结。
- **加入了 6 张你 Google Drive 里的真实客户照片**（毕业照 2 张、全家福 2 张、形象照 2 张），放在对应服务页的主视觉区，KL 与 JB 页面共用同一批真实照片（你确认过不需要分店分开放）。
- **Blog 插图**：你附上的 8 张图片中，7 张确认是 AI 生成／网络示意图，已分别放到 7 篇相关 Blog 文章（影棚 vs 户外、学校 vs 专业影棚、为什么毕业照重要、穿搭指南、价格指南、形象照准备清单、男生形象照化妆）当装饰插图，并诚实标注「示意图，非实际拍摄成果」，不会误导成真实拍摄成果。第 8 张（全家福风格的米色横幅图）目前没有合适的文章可以放，先没有使用——如果你想指定放在哪里，跟我说一声。
- **修正了一个之前的问题**：毕业照页面原本有一组套餐价格表（RM50-100 / RM150-300 / RM300-600+），但这些数字并不是你提供的真实资料，已经改成诚实的「价格请以预约时门店最新公告为准」提示，避免网站上出现没有根据的价格误导客户。
- **JSON-LD、内部连结、图片路径、sitemap.xml 都已经重新检查过一轮**，没有失效连结或缺失图片。

**建议**：现在所有主要页面与 Blog 文章都已经完成，接下来可以先把网站完整上线到 GitHub Pages 的临时网址测试一轮，确认每一页都正常，再考虑把 premostudio.my 域名指过来（见第三步）。
