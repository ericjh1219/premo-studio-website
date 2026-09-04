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
- 毕业袍款式一览，展示 JB 分店现有的全部毕业袍款式（graduation-gowns.html，从毕业照页面可以点进去）
- 关于我们 / 门店资讯，含奖项、曾服务客户 logo 墙、KL/JB 门店实景照（about.html）
- Blog 文章总览页（blog.html）
- 常见问题 FAQ 总览页（faq.html）— 护照/签证照片、毕业照、全家福、专业形象照、一般问题共 5 大类、40+ 题问答

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
- `real-headshot-male.jpg` / `real-headshot-female.jpg` — 真实客户形象照成果（KL/JB 形象照页主视觉共用）
- `real-headshot-corporate-group.jpg` — 真实企业团体形象照成果（用于 Blog「谁需要专业形象照」文章）
- `real-passport-male.jpg` / `real-passport-child.jpg` — 真实客户护照照片成果（KL/JB 护照照片页共用）
- `blog-illus-*.jpg`（共 7 张）— **AI 生成／网络示意图**，仅用于 7 篇 Blog 文章插图，页面上都清楚标注「示意图，非实际拍摄成果」，绝不会当作真实拍摄成果展示

## 这次更新的重点

- **修复导航问题**：Passport Photo、Headshot、Graduation、Family Portrait 现在每个都有独立的 KL 和 JB 页面（之前 Passport 只有 KL、Headshot 只有 JB、毕业照和全家福是 KL/JB 合并成一页），并且每个服务页都有自己的地址、营业时间、JSON-LD 结构化资料，方便 Google 与 AI（ChatGPT 等）清楚辨认这是哪个分店的页面。
- **导航改成下拉选单**：4 个服务变成下拉选单，滑鼠移上去会显示 KL / JB 两个选项，不再像之前那样一排挤十几个连结。
- **加入了 8 张你提供的真实客户照片**（护照照片 2 张、毕业照 2 张、全家福 2 张、形象照 2 张），放在对应服务页的主视觉区，KL 与 JB 页面共用同一批真实照片（你确认过不需要分店分开放）。
- **修正了照片显示方式**：主视觉区的真实照片原本套用圆形裁切样式，会裁掉照片的大部分内容，只剩中间一小圈看得到；后来又调整成完全按照片原始比例显示（不裁切、不套用固定设计尺寸），照片是什么形状就显示什么形状，长方形照片也不会被硬挤成方形。
- **形象照右边的照片换成女生**：原本 KL/JB 形象照页右边放的是企业团体照，现在换成一张真实女性客户的形象照成果（企业团体照改放到 Blog「谁需要专业形象照」文章，那边继续使用）。
- **毕业照、全家福的主视觉照片放大**：调整了版面比例，让这两个服务的照片明显比之前大。
- **Blog 文章里的插图不再被裁切**：之前几篇文章（影棚 vs 户外、学校 vs 专业影棚、为什么毕业照重要、穿搭指南、价格指南、形象照准备清单、男生化妆、谁需要专业形象照）的插图套用了固定高度会裁掉图片上下部分，现在改成按图片原始比例完整显示。
- **首页主视觉补上真实照片**：首页原本也是空的圆形占位符，现在放上真实客户照片，一样是完整显示、不裁切、放大处理。
- **新增「毕业袍款式一览」独立页面**：原本毕业袍照片只是小小一张嵌在毕业照页面里，现在做成独立页面（graduation-gowns.html），把图片放大完整呈现，并额外列出所有款式的文字清单方便浏览与搜索引擎收录；KL/JB 毕业照页面则改成一段简短介绍 + 「查看全部毕业袍款式」按钮连过去。
- **补上关于我们（About Us）的品牌故事**：about.html「我们的故事」原本是空的占位文字，现在换成你提供的完整中英文品牌故事；首页「关于 Premo Studio」区块也同步更新，拿掉了原本橙色标示的「此处补上品牌故事」提示文字。
- **Blog 插图**：你附上的 8 张图片中，7 张确认是 AI 生成／网络示意图，已分别放到 7 篇相关 Blog 文章（影棚 vs 户外、学校 vs 专业影棚、为什么毕业照重要、穿搭指南、价格指南、形象照准备清单、男生形象照化妆）当装饰插图，并诚实标注「示意图，非实际拍摄成果」，不会误导成真实拍摄成果。第 8 张（全家福风格的米色横幅图）目前没有合适的文章可以放，先没有使用——如果你想指定放在哪里，跟我说一声。
- **修正了一个之前的问题**：毕业照页面原本有一组套餐价格表（RM50-100 / RM150-300 / RM300-600+），但这些数字并不是你提供的真实资料，已经改成诚实的「价格请以预约时门店最新公告为准」提示，避免网站上出现没有根据的价格误导客户。
- **JSON-LD、内部连结、图片路径、sitemap.xml 都已经重新检查过一轮**，没有失效连结或缺失图片。

## 这次更新（第二轮）

- **首页主视觉改成 3 张照片**：换成你提供的三张真实照片（造型概念团体照、个人形象写真、全家福），排版改成「上方一张大图 + 下方两张并排」。
- **「立即预约」按钮改连去 minibookit**：全站所有写着「立即预约」的按钮（首页、各服务页主视觉、每个页面的页尾，共 22 个页面 31 个按钮）现在会直接打开 `https://premostudio.minibookit.com/`；写着「WhatsApp 预约」「WhatsApp 询问」的按钮（导航栏、部分次要按钮）维持连去 WhatsApp，没有更动。如果你希望全部按钮都改成 minibookit（连 WhatsApp 按钮也换掉），跟我说一声即可。
- **KL 护照照片页的真实成果对比图换新**：原本三张分开的男 / 女 / 童对比照，换成你提供的新版整合对比图（男生 / 女生 / 儿童护照照片，修图前后对比）。
- **毕业袍款式补上大学 logo**：9 款毕业袍中，Sunway University、Curtin University、Newcastle University、University of London 这 4 款已经放上真实校徽（从你之前提供的毕业袍照片里截取）。**MMU、Raffles、NUS、SIM、UTM 这 5 款目前还是文字**——因为我这边没有办法直接连到网络下载图片，找不到这 5 所学校的官方 logo 图档，如果你可以传这 5 个 logo 的图片给我（或截图也可以），我可以补上。
- **JSON-LD、内部连结、图片路径、sitemap.xml 已重新检查过一轮**，没有失效连结或缺失图片。

## 这次更新（第三轮）

- **新增「常见问题 FAQ」独立页面**（faq.html）：把你提供的完整问答整理成 5 大类——护照/签证证件照、毕业照、全家福、专业形象照/职业头像、一般摄影问题，共 40+ 题，全部中英对照。页面顶部有分类快速跳转按钮，也加上了 FAQPage 结构化资料，方便 Google 与 AI 直接抓取回答。
- **全站导航栏加上「FAQ」连结**（22 个页面都加了，在 Blog 和 About 中间）。
- **sitemap.xml 加入 faq.html**。
- 有两个小地方我做了判断，跟你确认一下：毕业照 FAQ 那题（有提供毕业袍吗）我加了一个连去「毕业袍款式一览」页面的连结，方便顾客直接查看实际款式；另外你原文里形象照那题「多久可以收到照片」下面写的备注（提到 24 小时交付 SLA）看起来是你写给我的说明而不是要放上网站的文案，所以我没有直接搬到 FAQ 上——如果 24 小时交付真的是你们形象照 Softcopy 的正式政策，可以告诉我，我直接把这句加进 FAQ 和形象照页面。

## 这次更新（第四轮）

- **「毕业袍款式一览」页面大幅扩充**：你补传的 7 张毕业袍实拍照片，我整理成完整版放上页面，不再裁切、也不缩成小图标——现在完整呈现以下所有学校 / 学院的真实照片：
  - Sunway University、Curtin University、Newcastle University、University of London、Murdoch University（+ MMU、Raffles、NUS、SIM、UTM）
  - Monash University（White／Grey／Pink／Red／Orange／Yellow／Purple／L. Blue／D. Blue 等披肩颜色，另有 Pharmacy／Art／Business & Economics 学院款式）
  - THE ONE ACADEMY、TARC 拉曼大学学院（Business Accounting／Science Information System & Engineering／Hospitality Hotel Management／Event Management 等学院款式）
  - UTAR 拉曼大学、INTI International University & Colleges（各学院披肩颜色）
  - Universiti Malaya 马来亚大学（13 个学院披肩颜色，从 Creative Arts 到 Medicine、Dentistry）
- 页面下方保留一份完整学校 / 学院文字清单，方便浏览与搜索引擎收录。原本 9 格文字 / 局部 logo 的小格子已经拿掉，改成这批完整实拍照片。
- 你重复传了一张「Sunway + Newcastle + MMU/SIM/UTM」的较小版本（只有部分学校、没有 Curtin/UoL/Murdoch/Raffles/NUS），内容已经完整包含在第一张大图里，所以这张没有另外放上去，避免重复；如果这张其实是要给我看不同的东西，请告诉我。
- JSON-LD、内部连结、图片路径、sitemap.xml 已重新检查过一轮，没有问题。

## 这次更新（第五轮）

- **新增「作品集 Portfolio」独立页面**（portfolio.html）：从你新提供的 Family / Graduation / Headshot / Passport 四个资料夹（共 60+ 张真实客户照片）里，我逐张查看后挑选出 41 张放上网站，全部**按原始比例完整显示、完全没有裁切**，分成四个分类展示：
  - 📸 护照 / 签证证件照（13 张）——刻意挑了涵盖婴儿、儿童、青少年、成人到银发族，以及不同肤色 / 国籍（含马来西亚护照、NZ 签证、德国护照）的照片，突显「各种年龄与签证类型我们都熟悉」这个卖点。
  - 👔 专业形象照（12 张）——包含个人形象照、编辑风格写真，也放了 2 张公司团队合照（10 人、12 人），方便有团队拍摄需求的客户参考。
  - 🎓 毕业照（8 张）——各种家庭组合、含毛孩入镜的毕业照。
  - 👨‍👩‍👧 全家福（8 张）——四口之家、三代同堂、大家庭等不同组合。
  - 首页也加了一个「看看我们拍过什么」预览区块（6 张精选照），点「查看完整作品集」会连到 portfolio.html。
  - 全站 23 个页面的导航栏都加上「作品集」连结（FAQ 和 About 中间），sitemap.xml 也已更新。
- **有一批照片我看过后没有放上网站，跟你说明一下原因**：Headshot 资料夹里有几张是泳装 / 健身比赛风格（比基尼 + 奖牌）、贴身内衣风格，以及几张袒胸/半裸的时尚编辑风格照片——这些拍得都很好，但考虑到 Premo Studio 网站同时也要给做护照照片、带小孩拍全家福的客户看，这类照片放在同一个作品集页面可能不太搭调，所以我先没有采用。如果你希望我加进去（例如另外做一个「时尚 / 编辑风格作品」分类，跟护照、全家福分开呈现），跟我说一声，我可以另外处理。
- 有 2 张毕业照（`_PMO0085.jpg`、`DSC07063.jpg`）背景中会看到「TAYLOR'S UNIVERSITY」字样的红色证书筒，这是真实客户的真实物品，不是刻意置入，我保留原样没有做任何遮挡处理——如果你希望模糊处理或不使用这两张，告诉我即可。
- JSON-LD、内部连结、图片路径、sitemap.xml 已重新检查过一轮，没有问题；Playwright 视觉检查也确认所有照片都完整显示、没有跑版或裁切。

## 这次更新（第六轮）

- **补上真实 Google 客户评价**：你传的 15 张 Google Review 截图（Family / Graduation / Headshot 各 5 张），我逐张读取文字内容后，把其中 14 条有效评价（1 条只有服务标签、没有文字内容，没有采用）填进网站原本预留的「客户评价」区块：
  - `family-portrait-kl.html`、`family-portrait-jb.html`：原本是「暂无评价」的提示文字，现在补上 5 条全家福真实评价。
  - `graduation-photo-kl.html`、`graduation-photo-jb.html`：补上 5 条毕业照真实评价。
  - `headshot-kl.html`、`headshot-jb.html`：补上 4 条形象照真实评价。
  - 首页新增一个「顾客怎么说」区块，从三个分类各挑一条代表性评价。
  - `passport-photo-jb.html` 原本也有 3 个空的评价占位格——这次传来的 Google Review 截图里没有护照照片相关的评价，所以这三格暂时保留原样没有更动；如果你有新山分店护照照片的评价截图，之后可以补上。
  - 评价内容与顾客显示名称都是 Google 上公开显示的原文，直接引用；有 1 位顾客（"RUIXUAN"）留的评价内容其实是「房地产摄影 Real estate photography」，跟 Premo 目前网站服务无关，也没有采用。
- JSON-LD、内部连结、图片路径、sitemap.xml 已重新检查过一轮，没有问题。

## 这次更新（第七轮）

- **全家福页面「造型与穿搭建议」区块补上配图**：你提供的这张全家福示意图（协调米白色系穿搭）放到了 `family-portrait-kl.html` 与 `family-portrait-jb.html` 的「造型与穿搭建议」区块右侧，左文右图排版，图片完整显示不裁切。
- 这张图片经确认是网络示意图／AI 生成的参考图，不是 Premo Studio 实际拍摄成果，所以图片下方按照全站一致的做法标注了「示意图，非实际拍摄成果」，避免误导顾客。

## 这次更新（第八轮）— GEO / AEO（让 AI 更容易推荐你）

用你提供的真实 Google Business Profile 截图、Google Maps 连结、Facebook 与 Instagram 连结，把网站结构化数据（schema）和可见文字里几个不准确或空缺的地方补齐、修正：

- **地理坐标（geo coordinates）**：从你给的两个 Google Maps 连结解析出精确经纬度，加进 KL（3.0841105, 101.6775889）与 JB（1.5472836, 103.7813944）两间分店在全部 10 个页面（8 个服务页 + 首页 + About）的结构化数据里。这能帮助 AI 与地图更准确判断你的分店实际位置，是「附近哪里可以拍护照照片／形象照」这类在地搜索的重要信号。
- **社群连结（sameAs）**：结构化数据里原本是空的 `sameAs` 栏位，现在补上真实的 Facebook 与 Instagram 连结——形象照相关页面用 `@STUDIOPREMO` / `@premo_studio`，毕业照与全家福相关页面用 `@3ric.photography` / `@3ric_photography`，首页与 About 页则把两组都列出来。这是 AI 判断「这是不是真实、活跃的商家」的重要依据。
- **网站底部新增可点击的社群连结**：之前网站上其实完全没有 Facebook / Instagram 的连结（只有结构化数据里有，访客看不到），现在每一页的页尾都加上了这四个可点击的连结。
- **修正评价数字的落差**：你这次传来的 Google Business Profile 截图显示 KL 分店是 5.0★ 130 则评价，JB 分店是 4.9★ 326 则评价。网站之前 KL 相关页面写的是「500+ 评价」（推测是旧的估计值，不是真实数字），这次已经全部改成真实的「130+」；JB 相关页面（`headshot-jb.html`、`passport-photo-jb.html` 的统计卡，以及所有 JB 服务页与首页/About 的结构化数据）也补上真实的「4.9★ 326+」。`about.html` 因为涵盖两间分店，改成两间分店合计的「4.9★ 450+」。
- **`passport-photo-jb.html` 原本 3 格「[请填入]」的占位数字**，已经用真实的 Google 评价数字（4.9★ / 326+）补上其中一格；「服务顾客人数」跟「营运年数」这两格因为这次没有相关数字，先换成「2 间分店」跟「10+ 年经验」（跟其他页面一致的真实数字），避免继续挂着未填的占位文字。
- JSON-LD、内部连结、图片路径、sitemap.xml 已重新检查过一轮，没有问题；也用 Playwright 截图确认了页尾的社群连结与统计数字显示正常。

**这些是网站「站内」能做的部分。** AI 推荐你的公司，更大程度取决于「站外」信号——Google Business Profile 的完整度与活跃度（照片、问答、按时回复评价）、其他平台或网络上别人对 Premo Studio 的真实提及。这部分我没办法帮你操作（需要你自己登入 Google Business Profile 后台），但如果需要，我可以列一份具体的检查清单给你参考。

## 这次更新（第九轮）

- `passport-photo-jb.html` 原本 3 格空白的顾客评价占位文字，改成跟 `passport-photo-kl.html` 一样的 4 条真实客户评价（Lee Lip Yan、Yinhui Lim、Penny Ho、Ashley T.）。提醒一下：这 4 条评价原本是 KL 分店 Google 上的真实评价，这次是直接沿用到 JB 页面，并不是新山分店独立收到的评价——如果之后你有新山分店自己的护照照片顾客评价，建议换成新山专属的评价，会更准确。
- JSON-LD、内部连结、图片路径已重新检查，没有问题。

## 这次更新（第十轮）— 毕业照 SEO / AEO / GEO 全面加强

这次的目标：把「毕业照」这个服务的 SEO/AEO/GEO 强度做到跟「护照照片」一样强，同时不制造重复页面、不堆砌关键字、不编造任何数据。

**网址部分：** 检查过现有网站结构后，`graduation-photo-kl.html` 和 `graduation-photo-jb.html` 本来就是毕业照这两个搜索意图（KL / JB）唯一的对应页面，没有重复或冲突的网址，所以维持原本的网址不变——没有改成 `/kl-graduation-photo` 这种新网址。这是刻意的决定：网站目前用的是纯 GitHub Pages（没有服务器端 301 转址功能），改网址只会需要用比较不可靠的「网页转址」手法，反而增加风险，对已有的 Google 收录也没有好处。

**KL / JB 毕业照页面大幅强化**（内容全部来自网站原有的真实资料，没有新增任何编造的数字、价格、合作或奖项）：
- Above-the-fold 说明清楚：PREMO Studio、吉隆坡／新山、影棚或校园户外、专业打光、摄影师全程指导姿势、自然修图、个人／家人／团体照都能拍、拍摄后即可预览（这条来自真实顾客评价 Jaclyn Gan 的原文）。
- 新增「为什么选择 PREMO」区块：4 个真实卖点（专业打光、摄影师指导姿势、多种合照组合、自然修图）。
- 新增「毕业照实拍作品」小型作品集（4 张真实客户毕业照，取自你原有的作品集图片，KL 和 JB 两页用了不同的照片组合，避免完全重复）。
- 新增「毕业照可以拍哪些组合」AEO 区块：个人独照、毕业＋家人、毕业＋朋友、毕业＋伴侣、毕业＋宠物、证书照、学士服写真、正式／轻松风格——全部都是网站 FAQ 页面原本就承诺提供的真实服务项目。
- 新增「拍摄流程」7 个步骤说明。
- 毕业袍区块保留并加强：现场超过 15 所大学的真实毕业袍库存（来自你现有的 `graduation-gowns.html` 页面数据）。
- 穿搭建议区块，附完整穿搭指南连结。
- Graduation Photography FAQ 从原本的 3 条扩充到 9 条真实问答（摆姿势、团拍、家人、宠物、毕业袍、自备服装、交件时间、周末预约、毕业季），内容取自网站 `faq.html` 页面原本就有的真实答案。
- 新增「延伸阅读」区块，串联全部 5 篇毕业照指南文章 + 毕业袍页面。
- Schema 新增 `Service`、`BreadcrumbList`，`FAQPage` 扩充到 9 条，与页面上显示的 FAQ 内容一致。
- 新增一段关于吉隆坡／新山周边真实大学的自然语句：KL 页面提到 Universiti Malaya、Sunway、Monash、UTAR、INTI、MMU（都是现有毕业袍库存里真实备有的学校）；JB 页面则提到 NUS、SIM（新加坡院校，因为新山邻近新加坡）与 UTM（新山士古来的大学）——这些都只是「我们备有你学校的毕业袍」这个真实事实，没有声称任何官方合作关系。
- **JB 页面刻意维持约 70% 与 KL 页面相同的服务说明架构，30% 换成新山本地内容**（新山 Mount Austin 地址、不同的真实作品照片、新加坡邻近院校毕业袍），避免变成单纯复制 KL 页面的「doorway page」。
- 5 篇毕业照指南文章（穿搭指南、价格指南、影棚 vs 户外、学校 vs 影棚、为什么毕业照重要）以及毕业袍页面，原本文末只连回 KL 页面，这次都加上了 JB 页面的连结，以及连回 FAQ 页面毕业照区块的连结，让整个「毕业照」主题的内部连结形成完整的网络。
- 首页「我们的服务」区块的 4 个服务名称改成更完整的说法：Passport & Visa Photography、Professional Headshots、Graduation Photography、Family Portraits（原本是较简短的 Passport Photo、Headshot 等）。
- JSON-LD、内部连结、图片路径、sitemap.xml 已重新检查过，没有问题；也用 Playwright 完整截图确认 KL 和 JB 两个页面在各个区块都正常显示。
