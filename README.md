# hs-founder-skill：创始人 IP 内容系统

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

## 陌生电脑一句话安装

前提：电脑装好 git 和 Codex CLI（或 Claude Code）。启动 AI 后原样粘贴：

> 从 https://github.com/handsomeng/hs-founder-skill 克隆仓库，把里面的 vault-template 文件夹复制到我的家目录并改名为「我的IP」（不要放进 Downloads、Documents、Desktop），在这个新文件夹里执行 git init 并完成首次提交，然后删掉克隆下来的临时仓库。装完告诉我下一步怎么开始。

装完退出会话，`cd ~/我的IP` 后重新启动 AI（必须从这个文件夹启动才能认到路由和 skill），说「开始采访」。
