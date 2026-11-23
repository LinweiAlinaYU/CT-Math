# GitHub Pages 部署说明 / Deployment Guide

## A. 最简单的方式：使用 GitHub 网页上传

1. 登录 GitHub，点击 **New repository**，例如命名为 `ct-integrated-mathematics`。若希望公开访问，建议设置为 **Public**。
2. 创建 repository。进入仓库，选择 **Add file → Upload files**。
3. **解压 ZIP 文件**，将解压所得文件夹内的文件上传至 repository 根目录。确保 `index.html` 位于根目录，即仓库首页能够直接看到 `index.html`。注意：**不要只上传 ZIP 文件本身，也不要把整个文件夹放在仓库的子目录中**。
4. 点击 **Commit changes** 保存文件。
5. 进入仓库 **Settings → Pages**，在 **Build and deployment** 中设置：
    - **Source:** Deploy from a branch
    - **Branch:** `main`
    - **Folder:** `/(root)`
    - 然后点击 **Save**
6. 在 **Settings → Pages** 中查看 GitHub 提供的公开站点地址。对于普通项目仓库，通常为：

   `https://YOUR-USERNAME.github.io/ct-integrated-mathematics/`

7. 打开站点，检查顶部标题是否为 **Can You Fix the Broken Line Tool?**，再测试 Explore 的坐标滑块以及 Elaborate 的算法切换。

> 如果已有网站仓库：只需要将本包里的 `index.html` 用作仓库根目录的 `index.html`。若仓库里还有已有的网站资源，注意不要误删其他内容。

## B. 更新网页

以后每次有改动，只需替换根目录下的 `index.html` 并提交。无需安装 Node.js、npm、Jekyll 或其他构建工具。

## C. 常见问题

**出现 404**：检查 Pages 是否启用、源分支与 `/(root)` 是否正确、`index.html` 是否在根目录、访问的 URL 是否使用实际 repository 名称。

**GitHub 上能看到源码，但看不到网站**：请使用 `Settings → Pages` 显示的网站 URL，不是仓库代码 URL。

**样式或交互丢失**：本网站的 CSS 与 JavaScript 都在 `index.html` 内。确保上传的是包中的完整文件，而不是 README 或屏幕截图。

**图片缺失**：`assets/site-preview.png` 仅供 GitHub README 展示，不影响网站运行。交互图像以网页自身的 SVG 代码绘制。

**在线更改后页面仍是旧版**：可刷新页面；也可在 Pages 部署状态页面确认最新提交已发布。

## D. 仓库结构

```text
ct-integrated-mathematics/
├── index.html
├── .nojekyll
├── README.md
├── DEPLOYMENT.md
└── assets/
    └── site-preview.png
```

## English quick steps

Create a GitHub repository → upload the **contents** of this folder at repository root → **Settings → Pages** → **Deploy from a branch** → select `main` and `/(root)` → **Save** → visit the displayed Pages URL.

Official documentation: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
