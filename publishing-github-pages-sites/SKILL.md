---
name: publishing-github-pages-sites
description: Use when a user wants to create, publish, repair, or update a simple static website on GitHub Pages, including repo setup, Pages settings, push authentication, custom domain DNS, or live URL verification.
---

# Publishing GitHub Pages Sites

## Overview

核心原则：先把一个最小静态站在 GitHub Pages 跑通，再处理美化、域名、DNS、备案和自动化。GitHub Pages 适合 HTML/CSS/JS/图片这类静态网站；如果需要后端、数据库、登录、支付或中国大陆备案主机，要换路线。

## When to Use

使用本 Skill：

- 用户说“用 GitHub 做网站”“放到 GitHub Pages”“生成一个网页”“把网页上线到 GitHub”。
- 已有 `index.html`、`styles.css`、`assets/` 等静态文件，需要发布。
- GitHub 仓库已创建，但 push、Pages 构建、认证、域名或 DNS 卡住。
- 用户需要一个可分享的临时官网、Coming Soon 页、个人作品页、活动页。

不要使用本 Skill：

- 网站必须在中国大陆稳定访问并完成 ICP 备案。此时 GitHub Pages 只能做预览，不是正式备案主机。
- 项目依赖服务端运行。此时优先考虑 Vercel、Netlify、Cloudflare Pages 或云服务器。

## Publishing Route

| 情况 | 推荐路线 |
| --- | --- |
| 纯静态页面，无构建步骤 | GitHub Pages: `main` branch + root folder |
| 需要 npm build、React/Vite/Next 静态导出 | GitHub Actions Pages workflow |
| 本机没有 GitHub 推送权限 | 先解决认证，再发布 |
| 长期维护同一个仓库 | 仓库专用 SSH Deploy Key |
| SSH 22 端口超时 | 用 `ssh://git@ssh.github.com:443/OWNER/REPO.git` |
| 要绑定自定义域名 | 先确认 GitHub Pages 预览稳定，再改 DNS |

## Workflow

1. 做发布预检。
   - 确认项目是不是静态网站。
   - 确认入口文件通常是 `index.html`。
   - 确认图片、字体、CSS 路径不是本机绝对路径。
   - 确认不包含未定稿的邮箱、电话、私密信息。

2. 准备 GitHub 仓库。
   - 如果仓库不存在，请用户创建或授权创建。
   - 如果仓库已存在，检查远程地址、默认分支、当前文件状态。
   - 连接器能读仓库不等于能写文件；必须确认内容推送权限。

3. 选择 Pages 发布方式。
   - 简单静态站先用 branch publish：`main` / root。
   - 只有需要构建步骤，才添加 GitHub Actions。
   - 不要同时保留多套发布机制，避免队列和失败状态互相干扰。

4. 处理认证。
   - HTTPS push 失败时，不要反复重试。
   - 临时操作可用 GitHub CLI 登录。
   - 长期发布优先用 SSH Deploy Key，并限制在单个仓库。
   - 不要把 token、私钥、验证码写进项目文件或聊天正文。

5. 推送并等待。
   - push 后给 GitHub Pages 几分钟构建时间。
   - 如果后台显示 queued，不要频繁触发新部署。
   - 如果 Pages branch route 反复失败且需要构建，再切到 Actions。

6. 真实验证。
   - 公共 URL 返回 `200`。
   - 页面包含最新关键文字。
   - CSS、图片、Logo 等资源返回 `200`。
   - 手机和桌面宽度没有明显断行、遮挡、溢出。
   - 本地工作区干净，或明确说明还剩什么改动。

7. 域名和 DNS。
   - 先让 `https://OWNER.github.io/REPO/` 稳定可打开。
   - 再配置 custom domain 和 DNS。
   - apex 域名、`www`、CNAME、A/AAAA 记录要分别说明。
   - 中国大陆正式站要单独评估云服务器地区、备案服务号和 ICP 流程。

## Red Flags

- 只看到 GitHub 仓库存在，就说网站已经上线。
- 只看后台绿色或红色状态，不打开真实网址。
- 连接器能读 GitHub，就误以为可以 push。
- 把简单静态站一开始做成复杂 Actions。
- 忽略 logo、CSS、图片是否真实加载。
- 把 GitHub Pages 当成中国大陆备案服务器。
- 在回复里打印私钥、token 或验证码。

## Done Criteria

完成时必须能说清楚：

- 线上地址是什么。
- 发布机制是什么：branch Pages 还是 Actions Pages。
- 最新内容是否已经出现在真实页面。
- 关键资源是否加载。
- 认证方式是否安全、可持续。
- 自定义域名、DNS、ICP 或大陆访问还有没有后续限制。

