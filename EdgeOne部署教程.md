# EdgeOne Pages 部署教程（隐藏你的名字）

> 目标：把「相亲帮帮」H5 部署到腾讯 EdgeOne，得到一个**不带你名字**的链接：
> `https://hangzhou-xiangqinbangbang.edgeone.site`
>
> 优势：国内访问飞快（腾讯 CDN），免费，绑定 GitHub 后改代码能自动更新。

---

## 第一步：注册登录

1. 浏览器打开：**https://edgeone.ai/pages**
2. 点右上角「登录 / 注册」
3. 用**微信扫码**登录（最方便），或邮箱注册腾讯云账号
4. 登录成功后进入 EdgeOne 控制台

## 第二步：创建项目（导入 GitHub 仓库）

1. 首次进入会看到「场景选择大厅」，鼠标移到 **「创建项目」**
2. 选择 **「通过导入 Git 仓库创建」**
3. 页面出现 Git 提供商，点 **「GitHub」**

## 第三步：授权 GitHub（关键一步）

1. 会弹到 GitHub 授权页，点绿色按钮 **「Authorize EO Makers」**
2. 选择仓库权限：
   - 推荐选 **「Only select repositories」**（只选 `xiangqinbangbang`）
   - 或者图省事选「All repositories」也行
3. 点 **「Install」** 完成授权
4. 自动跳回 EdgeOne，下拉选择你的仓库 **`xiangqinbangbang`**

## 第四步：填配置（重点看这里）

| 配置项 | 怎么填 |
|---|---|
| **项目名称** | `hangzhou-xiangqinbangbang`（**这个就是你的链接前缀**） |
| **框架预设** | 选「其他 / Other」（纯静态 HTML，不需要框架） |
| **构建命令 Build command** | **留空**（这是纯 HTML，不用编译） |
| **输出目录 Output directory** | 留空，或填 `.`（根目录） |
| **加速区域** | 选「全球」或「中国大陆」 |

> ⚠️ 这个项目是**纯静态 HTML**，没有 package.json、没有构建脚本，所以构建命令一定要留空，否则会报错。

## 第五步：部署

1. 检查配置无误，点 **「开始部署」**
2. 等待 1-2 分钟，看到「部署成功」的提示
3. 部署完成后，页面上会有**预览链接**（格式 `xxx.edgeone.site`）

## 第六步：拿到链接

- 在「项目概览」或「构建部署」页面右上角，点 **「预览」** 或查看域名
- 默认域名就是：**`https://hangzhou-xiangqinbangbang.edgeone.site`**
- 把这个链接发我，我帮你验证能不能正常打开

---

## 常见问题

**Q1：免费域名后缀到底是什么？**
EdgeOne 的免费默认域名后缀是 `edgeone.site`，所以你的项目会得到 `hangzhou-xiangqinbangbang.edgeone.site`。

**Q2：需要备案吗？**
用 EdgeOne 自带的 `edgeone.site` 免费域名**不需要备案**，部署完就能访问。

**Q3：以后改了代码怎么办？**
因为绑定了 GitHub 仓库，以后你（或我）往仓库推新代码，EdgeOne 会**自动重新部署**，1-2 分钟生效。这是「导入 Git 仓库」方式比「直接上传」更好的地方。

**Q4：能自己买域名吗？**
以后如果买自己的域名（比如 `xxx.com`），可以在 EdgeOne 的「域名管理」里绑定自定义域名。那时就需要备案了（国内服务器要求）。

---

## 备选：如果不想授权 GitHub

EdgeOne 还支持「直接上传」方式，不用授权 GitHub，把 `相亲帮帮.html` 文件拖进去就能部署。缺点是以后改代码要手动重新上传。适合想最快上线、不折腾 GitHub 授权的情况。
