# GitBook 部署指南

本文档说明如何部署和发布 Hyperliquid Recovery Bot 的 GitBook 文档。

## 📚 关于 GitBook

GitBook 是一个现代化的文档平台，可以将 Markdown 文件转换为美观的在线文档。

## 🚀 快速部署

### 方法一：GitBook.com 在线部署 (推荐)

1. **注册 GitBook 账户**
   - 访问 [GitBook.com](https://www.gitbook.com/)
   - 注册或登录账户

2. **创建新的 Space**
   - 点击 "New Space"
   - 选择 "Import from Git"
   - 连接您的 GitHub 仓库

3. **配置同步**
   - 选择 `docs/gitbook` 目录作为文档根目录
   - 设置自动同步，当代码更新时自动更新文档

4. **发布文档**
   - 文档会自动生成并发布
   - 获得一个公开的文档链接

### 方法二：本地构建和部署

1. **安装 GitBook CLI**
   ```bash
   npm install -g gitbook-cli
   ```

2. **初始化和安装插件**
   ```bash
   cd docs/gitbook
   gitbook install
   ```

3. **本地预览**
   ```bash
   gitbook serve
   # 访问 http://localhost:4000 预览文档
   ```

4. **构建静态文件**
   ```bash
   gitbook build
   # 生成的文件在 _book 目录中
   ```

5. **部署到静态托管**
   - 将 `_book` 目录内容上传到：
     - GitHub Pages
     - Netlify
     - Vercel
     - 或其他静态托管服务

## 📁 文档结构

```
docs/gitbook/
├── README.md              # 首页
├── SUMMARY.md             # 目录结构
├── book.json              # GitBook 配置
├── quick-start.md         # 快速开始
├── bot-usage.md           # 机器人使用
├── address-detection.md   # 地址检测
├── asset-recovery.md      # 资产恢复
├── security.md            # 安全指南
├── faq.md                 # 常见问题
├── features.md            # 功能特性
└── contact.md             # 联系支持
```

## ⚙️ 配置说明

### book.json 配置
```json
{
  "title": "Hyperliquid Recovery Bot 用户指南",
  "description": "完整使用指南",
  "language": "zh-hans",
  "plugins": [
    "search",           // 搜索功能
    "sharing",          // 分享按钮
    "copy-code-button", // 代码复制按钮
    "back-to-top-button" // 返回顶部
  ]
}
```

### 自定义变量
在文档中可以使用以下变量：
- `{{ book.botUrl }}` - 机器人链接
- `{{ book.version }}` - 版本号
- `{{ book.supportEmail }}` - 支持邮箱

## 🔧 维护和更新

### 更新文档内容
1. 编辑对应的 Markdown 文件
2. 提交到 Git 仓库
3. GitBook 会自动同步更新

### 添加新页面
1. 创建新的 Markdown 文件
2. 在 `SUMMARY.md` 中添加链接
3. 提交更改

### 修改目录结构
编辑 `SUMMARY.md` 文件：
```markdown
# Summary

* [项目介绍](README.md)
* [快速开始](quick-start.md)
* [新页面](new-page.md)
```

## 📊 SEO 优化

### 页面元数据
在每个 Markdown 文件开头添加：
```markdown
---
title: 页面标题
description: 页面描述
keywords: 关键词1, 关键词2
---
```

### URL 优化
- 使用有意义的文件名
- 避免中文文件名
- 保持 URL 结构简洁

## 🌐 多语言支持

如需支持多语言：

1. **创建语言目录**
   ```
   docs/gitbook/
   ├── zh/          # 中文版本
   └── en/          # 英文版本
   ```

2. **配置 book.json**
   ```json
   {
     "language": "zh-hans",
     "languages": {
       "zh": "中文",
       "en": "English"
     }
   }
   ```

## 📱 移动端优化

GitBook 自动适配移动端，但可以通过以下方式优化：

1. **图片优化**
   - 使用适当的图片尺寸
   - 提供高分辨率图片的替代方案

2. **表格优化**
   - 避免过宽的表格
   - 使用响应式表格设计

3. **代码块优化**
   - 保持代码行长度适中
   - 使用语法高亮

## 🔍 搜索功能

GitBook 内置搜索功能：
- 自动索引所有内容
- 支持中文搜索
- 实时搜索结果

## 📈 分析和统计

### Google Analytics
在 `book.json` 中添加：
```json
{
  "plugins": ["ga"],
  "pluginsConfig": {
    "ga": {
      "token": "UA-XXXXXXXX-X"
    }
  }
}
```

### 用户反馈
可以集成：
- Disqus 评论系统
- GitHub Issues 反馈
- 自定义反馈表单

## 🚨 常见问题

### 构建失败
1. 检查 `book.json` 语法
2. 确认所有插件已安装
3. 检查 Markdown 语法错误

### 中文显示问题
1. 确保文件编码为 UTF-8
2. 设置正确的语言配置
3. 使用支持中文的字体

### 图片不显示
1. 检查图片路径是否正确
2. 确保图片文件存在
3. 使用相对路径引用图片

## 📞 获取帮助

如果在部署过程中遇到问题：

1. **查看 GitBook 官方文档**
   - [GitBook 文档](https://docs.gitbook.com/)
   - [GitBook CLI 文档](https://github.com/GitbookIO/gitbook-cli)

2. **社区支持**
   - GitBook 社区论坛
   - Stack Overflow
   - GitHub Issues

3. **联系我们**
   - 通过项目 Issues 报告问题
   - 发送邮件到技术支持

---

**提示**: 建议先在本地测试文档效果，确认无误后再部署到生产环境。
