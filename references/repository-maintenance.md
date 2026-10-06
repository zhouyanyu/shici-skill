# Skill 仓库维护与同步

## 已授权范围

用户要求创建 `shici`、编写详细 README，并发布至 `git@github.com:zhouyanyu/shici-skill.git`；沿用其既有规则，以后修改本 skill 时同时更新仓库与必要 README。

- SSH：`git@github.com:zhouyanyu/shici-skill.git`
- 网页：`https://github.com/zhouyanyu/shici-skill`
- 安装名及 frontmatter：`shici`，仓库目录可为 `shici-skill`。

同步仅限 skill、元数据、方法参考、公开示例和说明文档。原书、私人笔记、背诵进度、个人创作与凭据不能进入发布仓库。普通读书任务不触发仓库同步，也没有定时同步任务。

## 操作

1. 检查本地安装及已有 checkout、仓库状态与远端。优先复用有效 checkout；已有内容先读取，不覆盖他人的未提交修改。
2. 正常获取远端状态和默认分支；远端为空时可初始化 main。无强制推送，不重置或删除用户变更。冲突不能可靠解决时保留工作并说明。
3. 修改源文件和本地安装，保持一致；行为、目录、依赖或用法变化同步 README。只有安装或已有配置确实变化时才说明需要重新加载技能。
4. 运行可用的 skill-creator 结构校验，检查引用、模板、示例和 README 安装命令；人工审查内容与公开范围。工具缺失则注明实际检查方式。
5. 精确暂存本次发布文件，提交并正常推送。已获该范围授权无需重复确认；环境执行权限仍遵守工具机制。
6. 对比远端分支提交与本地提交，报告实际结果；失败保留本地成果，不能声称已发布。

## Windows SSH

本机 Git 默认 SSH 可能无法使用 Windows SSH 代理。先用 `C:/Windows/System32/OpenSSH/ssh-add.exe -l` 查看已加载的公开指纹，再用：

```powershell
git -c 'core.sshCommand=C:/Windows/System32/OpenSSH/ssh.exe -o BatchMode=yes -o ConnectTimeout=15' ls-remote 'git@github.com:zhouyanyu/shici-skill.git'
```

成功后可仅为当前 checkout 配置 `core.sshCommand`。不修改全局配置、不读取私钥，不打印凭据。SSH 不可用时可使用已有 HTTPS 凭据访问同一仓库；没有访问权限时如实报告，不绕过认证。

其他使用者 fork 后可以维护自己的版本；除非得到其明确指令，不自动修改发布地址，也不认为本说明授权向原作者仓库推送。
