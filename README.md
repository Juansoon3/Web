# 闫娜个人网站

SNH48 X队成员闫娜的个人信息展示网站，包括个人简介、演艺经历、图片展示等内容。

## 项目介绍

这是一个静态网站项目，使用纯 HTML5 和 CSS3 构建，无需构建工具，可以直接部署到任何静态网站托管服务。

## 功能特点

- 响应式设计，支持移动端和桌面端
- 语义化 HTML5 结构
- SEO 优化，包含 Open Graph 和 Twitter Card 元标签
- 优化的加载性能
- 支持国内网络访问（通过 Vercel 亚洲区域部署）

## 本地运行

### 方法 1：使用 Python HTTP 服务器

```bash
# 进入项目目录
cd Web

# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

然后在浏览器中访问：`http://localhost:8000`

### 方法 2：使用 Node.js http-server

```bash
# 安装 http-server（如果还没有安装）
npm install -g http-server

# 进入项目目录
cd Web

# 启动服务器
http-server -p 8000
```

然后在浏览器中访问：`http://localhost:8000`

## 部署到 GitHub

### 步骤 1：在 GitHub 上创建仓库

1. 访问 [GitHub.com](https://github.com) 并登录
2. 点击右上角的 **+** 号，选择 **New repository**
3. 填写仓库信息：
   - **Repository name**: 输入仓库名称，例如 `yanna-website`
   - **Description**: 可选，例如 "闫娜个人网站"
   - **Public/Private**: 选择 **Public**（公开）
4. **不要**勾选 "Add a README file"、"Add .gitignore"、"Choose a license"
5. 点击 **Create repository** 按钮

### 步骤 2：使用 GitHub Desktop 上传项目

1. 打开 **GitHub Desktop** 应用程序
2. 点击左上角的 **File** → **Add Local Repository...**
3. 浏览到项目目录：`c:\Users\1\Documents\trae_projects\Web`
4. 点击 **Add Repository**
5. 在 GitHub Desktop 中，您会看到项目的变更
6. 在左下角的 "Summary" 框中输入提交信息，例如：`Initial commit - 闫娜个人网站`
7. 点击 **Commit to main** 按钮
8. 点击右上角的 **Publish repository** 按钮
9. 在弹出的窗口中：
   - **Name**: 确认仓库名称（例如：`yanna-website`）
   - **Description**: 可选描述
   - **Visibility**: 选择 **Public**
10. 点击 **Publish repository** 按钮

### 步骤 3：验证上传成功

1. 上传完成后，GitHub Desktop 会显示 "Repository published"
2. 点击 **View on GitHub** 按钮，或者在浏览器中访问您的仓库地址
3. 您应该能看到所有文件都已上传到 GitHub

## 部署到 Vercel

### 步骤 1：注册/登录 Vercel

1. 打开浏览器，访问 [Vercel.com](https://vercel.com)
2. 点击右上角的 **Sign Up** 或 **Login**
3. 选择使用 **GitHub** 账号登录（推荐）
4. 授权 Vercel 访问您的 GitHub 账号

### 步骤 2：导入 GitHub 仓库到 Vercel

1. 登录后，点击 **Add New...** → **Project**
2. 在 "Import Git Repository" 部分，您会看到您的 GitHub 仓库列表
3. 找到并点击您的仓库（例如：`yanna-website`）
4. 点击 **Import** 按钮

### 步骤 3：配置项目设置

在项目配置页面，您会看到以下设置：

**Framework Preset**: 
- Vercel 会自动检测为 "Other" 或 "Static HTML"
- 保持默认设置即可

**Build and Output Settings**:
- **Build Command**: 留空（不需要构建命令）
- **Output Directory**: 留空（根目录）
- **Install Command**: 留空（不需要安装依赖）

**Environment Variables**:
- 不需要添加任何环境变量

**Root Directory**:
- 保持为 `./`（根目录）

### 步骤 4：开始部署

1. 检查所有设置无误后，点击 **Deploy** 按钮
2. 等待部署完成（通常需要 1-3 分钟）
3. 部署成功后，您会看到一个绿色的 "Congratulations!" 页面
4. 记下您的 Vercel 域名，例如：`https://yanna-website.vercel.app`

## 国内访问优化

本项目已配置为在亚洲区域部署，确保国内用户可以快速访问。

### 配置说明

在 `vercel.json` 文件中，已配置以下区域：

```json
{
  "regions": ["sin1", "nrt1"]
}
```

- `sin1` = 新加坡（Singapore）
- `nrt1` = 东京（Tokyo）

这两个区域对中国大陆的访问速度优化最好。

### 验证部署区域

1. 在 Vercel 项目页面，点击 **Deployments** 标签
2. 点击最新的部署记录
3. 查看 **Build Log**，您应该能看到类似这样的信息：
   ```
   Running build in Singapore, Singapore (Southeast Asia) – sin1
   ```
   或
   ```
   Running build in Tokyo, Japan (Asia Pacific) – nrt1
   ```

### 国内访问测试

1. **不使用 VPN** 的情况下访问您的 Vercel 域名
2. 测试访问速度：
   - 页面加载速度应该比较快（因为部署在新加坡或东京）
   - 如果加载较慢，可能需要等待 DNS 缓存更新（通常需要几分钟到几小时）

## 项目结构

```
Web/
├── index.html          # 首页
├── about.html          # 关于页面
├── gallery.html        # 图片展示页面
├── contact.html        # 联系方式页面
├── style.css           # 样式文件
├── vercel.json         # Vercel 配置文件
├── .gitignore          # Git 忽略文件
└── README.md           # 项目说明文档
```

## 更新项目

当您需要更新网站时：

1. 在本地修改文件
2. 打开 GitHub Desktop
3. 您会看到变更列表
4. 在 "Summary" 框中输入提交信息
5. 点击 **Commit to main** 按钮
6. 点击 **Push origin** 按钮（或 **Sync** 按钮）
7. Vercel 会自动检测到 GitHub 的更新并重新部署

## 常见问题

### 问题 1：访问速度慢

**解决方案**：
- 等待 DNS 缓存更新（通常需要 5-10 分钟）
- 检查是否使用了正确的区域（新加坡或东京）
- 尝试清除浏览器缓存

### 问题 2：页面显示 404 错误

**解决方案**：
- 检查 `vercel.json` 中的路由配置
- 确保所有文件都已上传到 GitHub
- 重新部署项目

### 问题 3：样式未加载

**解决方案**：
- 检查 `style.css` 文件是否存在
- 检查 HTML 文件中的 CSS 链接是否正确
- 清除浏览器缓存后重试

### 问题 4：在国内无法访问

**解决方案**：
- 确认 `vercel.json` 中配置了 `regions: ["sin1", "nrt1"]`
- 检查部署日志确认使用了正确的区域
- 如果仍然无法访问，可能需要等待 Vercel 的 CDN 缓存更新

## 技术栈

- HTML5
- CSS3
- Vercel（部署平台）
- GitHub（版本控制）

## 许可证

本项目仅供学习和展示使用。

## 联系方式

如有问题或建议，请通过以下方式联系：

- 微博：@闫娜
- 抖音：@闫娜
- B站：@闫娜

---

**注意**：请确保在 GitHub 上创建的是 **Public** 仓库（公开仓库），这样 Vercel 才能访问。