# 📤 GitHub 提交指南

## ✅ 已完成：本地 Git 初始化

Git 仓库已在本地初始化，文件已提交到本地仓库。

## 📋 下一步：推送到 GitHub

### 第一步：在 GitHub 创建仓库

1. 打开 https://github.com/new
2. 填写信息：
   - Repository name: `gis-portfolio`
   - Description: `GIS职业规划与作品集网站`
   - 选择 **Public**
   - **不要**勾选 "Add a README file"
3. 点击 **Create repository**

### 第二步：连接远程仓库并推送

创建仓库后，在页面中找到 **"…or push an existing repository from the command line"**，复制下面的命令运行：

```bash
git remote add origin https://github.com/你的用户名/gis-portfolio.git
git branch -M main
git push -u origin main
```

**或者如果你已经完成了创建，直接运行：**

```bash
# 替换 your-username 为你的 GitHub 用户名
git remote add origin https://github.com/your-username/gis-portfolio.git
git branch -M main
git push -u origin main
```

### 第三步：验证上传

1. 刷新 GitHub 页面
2. 应该能看到所有文件：
   ```
   career-plan/
   portfolio/
   index.html
   vercel.json
   README.md
   DEPLOY_GUIDE.md
   VERCEL_DEPLOY.md
   ```

## 🚀 部署到 Vercel

GitHub 上传完成后，访问 https://vercel.com：

1. 点击 **Add New Project**
2. 导入 `gis-portfolio` 仓库
3. Framework Preset 选择 **Other**
4. 点击 **Deploy**

## 🔄 后续更新代码

以后修改代码后，使用以下命令更新：

```bash
# 查看修改的文件
git status

# 添加所有修改
git add .

# 提交修改
git commit -m "描述这次修改的内容"

# 推送到 GitHub
git push origin main
```

## ❓ 常见问题

### Q: 提示 "Authentication failed"？
A: 需要使用 GitHub Personal Access Token 代替密码：
1. 访问 https://github.com/settings/tokens
2. 点击 **Generate new token (classic)**
3. 勾选 **repo** 权限
4. 复制生成的 token，在命令行提示密码时粘贴它

### Q: 提示 "rejected because the remote contains work"？
A: 远程仓库有冲突，运行：
```bash
git pull origin main --allow-unrelated-histories
git push origin main
```

### Q: 不想用命令行？
A: 可以使用 GitHub Desktop 或者直接在网页上传文件。

---

💡 **需要帮助？** 遇到任何问题告诉我！
