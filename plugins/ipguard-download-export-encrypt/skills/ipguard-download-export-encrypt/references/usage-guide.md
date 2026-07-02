# IP-guard 下载/导出/预览加密 Skill 使用说明

## 这个 skill 适合干什么

这个 skill 主要用来处理金蝶/苍穹/星空项目里的 IP-guard 相关工作，重点是三类链路：

- 预览加密
- 下载加密
- 导出加密

同时也适合做这些配套工作：

- 修改 Java 插件或文件服务扩展
- 处理本地维护工具
- 发布 Jar
- 排查旧 Pod、旧包、版本不一致
- 整理部署说明和客户交付手册

## 什么时候用

适合直接说这些话时用：

- “帮我把附件预览加密加上。”
- “下载没有加密，帮我排查。”
- “导出 Excel 也要加密。”
- “客户局域网电脑上要一个维护工具，别让客户敲命令。”
- “Jar 发布后还有旧 Pod，帮我处理掉。”
- “把这个功能做成可交付的 skill / 维护说明。”

## 怎么用

你可以直接这样发指令：

- `Use $ipguard-download-export-encrypt to add preview/download/export encryption.`
- `Use $ipguard-download-export-encrypt to troubleshoot old pods after Jar publish.`
- `Use $ipguard-download-export-encrypt to prepare a customer-side maintenance tool.`

中文也可以直接说：

- “用这个 skill 帮我检查预览加密为什么没生效。”
- “用这个 skill 帮我整理客户局域网维护工具的部署方式。”
- “用这个 skill 帮我把下载加密和导出加密一起补齐。”

## 别人怎么安装

把整个 skill 目录复制到对方机器的 Codex skills 目录里即可。

Windows 常见路径：

`C:\Users\<用户名>\.codex\skills\ipguard-download-export-encrypt`

如果对方是 macOS / Linux，一般放到：

`~/.codex/skills/ipguard-download-export-encrypt`

安装后保留这几个文件：

- `SKILL.md`
- `agents/openai.yaml`
- `references/usage-guide.md`

然后让对方重新打开 Codex，或者刷新技能列表。

如果对方用的是 Codex 桌面端，通常重启应用后就会重新扫描技能目录。
如果还是没出现，就确认目录名是不是 `ipguard-download-export-encrypt`，以及 `SKILL.md` 是否还在根目录。

## 别人怎么使用

两种方式都可以：

1. 直接在聊天里写明确指令，例如：
   - `Use $ipguard-download-export-encrypt to troubleshoot download encryption.`
   - `Use $ipguard-download-export-encrypt to add preview encryption.`
2. 直接说中文，例如：
   - “用这个 skill 帮我排查下载加密。”
   - “用这个 skill 帮我处理预览加密。”

因为这个 skill 已经允许自动触发，所以只要话题相关，Codex 也可能自动用上它。

## 我会优先怎么做

通常会按这个顺序处理：

1. 先确认你要的是预览、下载、导出中的哪一条。
2. 再看当前代码和部署目录是否已经有相关实现。
3. 只改必要代码，不乱扩展。
4. 如果涉及部署，会优先处理旧 Jar、旧 Pod、配置不一致这些问题。
5. 如果需要给客户交付，会补维护说明、分发方式和检查步骤。

## 你要把这个 skill 发给别人，怎么做

最简单的方式就是把整个目录发过去：

`C:\Users\LiangChao.Weng\.codex\skills\ipguard-download-export-encrypt`

别人拿到后，放到自己的 Codex skills 目录下就能用。目录里至少要有：

- `SKILL.md`
- `agents/openai.yaml`

如果你还想让别人更容易上手，可以再附上：

- 一份部署说明
- 一份客户维护手册
- 你们项目里的 Jar 发布脚本或打包包

## 建议的交付内容

如果你准备正式发出去，建议一起打包这几样：

- skill 目录本体
- 本地维护工具
- Jar 发布脚本
- 部署说明
- 常见问题排查记录

这样别人拿到后，不用再翻散文件。

## 发布包目录清单

- 参考 [references/release-package-checklist.md](references/release-package-checklist.md)
