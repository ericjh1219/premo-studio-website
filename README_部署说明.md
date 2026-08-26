# Premo Studio 新网站 — 部署说明（不需要写代码）

这个资料夹里的文件就是完整的网站（首页 + JB/KL 护照照片 + JB 形象照 + 毕业照 + 全家福 + About 共 7 页）。你已经有 GitHub 帐号了，所以**完全不需要再另外注册 Cloudflare 或任何其他服务**——GitHub 自己就有免费的网站托管功能（叫 GitHub Pages），全程只用一个帐号，一毛钱都不用付。

## 第一步：把文件放上 GitHub（约 5 分钟）

1. 登入你的 GitHub 帐号，点右上角 **+** → **New repository**
2. Repository name 填 `premo-studio-website`（或你喜欢的名字），**必须设成 Public**（GitHub Pages 免费版只支援公开的 repository），直接按 **Create repository**
3. 建好之后，页面上会有 **uploading an existing file** 的连结，点进去
4. 把这个资料夹里**全部的文件跟资料夹**（`index.html`、`style.css`、`passport-photo-jb.html`、`passport-photo-kl.html`、`headshot-jb.html`、`graduation-photo.html`、`graduation-photo-cost-guide.html`、`family-portrait.html`、`about.html`、`robots.txt`、`sitemap.xml`，以及整个 `assets` 资料夹——里面是你的品牌 logo、获奖图片、客户 logo）直接拖拉进网页上传区。GitHub 会自动保留资料夹结构，不用担心。
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

- 首页（index.html）
- KL 护照照片（passport-photo-kl.html）
- JB 护照照片（passport-photo-jb.html）
- JB 形象照（headshot-jb.html）
- 毕业照 KL+JB 合并页（graduation-photo.html）
- 毕业照价格指南文章（graduation-photo-cost-guide.html）
- 全家福 KL+JB 合并页（family-portrait.html）
- 关于我们 / 门店资讯，含奖项与客户 logo（about.html）

**建议**：这 7 页都做完了，接下来可以先把网站完整上线到 GitHub Pages 的临时网址测试一轮，确认每一页都正常，再考虑把 premostudio.my 域名指过来（见第三步）。
