# jotdone 静态站点（GitHub Pages）

用于 App Store Connect 必填的「隐私政策 URL」与「技术支持 URL」。
纯静态 HTML，无需构建，托管在 GitHub Pages。

## 文件说明
- `index.html` — 简单产品落地页
- `privacy.html` — 隐私政策（App Store 审核必填）
- `support.html` — 技术支持 / 常见问题（App Store 审核必填）

上线后地址：
- 隐私政策：`https://jotdone.github.io/privacy`
- 技术支持：`https://jotdone.github.io/support`

## 部署步骤
1. 在 GitHub 新建一个仓库，仓库名**必须**为 `jotdone.github.io`（属于你自己的 GitHub 账号）。
   - 注意：仓库名必须是 `<你的用户名>.github.io` 这种形式，GitHub Pages 才会自动以根路径发布。
2. 把本目录下的三个 `.html` 文件推送到该仓库的 `main` 分支：
   ```bash
   cd website
   git init
   git add *.html
   git commit -m "init jotdone pages"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/jotdone.github.io.git
   git push -u origin main
   ```
3. 仓库 → Settings → Pages → Source 选择 `Deploy from a branch`，分支选 `main`、目录选 `/ (root)`，保存。
4. 等待几分钟，访问 `https://jotdone.github.io/privacy` 确认能打开。
5. 在 App Store Connect → 你的 App → App 信息 中填写：
   - 隐私政策 URL：`https://jotdone.github.io/privacy`
   - 技术支持 URL：`https://jotdone.github.io/support`

## 自定义
- 邮箱 `support@jotdone.app` / `privacy@jotdone.app` 为占位，请替换为你真实可用的邮箱。
- 如需自有域名（如 `jotdone.app`），可在仓库 Settings → Pages 中绑定自定义域，并把上面的 URL 改为你的域名路径。
