---
name: github-push
description: 将当前项目提交并推送到 GitHub 远程仓库。使用在用户要求提交 commit 并 push 到 GitHub，或提到"推送到 GitHub""提交到 GitHub"时。不要用于 Gitee 或其他平台。
---

# GitHub Push Skill

将当前项目提交并推送到 GitHub 远程仓库。

## 仓库地址
- Gitee (origin): git@gitee.com:HGJ-2005/opencode-custom-skill.git
- GitHub (github): git@github.com:Noya0502/opencode-custom-skill.git

## SSH 配置
- Host github.com 使用 ~/.ssh02/id_ed25519 私钥，走 ssh.github.com:443 端口。
- Host gitee.com 使用同一私钥。

## 步骤

1. 检查 git 状态
   - 运行 `git status --short` 查看有哪些变更
   - 如果工作区干净，直接告知用户没有需要推送的内容

2. 添加变更文件
   - 使用 `git add -A` 添加所有变更
   - 或按文件精确添加

3. 提交
   - 规范提交信息：`update: 简要描述本次改动`
   - 示例：`git commit -m "update: homepage nav expansion"`
   - 若用户已明确指定 commit message，则优先使用

4. 推送到 GitHub
   - 运行 `git push github master`
   - 若提示 known_hosts 写入权限被拒绝（sandbox 限制），可忽略——已配置 StrictHostKeyChecking no 且首次连接已持久化
   - 同时推送到 Gitee 可选：`git push origin master`

## 执行命令模板

```powershell
git status --short
git add -A
git commit -m "update: 描述"
git push github master
git push origin master   # 可选，同时同步到 Gitee
```

## 常见问题

- **Repository not found**：检查 GitHub 远程地址是否正确，仓库是否已创建，SSH key 是否已加入 GitHub 账号
- **Permission denied (publickey)**：检查 ~/.ssh/config 中 github.com 的 IdentityFile 是否指向正确私钥
- **Connection refused port 22**：GitHub 已走 ssh.github.com:443 备用通道，无需额外修改
- **hostfile_replace_entries Permission denied**：sandbox 限制导致 known_hosts 无法更新，不影响推送本身
