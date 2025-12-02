# Cloudflare Pages 部署指南

## 🚀 部署方式

### 方法一：Git 集成部署（推荐）⭐

这是最推荐的方式，支持自动部署和版本管理。

#### 步骤：

1. **将代码推送到 Git 仓库**

```bash
# 初始化 Git 仓库（如果还没有）
git init

# 添加所有文件
git add .

# 提交
git commit -m "Initial commit: Aohan Millet website"

# 添加远程仓库（以 GitHub 为例）
git remote add origin https://github.com/your-username/aohan-millet.git

# 推送代码
git push -u origin main
```

2. **在 Cloudflare 创建 Pages 项目**

   a. 访问 [Cloudflare Dashboard](https://dash.cloudflare.com/)
   
   b. 点击左侧菜单的 **"Pages"**
   
   c. 点击 **"创建项目"** 或 **"Connect to Git"**
   
   d. 选择您的 Git 提供商（GitHub/GitLab/Bitbucket）
   
   e. 授权 Cloudflare 访问您的仓库
   
   f. 选择 `aohan-millet` 仓库

3. **配置构建设置**

```
项目名称：aohan-millet
生产分支：main
框架预设：None
构建命令：（留空）
构建输出目录：/
根目录：（留空）
环境变量：（不需要）
```

4. **保存并部署**

   - 点击 **"保存并部署"**
   - Cloudflare 会自动部署您的网站
   - 几分钟后，您将获得一个 `https://aohan-millet.pages.dev` 域名

5. **后续更新**

   每次推送到 `main` 分支，Cloudflare 会自动重新部署：
   
```bash
git add .
git commit -m "Update content"
git push
```

---

### 方法二：直接上传（快速部署）⚡

适合快速测试或不使用 Git 的场景。

#### 步骤：

1. **准备文件**

   确保以下文件在同一个文件夹中：
   - `index.html`
   - `styles.css`
   - `script.js`

2. **登录 Cloudflare**

   访问 [Cloudflare Pages](https://pages.cloudflare.com/)

3. **创建项目**

   - 点击 **"创建项目"**
   - 选择 **"直接上传"**

4. **上传文件**

   - 将所有文件拖拽到上传区域
   - 或点击上传按钮选择文件

5. **配置项目**

```
项目名称：aohan-millet
```

6. **部署**

   - 点击 **"部署站点"**
   - 等待部署完成（通常1-2分钟）

7. **更新网站**

   需要更新时，重新上传新版本的文件即可。

---

### 方法三：使用 Wrangler CLI（开发者推荐）💻

适合熟悉命令行的开发者。

#### 步骤：

1. **安装 Wrangler**

```bash
npm install -g wrangler
```

2. **登录 Cloudflare**

```bash
wrangler login
```

这会打开浏览器窗口，完成授权。

3. **部署项目**

```bash
# 在项目目录下执行
wrangler pages publish . --project-name=aohan-millet
```

4. **后续更新**

```bash
# 每次更新后执行
wrangler pages publish . --project-name=aohan-millet
```

---

## 🌐 自定义域名

部署后，您可以添加自己的域名。

### 步骤：

1. **在 Cloudflare Pages 中添加域名**

   - 进入您的 Pages 项目
   - 点击 **"自定义域"** 标签
   - 点击 **"设置自定义域"**
   - 输入您的域名（例如：`www.aohanmillet.com`）

2. **配置 DNS**

   如果域名在 Cloudflare 管理：
   - Cloudflare 会自动添加 DNS 记录
   
   如果域名在其他地方：
   - 添加以下 DNS 记录到您的域名提供商：
   
   ```
   类型：CNAME
   名称：www（或您的子域名）
   值：aohan-millet.pages.dev
   ```

3. **等待 DNS 生效**

   通常需要几分钟到24小时。

4. **SSL/HTTPS**

   Cloudflare 会自动为您的自定义域名提供免费 SSL 证书。

---

## ⚙️ 高级配置（可选）

### 添加 _headers 文件（优化安全性和缓存）

在项目根目录创建 `_headers` 文件：

```
/*
  X-Frame-Options: DENY
  X-Content-Type-Options: nosniff
  X-XSS-Protection: 1; mode=block
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: geolocation=(), microphone=(), camera=()

/*.css
  Cache-Control: public, max-age=31536000, immutable

/*.js
  Cache-Control: public, max-age=31536000, immutable

/*.html
  Cache-Control: public, max-age=3600
```

### 添加 _redirects 文件（URL重定向）

在项目根目录创建 `_redirects` 文件：

```
# 重定向示例
/old-page  /  301

# SPA 路由支持（如果将来需要）
/*  /index.html  200
```

### 添加 robots.txt（SEO优化）

```
User-agent: *
Allow: /

Sitemap: https://your-domain.com/sitemap.xml
```

---

## 🔍 部署后检查清单

- [ ] 网站能正常访问
- [ ] 所有页面链接工作正常
- [ ] 响应式设计在移动端正常显示
- [ ] 导航菜单在移动端可以展开
- [ ] 所有动画效果正常
- [ ] 滚动动画触发正确
- [ ] 返回顶部按钮工作
- [ ] HTTPS 证书生效
- [ ] 自定义域名（如果配置）正确解析

---

## 🐛 常见问题

### 1. 部署后页面空白

**原因**：文件路径问题

**解决**：确保所有资源文件（CSS、JS）使用相对路径或绝对路径。

### 2. CSS/JS 没有加载

**原因**：文件名大小写或路径错误

**解决**：检查 `index.html` 中的文件引用是否与实际文件名一致。

### 3. 自定义域名无法访问

**原因**：DNS 未生效或配置错误

**解决**：
- 检查 DNS 记录是否正确
- 等待 DNS 传播（最多24小时）
- 使用 `dig` 或 `nslookup` 命令检查 DNS

```bash
dig your-domain.com
```

### 4. 更新后内容没有变化

**原因**：浏览器缓存

**解决**：
- 按 `Ctrl + F5`（Windows）或 `Cmd + Shift + R`（Mac）强制刷新
- 清除浏览器缓存
- 使用隐身模式测试

---

## 📊 性能优化建议

Cloudflare Pages 已经提供了很多优化，但您还可以：

1. **启用 Cloudflare Analytics**
   - 在 Pages 项目设置中启用 Web Analytics
   - 查看访问量和性能数据

2. **优化图片（如果将来添加）**
   - 使用 WebP 格式
   - 使用 Cloudflare Images 服务

3. **使用 Cloudflare CDN**
   - 自动启用，无需配置
   - 全球300+节点加速

---

## 🎯 测试部署

本地测试模拟 Cloudflare Pages 环境：

```bash
# 使用 Python 启动本地服务器
python -m http.server 8000

# 或使用 Node.js
npx serve .

# 访问 http://localhost:8000
```

---

## 📱 移动端测试

部署后在以下设备上测试：

- [ ] iPhone Safari
- [ ] Android Chrome
- [ ] iPad Safari
- [ ] Android 平板
- [ ] 各种屏幕尺寸（使用浏览器开发者工具）

---

## 🔐 安全最佳实践

Cloudflare Pages 默认提供：

- ✅ 免费 SSL/TLS 证书
- ✅ 自动 HTTPS 重定向
- ✅ DDoS 保护
- ✅ CDN 加速
- ✅ 防火墙规则

---

## 📈 监控和分析

1. **Cloudflare Web Analytics**
   - 免费
   - 隐私友好
   - 无需 cookie

2. **自定义分析（可选）**
   - Google Analytics
   - Plausible
   - Fathom

添加方式：在 `index.html` 的 `</head>` 前添加跟踪代码。

---

## 💡 提示

- 首次部署可能需要2-5分钟
- 更新通常在30秒内完成
- Cloudflare Pages 提供无限带宽
- 支持每月500次构建
- 支持并发构建

---

## 📞 获取帮助

- Cloudflare 文档：https://developers.cloudflare.com/pages/
- Cloudflare 社区：https://community.cloudflare.com/
- 支持：https://support.cloudflare.com/

---

## ✅ 部署成功！

您的敖汉小米网站现在已经上线，可以通过以下方式访问：

- **Pages.dev 域名**：`https://aohan-millet.pages.dev`
- **自定义域名**：`https://your-domain.com`（如果已配置）

祝您使用愉快！🎉
