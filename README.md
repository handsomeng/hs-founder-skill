# hs-founder-skill：创始人 IP 内容系统

## 给 AI 的安装指令（用户说「安装 hs-founder-skill」时照此执行）

用户只需要说：**「安装 https://github.com/handsomeng/hs-founder-skill 并配置我的 Obsidian 知识库」**。你（AI）看到这句话后自动完成以下全部步骤，过程中不问技术问题：

1. 问用户一个问题：「知识库文件夹想叫什么名字？（直接回车默认叫 我的IP）」
2. `git clone https://github.com/handsomeng/hs-founder-skill.git /tmp/hs-founder-skill`
3. 把 `/tmp/hs-founder-skill/vault-template` 复制为 `~/<用户起的名字>`（家目录直接子目录，禁止放 Downloads / Documents / Desktop，macOS 会拦 AI 读写）
4. 在新文件夹里 `git init && git add -A && git commit -m "init"`
5. 删除 `/tmp/hs-founder-skill`
6. 用大白话告诉用户剩下两个必须人工做的动作：
   - 打开 Obsidian，「打开文件夹作为仓库」，选刚建的文件夹
   - 退出当前 AI 会话，进入该文件夹重新启动（`cd ~/文件夹名` 后运行 codex 或 claude），然后说「开始采访」

给不懂技术的老板搭的 AI 内容流水线。四个模块：采访建档 → 选题提取 → 脚本框架 → 审稿。skill 直接内置在知识库文件夹里，AGENTS.md（Codex）和 CLAUDE.md（Claude Code）双路由，零安装依赖。

## 明天装机步骤（操作人：瀚森哥）

1. 老板电脑装好 Obsidian 和 Codex CLI（或 Claude Code）
2. 把 `vault-template/` 整个文件夹拷到老板的**家目录直接子目录**，改名，例如 `~/张总IP/`（别放 Downloads / Documents / Desktop，macOS 会拦 AI 读写）
3. Obsidian 里「打开文件夹作为仓库」，选这个文件夹
4. 进文件夹初始化 git 保底：`cd ~/张总IP && git init && git add -A && git commit -m "init"`（有条件再接私有 remote）
5. 在这个文件夹里启动 `codex`（或 `claude`），对它说：**开始采访**
6. 采访当场做完（约 40 到 60 分钟），生成人设档案，让老板确认
7. 现场跑通最短链路：随便聊十分钟让 AI 提取选题 → 定一个 → 出框架。老板当天拿到第一个能拍的框架

## 交给老板的口令卡（抄给他，四句够用）

- **开始采访**：第一次用 / 每月说「更新人设」补充近况
- **提取选题**：素材扔进 01-收件箱后说这句；收件箱空着也可以直接跟 AI 聊，它从聊天里挖
- **出框架**：从选题库挑一个，AI 出骨架，他填【留白】
- **审稿**：写完粘给 AI，它出修改清单，不代写

## 和老板约定的一件事（系统成败所在）

收件箱怎么喂：每天把微信语音转文字 / 备忘录随想 / 会议记录粘进 `01-收件箱/当天日期.md`。谁来做（他自己或助理）、什么时候做，明天当面定下来。

## 结构

```
vault-template/
├── AGENTS.md / CLAUDE.md   AI 操作手册 + 口令路由（两文件内容相同）
├── skills/                  四个模块的详细执行手册
├── 00-人设中枢/ → 05-数据复盘/   内容流水线目录，各有 _说明.md
```

改 skill 逻辑直接编辑 `skills/*/SKILL.md`，改完 git commit。

## 陌生电脑安装

前提：电脑装好 git 和 Codex CLI（或 Claude Code）。启动 AI，说一句：

> 安装 https://github.com/handsomeng/hs-founder-skill 并配置我的 Obsidian 知识库

AI 会读到本 README 开头的安装指令自动完成，最后引导你打开 Obsidian 和重启会话。
