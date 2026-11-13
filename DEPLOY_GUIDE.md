# GitHub Pages 发布与排查指南

### 路线 A：网页直接上传

1. 创建新的 GitHub 仓库，推荐公开仓库，默认分支 `main`。
2. 打开仓库的 **Add file → Upload files**。
3. 上传解压后的文件，确保仓库最外层就能看到 `index.html`（不是 `EpikHigh_v13_GitHub_Pages/index.html`）。
4. 提交文件。
5. **Settings → Pages**：Source 选择 **Deploy from a branch**；选择 **main**、**/(root)**，保存。
6. GitHub Pages 完成构建后，打开类似 `https://USERNAME.github.io/REPO/` 的网址。

### 路线 B：使用 Git 命令（可选）

```bash
git init
git add .
git commit -m "Publish Epik High music archive v13"
git branch -M main
git remote add origin https://github.com/USERNAME/REPO.git
git push -u origin main
```

然后按路线 A 的第 5–6 步在仓库 Settings 中打开 GitHub Pages。

### 常见问题

**404 / 空白页**：检查文件名确实是 `index.html`、位于仓库根目录，Pages 分支选的是 `main` 和 `/(root)`。发布有短暂构建延迟，可在仓库 Actions / Pages 查看状态。

**GitHub Pages 地址不对**：一般为 `https://USERNAME.github.io/REPO/`；用户主页仓库 `USERNAME.github.io` 才是根域地址。

**图片不显示**：本项目有些图片由外部平台提供，需联网；域名或平台可能限制外链。请逐条检查图片来源与授权，必要时更换为获得许可的素材。

**文件上传后仍是旧内容**：确认新 `index.html` 已提交，清理页面缓存或强制刷新，检查 Pages 部署完成。

**保存的收藏/打卡不见了**：`localStorage` 按域名隔离，从本地文件迁移到 GitHub Pages 是新域名。用户保存的数据不会自动跟随代码迁移。

**资料粘贴可以、自动抓网页失败**：属于浏览器跨域及第三方代理限制，不是 GitHub Pages 自动具备的数据抓取能力。

**打算加入共享评论或在线资料库？** 当前是纯前端静态站，需要额外接入合适的后端 / 数据库与权限控制，GitHub Pages 本身不提供写入型数据库。

### 上线前检查

- [ ] 手机竖屏可以打开首页和底部导航
- [ ] 日历日期与韩国当地时间符合预期
- [ ] 档案库搜索、筛选和来源链接可用
- [ ] 历史歌单与 2027 年官方未公布的歌单没有混淆
- [ ] 资料导入后本机刷新仍能读取
- [ ] 已核查有待核验标记的历史条目及发布素材权限
- [ ] 已实际测试一次其他手机/无痕窗口打开公开网址
