# 🚀 部署到 GitHub Pages 流程

你的仓库地址：`https://github.com/Yongfei-Hu/xidian-rainclass`

---

## 本地项目已就绪

以下文件已准备好，在 `D:/Downloads/xidian-rainclass/` 下：

```
xidian-rainclass/
├── index.html                  # 🏠 专栏首页
├── ai-security-ethics.html     # 📖 课程内容页
├── css/style.css               # 🎨 样式
├── images/*.png                # 🖼️ 23张配图
├── README.md                   # 📝 项目说明
├── SETUP.md                    # 📋 本指南
└── .git/                       # 已初始化 git
```

---

## 方法 A：使用 GitHub CLI（推荐，更快）

GitHub CLI 已安装在你的电脑上。先登录，然后一键推送。

### A1. 登录 GitHub

```bash
gh auth login
```

交互选择：
```
? What account do you want to log into?        → GitHub.com
? What is your preferred protocol for Git?     → HTTPS
? Authenticate Git with your GitHub credentials? → Yes
? How would you like to authenticate?          → Login with a web browser
```

浏览器弹窗 → 点授权 → 完成。

### A2. 配置 Git 身份

```bash
git config user.name "Yongfei-Hu"
git config user.email "你的GitHub邮箱"
```

### A3. 提交本地文件

```bash
git add .
git commit -m "西电雨课堂 - 人工智能安全与伦理课程页面"
```

### A4. 关联远程仓库并推送

```bash
git remote add origin https://github.com/Yongfei-Hu/xidian-rainclass.git
git branch -M main
git pull origin main --allow-unrelated-histories
git push -u origin main
```

> ⚠️ `--allow-unrelated-histories` 是必要的，因为你勾选了 "Add a README file"，远程仓库已有一个初始 README，和本地 git 历史无关。
>
> 如果 pull 时遇到冲突（README.md 两边都有），解决后 commit 再 push 即可。最简单的方式：pull 时直接保留本地版本覆盖远程。

---

## 方法 B：纯 Git 命令行

如果不想用 gh CLI，只使用 Git。

### B1. 配置 Git 身份

```bash
git config user.name "Yongfei-Hu"
git config user.email "你的GitHub邮箱"
```

### B2. 提交本地文件

```bash
git add .
git commit -m "西电雨课堂 - 人工智能安全与伦理课程页面"
```

### B3. 关联远程仓库

```bash
git remote add origin https://github.com/Yongfei-Hu/xidian-rainclass.git
git branch -M main
```

### B4. 拉取远程 README 并推送

```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

### B5. 认证

推送时会弹出 GitHub 登录窗口，或要求输入用户名和 **Personal Access Token**（不是密码）。

> 如果还没有 Token：打开 https://github.com/settings/tokens → Generate new token (classic) → 勾选 `repo` 权限 → 生成后复制保存。

---

## 步骤 3：开启 GitHub Pages

1. 打开 https://github.com/Yongfei-Hu/xidian-rainclass/settings/pages
2. **Source** → **Deploy from a branch**
3. **Branch** → 选 `main`，目录选 `/ (root)`，点 **Save**
4. 等 1-2 分钟，页面顶部显示：
   ```
   ✅ Your site is live at https://yongfei-hu.github.io/xidian-rainclass/
   ```

---

## 访问你的专栏 🎉

- 🏠 首页：`https://yongfei-hu.github.io/xidian-rainclass/`
- 📖 课程页：`https://yongfei-hu.github.io/xidian-rainclass/ai-security-ethics.html`

---

## 以后更新内容

```bash
git add .
git commit -m "更新说明"
git push
```

GitHub Pages 自动重新部署，几十秒后刷新即见。

---

## 快捷一键命令（已经完成 A1/A2 后可直接复制）

```bash
cd D:/Downloads/xidian-rainclass
git add .
git commit -m "西电雨课堂 - 人工智能安全与伦理课程页面"
git remote add origin https://github.com/Yongfei-Hu/xidian-rainclass.git
git branch -M main
git pull origin main --allow-unrelated-histories
git push -u origin main
```
