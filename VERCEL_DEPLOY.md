# 🚀 Vercel 部署指南

Vercel 是部署前端网站最简单、最快速的平台，支持自动更新和全球 CDN 加速。

## 📋 部署前准备

确保你的项目文件结构如下：

```
login/
├── career-plan/
│   └── index.html       # 职业规划网站
├── portfolio/
│   └── index.html       # 作品集网站
├── index.html           # 根目录重定向页
├── vercel.json          # Vercel 配置文件
├── README.md
└── VERCEL_DEPLOY.md     # 本指南
```

## 🎯 部署步骤（推荐方式：GitHub + Vercel）

### 第一步：上传代码到 GitHub

1. **注册/登录 GitHub**
   - 访问 https://github.com
   - 如果没有账号，点击 "Sign up" 注册

2. **创建新仓库**
   - 点击右上角 `+` → `New repository`
   - Repository name: `gis-portfolio`（或你喜欢的名字）
   - Description: `GIS职业规划与作品集网站`
   - 选择 **Public**（公开）
   - 勾选 **Add a README file**
   - 点击 **Create repository**

3. **上传文件到仓库**

   **方法一：网页上传（最简单）**
   
   a. 进入刚创建的仓库
   b. 点击 **Add file** → **Upload files**
   c. 将你的文件夹拖入上传区域：
      - `career-plan/`
      - `portfolio/`
      - `index.html`（根目录的）
      - `vercel.json`
      - `README.md`
   d. 在 "Commit changes" 处填写描述，如 "Initial upload"
   e. 点击 **Commit changes**

   **方法二：Git 命令行（适合有 Git 基础的用户）**
   
   ```bash
   # 克隆仓库
   git clone https://github.com/你的用户名/gis-portfolio.git
   
   # 进入项目目录
   cd gis-portfolio
   
   # 复制所有文件到此处
   # (将你的 career-plan, portfolio, index.html, vercel.json 复制进来)
   
   # 添加所有文件
   git add .
   
   # 提交
   git commit -m "Initial commit: Add career plan and portfolio websites"
   
   # 推送到 GitHub
   git push origin main
   ```

### 第二步：在 Vercel 上部署

1. **注册/登录 Vercel**
   - 访问 https://vercel.com
   - 点击 **Sign Up**
   - **重要**：选择 **Continue with GitHub** 使用 GitHub 账号登录

2. **导入项目**
   - 登录后会看到 Vercel 仪表板
   - 点击 **Add New Project**（或 "New Project"）
   - 在 "Import Git Repository" 下找到你的 `gis-portfolio` 仓库
   - 点击 **Import**

3. **配置项目**
   - Project Name: 会自动填充，可以不改（如 `gis-portfolio`）
   - Framework Preset: 选择 **Other**（因为是纯 HTML）
   - Root Directory: 保持 `./`（根目录）
   - Build Command: 留空
   - Output Directory: 留空

4. **开始部署**
   - 点击 **Deploy** 按钮
   - 等待 30 秒 - 1 分钟，Vercel 会自动构建和部署
   - 看到 "Congratulations!" 就表示部署成功！🎉

### 第三步：访问你的网站

Vercel 会为你生成一个域名，格式如下：
- 主域名：`https://gis-portfolio-你的用户名.vercel.app`
- 职业规划网站：`https://gis-portfolio-你的用户名.vercel.app/career-plan/`
- 作品集网站：`https://gis-portfolio-你的用户名.vercel.app/portfolio/`

点击 **Visit** 按钮即可查看网站！

## 🌐 配置自定义域名（可选）

如果你想使用自己的域名（如 `yourname.com`）：

1. 在 Vercel 项目页面点击 **Settings** → **Domains**
2. 输入你的域名，点击 **Add**
3. 按照提示在你的域名服务商处添加 DNS 记录
4. 等待 DNS 生效（通常几分钟到几小时）

## 🔄 自动更新

Vercel 的强大之处在于**自动部署**：

- 每当你修改本地文件并 `git push` 到 GitHub
- Vercel 会自动检测到变化并重新部署
- 无需手动操作，网站始终保持最新！

## 📱 更新网站的步骤

以后想要更新网站内容：

```bash
# 1. 修改你的 HTML 文件

# 2. 添加更改
git add .

# 3. 提交更改
git commit -m "更新：添加新项目"

# 4. 推送到 GitHub
git push origin main

# 5. Vercel 会自动重新部署！
```

## ❓ 常见问题

### Q: 部署后网站显示 404？
A: 检查 `vercel.json` 是否正确上传到仓库，或者尝试重新部署。

### Q: 两个网站之间的链接无法跳转？
A: 确保链接使用的是相对路径：
- 从职业规划到作品集：`../portfolio/index.html`
- 从作品集到职业规划：`../career-plan/index.html`

### Q: 如何删除已部署的项目？
A: 在 Vercel 仪表板中，点击项目 → Settings → General → Delete Project

### Q: 国内访问慢怎么办？
A: Vercel 在全球都有 CDN，但国内访问可能不如国内平台快。如果需要优化，可以考虑：
- 购买国内 CDN 服务
- 或者同时使用 Gitee Pages 作为国内镜像

## 📞 需要帮助？

如果在部署过程中遇到问题：
1. 检查 GitHub 仓库中的文件是否完整上传
2. 确认 Vercel 的 Framework Preset 设置为 "Other"
3. 查看 Vercel 的部署日志（Deploy 页面）查找错误信息

---

🎉 **恭喜！部署完成后，你就可以在简历上写上：**
> "个人作品集：https://你的域名.vercel.app"

祝求职顺利！🗺️✨
