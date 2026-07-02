# GitHub 发布与使用说明

## 1. 这是什么

这是一个围绕 **金蝶 AI 星空旗舰版** IP-guard 加密方案整理出来的 GitHub 分发包。

它的重点不是单纯让 Codex 安装，而是把以下内容标准化交付出去：

- 金蝶 AI 星空旗舰版附件预览加密说明
- 下载加密说明
- 导出加密说明
- 技能包和参考资料
- GitHub 分发方式

## 2. 适用对象

适合以下角色使用：

- 金蝶 AI 星空旗舰版实施人员
- 运维人员
- 二开开发人员
- 需要复用这套知识包的智能体

## 3. 发布前检查

发布前先确认仓库内有以下内容：

```text
<repo-root>/
  .agents/plugins/marketplace.json
  plugins/ipguard-download-export-encrypt/.codex-plugin/plugin.json
  plugins/ipguard-download-export-encrypt/skills/ipguard-download-export-encrypt/SKILL.md
```

重点检查：

- `marketplace.json` 中插件名为 `ipguard-download-export-encrypt`
- `plugin.json` 中插件名也为 `ipguard-download-export-encrypt`
- 没有提交密码、token、私钥、客户环境配置

## 4. 发布到 GitHub

建议单独建立一个干净仓库，只放这套交付包。

需要提交的核心内容：

- `.agents/plugins/marketplace.json`
- `plugins/ipguard-download-export-encrypt/`

## 5. 怎么使用

### 5.1 Codex 使用方式

```powershell
codex plugin marketplace add https://github.com/<owner>/<repo> --ref main
codex plugin add ipguard-download-export-encrypt@ipguard-marketplace
```

### 5.2 非 Codex 使用方式

不是 Codex 也可以使用：

1. 直接下载仓库源码或 ZIP。
2. 阅读 `README.md`、`SKILL.md` 和 `references/` 下的资料。
3. 按自己的智能体平台、知识平台或实施流程导入、改写或复用。

## 6. 使用后的业务理解

这套资料服务的核心目标是：

- 给金蝶 AI 星空旗舰版文件链路增加 IP-guard 加密能力
- 让外网预览、外网下载、导出可按策略安全控制
- 让内网链路尽量保持正常使用体验
- 让发布、回滚、核验、排障有统一说明

## 7. 当前标识

- marketplace：`ipguard-marketplace`
- plugin：`ipguard-download-export-encrypt`
