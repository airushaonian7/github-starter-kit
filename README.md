# GitHub 使用入门指南

> 这是 airushaonian7 的 GitHub 入门模板仓库——**把常用命令、模板文件、使用要点都放在这**，新项目直接复制复用。

## 一、GitHub 是什么

GitHub = **代码托管平台 + 协作社区**。你可以把代码放到云端（仓库 Repository），随时存取、备份、给别人看、和别人一起改。

- 私人代码 → 私有仓库（只有你能看）
- 开源/分享 → 公开仓库（全世界能看）
- 个人主页 → GitHub Pages（免费托管网页）

## 二、常用命令速查

### 本地 Git（每天用）

```bash
git init                          # 当前目录变成仓库
git add .                         # 暂存所有改动
git commit -m "说明文字"          # 提交（存档点）
git push                          # 推到 GitHub
git pull                          # 拉取远程最新
git status                        # 看改动状态
git log --oneline                 # 看提交历史
```

### GitHub CLI（gh，不用开网页）

```bash
gh repo create 仓库名 --public --source . --push   # 建公开仓库并推送
gh repo clone 用户名/仓库名                        # 克隆别人/自己的仓库
gh repo list --limit 20                           # 列出我的仓库
gh issue list                                    # 看 Issue 列表
gh auth status                                   # 看登录状态
```

## 三、一个完整流程（从零到推送）

```bash
# 1. 建项目目录并写代码
mkdir my-project && cd my-project
echo "# Hello" > README.md

# 2. 初始化 + 提交
git init
git add .
git commit -m "first commit"

# 3. 建远程仓库并推送（SSH 免密，不用输密码）
gh repo create my-project --public --source . --push
```

## 四、模板文件说明

| 文件 | 作用 |
|---|---|
| `.gitignore` | 告诉 Git 哪些文件不要提交（缓存/密钥/临时文件） |
| `LICENSE` | 开源许可证（本仓库用 MIT，最宽松） |
| `README.md` | 项目说明首页（自动显示在仓库主页） |
| `git-commands.md` | 本文件：命令速查 |

## 五、安全要点

1. **私钥永不外传**：`C:\Users\李明谦\.ssh\id_ed25519`（无 .pub 后缀的是私钥）
2. **密码永不进代码**：密码/API Key 放 `.env`（已被 .gitignore 排除），或存本地保险库
3. **个人信息保护**：不要在公开仓库放手机号/身份证/住址/家庭信息
4. **提交前检查**：`git status` 确认没有误提交敏感文件

## 六、下一步

- [ ] 建个人主页 → 见 `airushaonian7.github.io` 仓库
- [ ] 建第一个项目仓库
- [ ] 学 GitHub Issues（提需求/记任务）
- [ ] 学 Pull Request（代码协作）
