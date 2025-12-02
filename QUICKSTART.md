# 🚀 快速开始指南

## 5分钟部署到 Cloudflare Pages

### 前提条件
- ✅ 一个 Cloudflare 账号（免费）
- ✅ 项目文件（已准备好）

---

## 最快部署方式：直接上传 ⚡

### 步骤 1：下载项目文件

确保您有以下文件：
```
✓ index.html
✓ styles.css
✓ script.js
✓ _headers
✓ _redirects
✓ robots.txt
✓ sitemap.xml
```

### 步骤 2：访问 Cloudflare Pages

打开浏览器，访问：https://dash.cloudflare.com/

### 步骤 3：创建 Pages 项目

1. 点击左侧菜单 **"Pages"**
2. 点击 **"创建项目"**
3. 选择 **"直接上传"**

### 步骤 4：上传文件

**方法A：拖拽上传**
- 将所有文件选中
- 拖拽到上传区域

**方法B：点击上传**
- 点击 "选择文件" 按钮
- 选择所有文件
- 点击 "打开"

### 步骤 5：配置项目

```
项目名称：输入 "aohan-millet" 或您喜欢的名称
```

### 步骤 6：部署

点击 **"部署站点"** 按钮

### 步骤 7：等待完成

⏱️ 通常需要 1-2 分钟

### 步骤 8：访问网站

✅ 部署完成后，您会看到：
```
https://aohan-millet.pages.dev
```

🎉 **恭喜！网站已上线！**

---

## 使用 Git 自动部署（推荐用于长期维护）

### 步骤 1：创建 GitHub 仓库

```bash
# 1. 访问 https://github.com/new
# 2. 创建新仓库，命名为 "aohan-millet"
# 3. 不要初始化 README
```

### 步骤 2：推送代码

```bash
# 在项目文件夹中执行
git init
git add .
git commit -m "Initial commit: Aohan Millet website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/aohan-millet.git
git push -u origin main
```

### 步骤 3：连接到 Cloudflare Pages

1. 访问 https://dash.cloudflare.com/
2. 点击 **"Pages"** → **"创建项目"**
3. 选择 **"连接到 Git"**
4. 授权 GitHub
5. 选择 `aohan-millet` 仓库
6. 配置构建：
   ```
   构建命令：（留空）
   构建输出目录：/
   ```
7. 点击 **"保存并部署"**

### 步骤 4：自动部署

✅ 以后每次推送代码，都会自动部署：

```bash
git add .
git commit -m "Update content"
git push
```

---

## 本地预览（可选）

### 使用 Python

```bash
# Python 3
python -m http.server 8000

# 访问 http://localhost:8000
```

### 使用 Node.js

```bash
npx serve .

# 访问 http://localhost:3000
```

### 使用 PHP

```bash
php -S localhost:8000

# 访问 http://localhost:8000
```

---

## 自定义域名（可选）

### 步骤 1：在 Cloudflare Pages 中添加域名

1. 进入您的 Pages 项目
2. 点击 **"自定义域"**
3. 点击 **"设置自定义域"**
4. 输入您的域名

### 步骤 2：配置 DNS

**如果域名在 Cloudflare：**
- ✅ 自动配置，无需操作

**如果域名在其他地方：**
- 添加 CNAME 记录：
  ```
  类型: CNAME
  名称: www
  值: aohan-millet.pages.dev
  ```

### 步骤 3：等待生效

⏱️ 通常需要几分钟到24小时

---

## 验证部署

访问您的网站，检查：

- [ ] 页面正常显示
- [ ] 导航链接工作
- [ ] 移动端响应式正常
- [ ] 滚动动画正常
- [ ] 返回顶部按钮出现

---

## 常见问题

### Q: 部署后显示空白页？

**A:** 清除浏览器缓存，按 `Ctrl+F5` 强制刷新

### Q: CSS 样式没有加载？

**A:** 确保 `styles.css` 文件名正确，检查大小写

### Q: 如何更新网站内容？

**A:** 
- **直接上传方式**：重新上传新版本
- **Git方式**：推送代码即可自动更新

### Q: 忘记了网站地址？

**A:** 
1. 登录 Cloudflare Dashboard
2. 点击 "Pages"
3. 点击您的项目
4. 查看 "域" 部分

---

## 下一步

- 📊 启用 Cloudflare Web Analytics
- 🎨 根据需要自定义内容
- 🌐 添加自定义域名
- 📱 在各种设备上测试

---

## 获取帮助

- 📖 查看 [README.md](README.md) 了解详细信息
- 📘 查看 [DEPLOY.md](DEPLOY.md) 了解高级配置
- 💬 访问 Cloudflare 社区获取支持

---

**🎉 享受您的敖汉小米网站！**
