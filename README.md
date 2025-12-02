# 敖汉小米官方网站

<div align="center">

🌾 **世界小米之乡 · 8000年传承的黄金谷物** 🌾

[![部署状态](https://img.shields.io/badge/部署-Cloudflare_Pages-orange)](https://pages.cloudflare.com/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![FAO认证](https://img.shields.io/badge/FAO-全球重要农业文化遗产-green)](http://www.fao.org/giahs)

</div>

## 📖 项目简介

这是一个专业的敖汉小米介绍网站，全面展示了敖汉小米的文化遗产、营养价值、国际认可、种植特色和多维度价值。网站采用现代化设计，响应式布局，适配各种设备。

### ✨ 主要特点

- 🏛️ **全球认证**：FAO全球重要农业文化遗产
- 🌍 **世界起源**：8000年小米种植历史的考古证据
- 🥇 **国家地理标志**：2003年获批保护产品
- 📊 **权威数据**：基于科学检测和学术研究
- 🎨 **精美设计**：采用敖汉小米金黄色调主题
- 📱 **响应式布局**：完美适配桌面、平板、手机

## 🚀 快速开始

### 本地预览

1. 克隆或下载项目到本地：
```bash
git clone <repository-url>
cd aohan-millet-website
```

2. 使用任意 Web 服务器启动项目：

**方法1：使用 Python（推荐）**
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

**方法2：使用 Node.js**
```bash
# 安装 http-server
npm install -g http-server

# 启动服务器
http-server -p 8000
```

**方法3：使用 PHP**
```bash
php -S localhost:8000
```

3. 在浏览器中访问 `http://localhost:8000`

### 直接打开

由于这是纯静态网站，也可以直接双击 `index.html` 文件在浏览器中打开。

## ☁️ 部署到 Cloudflare Pages

### 方法1：通过 Git 集成（推荐）

1. **准备 Git 仓库**
   - 将项目推送到 GitHub、GitLab 或 Bitbucket

2. **登录 Cloudflare**
   - 访问 [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - 登录您的账号

3. **创建 Pages 项目**
   - 点击左侧菜单 "Pages"
   - 点击 "创建项目" 或 "Connect to Git"
   - 授权 Cloudflare 访问您的 Git 仓库
   - 选择包含本项目的仓库

4. **配置构建设置**
   ```
   项目名称：aohan-millet（或您喜欢的名称）
   生产分支：main（或 master）
   构建命令：（留空）
   构建输出目录：/
   根目录：/
   ```

5. **部署**
   - 点击 "保存并部署"
   - Cloudflare 会自动构建和部署您的网站
   - 部署完成后，您将获得一个 `*.pages.dev` 域名

6. **自定义域名（可选）**
   - 在 Pages 项目设置中点击 "自定义域"
   - 添加您自己的域名
   - 按照提示配置 DNS 记录

### 方法2：直接上传（快速部署）

1. **登录 Cloudflare Dashboard**
   - 访问 [Cloudflare Pages](https://pages.cloudflare.com/)

2. **创建项目**
   - 点击 "创建项目"
   - 选择 "直接上传"

3. **上传文件**
   - 将项目文件夹中的所有文件打包为 ZIP
   - 或者直接拖拽文件夹到上传区域
   - 上传以下文件：
     - `index.html`
     - `styles.css`
     - `script.js`
     - 其他资源文件（如有）

4. **完成部署**
   - 输入项目名称
   - 点击 "部署站点"
   - 等待部署完成

### 方法3：使用 Wrangler CLI

1. **安装 Wrangler**
```bash
npm install -g wrangler
```

2. **登录 Cloudflare**
```bash
wrangler login
```

3. **部署项目**
```bash
wrangler pages publish . --project-name=aohan-millet
```

## 📁 项目结构

```
aohan-millet-website/
│
├── index.html          # 主页面（包含所有内容）
├── styles.css          # 样式表（金黄色主题）
├── script.js           # 交互脚本
├── README.md           # 项目说明文档
└── .gitignore          # Git 忽略文件
```

## 🎨 设计特色

### 色彩方案
- **主色调**：`#D4A574`（敖汉小米金黄色）
- **深色**：`#B8904E`
- **浅色**：`#E8C9A3`
- **辅助色**：`#8B7355`
- **强调色**：`#F5DEB3`

### 字体
- **标题字体**：Noto Serif SC（宋体风格，体现传统文化）
- **正文字体**：Noto Sans SC（无衬线，现代易读）

### 响应式断点
- 桌面：1024px 以上
- 平板：768px - 1024px
- 手机：768px 以下

## 📊 内容亮点

### 1. 文化遗产
- FAO 全球重要农业文化遗产认证（2012年）
- 8000年种植历史考古证据
- 国家地理标志保护产品（2003年）
- 完整的历史时间线

### 2. 营养价值
- 蛋白质含量：10.4%（高于普通小米1.5倍）
- 18种氨基酸，含8种必需氨基酸
- 丰富的维生素B群和矿物质
- 科学对比数据表格

### 3. 国际认可
- 联合国粮农组织（FAO）认证
- 国际农业博览会金奖
- 《Science》期刊学术报道
- 多项国内权威认证

### 4. 种植特色
- 北纬42°黄金纬度
- 年日照2900-3000小时
- 传统旱作农业技术
- 有机种植标准

### 5. 产品稀缺性
- 产地唯一性（仅产于敖汉旗）
- 年产量约30万吨
- 一年一季，生长周期120天
- 完全依靠天然降水

## 🔧 技术栈

- **HTML5**：语义化标签
- **CSS3**：
  - Flexbox 和 Grid 布局
  - CSS 变量
  - 渐变和动画
  - 响应式媒体查询
- **JavaScript**：
  - 原生 ES6+
  - Intersection Observer API
  - 平滑滚动
  - 懒加载优化
- **部署**：Cloudflare Pages

## 📱 浏览器兼容性

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ 移动浏览器（iOS Safari, Chrome Mobile）

## 🌟 特色功能

### 交互动画
- 滚动触发的卡片淡入动画
- 营养条进度动画
- 数字滚动计数效果
- 时间线逐项显示
- 悬停效果和过渡

### 用户体验
- 固定导航栏，滚动时阴影变化
- 移动端汉堡菜单
- 平滑锚点跳转
- 返回顶部按钮
- 响应式图片和布局

### 性能优化
- 防抖滚动事件
- Intersection Observer 懒加载
- CSS 硬件加速
- 最小化重排重绘

## 📈 SEO优化

- ✅ 语义化 HTML 标签
- ✅ Meta 描述和关键词
- ✅ 适当的标题层级（H1-H4）
- ✅ 结构化内容
- ✅ 移动端友好
- ✅ 快速加载速度

## 🔒 安全性

- 无外部依赖（除了 Google Fonts）
- 纯静态内容，无服务器端代码
- Cloudflare 提供的 HTTPS 和 DDoS 保护
- 内容安全策略（CSP）友好

## 📝 数据来源

所有数据均来自权威机构和学术研究：

- 联合国粮食及农业组织（FAO）
- 国家质量监督检验检疫总局
- 中国农业科学院
- 国家粮食质量检测中心
- 《Science》学术期刊
- 考古研究报告

## 🤝 贡献

欢迎提交问题和改进建议！

## 📄 许可证

MIT License

## 📞 联系方式

有关敖汉小米产品的咨询，请认准官方地理标志产品标识。

## 🎯 更新日志

### v1.0.0 (2024)
- ✅ 初始版本发布
- ✅ 完整的内容架构
- ✅ 响应式设计
- ✅ 交互动画
- ✅ Cloudflare Pages 部署支持

## 🙏 致谢

感谢所有为敖汉小米文化传承和推广做出贡献的人们！

---

<div align="center">

**传承古老农耕文明，守护人类粮食未来**

Made with ❤️ for Aohan Millet

</div>
