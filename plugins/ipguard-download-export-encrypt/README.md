# 金蝶 AI 星空旗舰版 IP-guard 加密技能包

这是一个围绕 **金蝶 AI 星空旗舰版** IP-guard 集成方案整理的技能包与发布包。

它面向的不是通用网站文件下载场景，而是金蝶 AI 星空旗舰版附件、预览、下载、导出链路的安全加密需求。

## 适用系统

- 金蝶 AI 星空旗舰版
- 基于苍穹 / Cosmic 的附件服务链路
- 需要对接 IP-guard 的文件安全控制场景

## 目标效果

使用这套方案时，关注的是以下业务效果：

- 外网附件预览可加密
- 外网附件下载可加密
- 导出文件可加密
- 内网链路按策略放行，避免预览乱码
- 发布和排障过程可标准化

## 这个目录包含什么

```text
ipguard-download-export-encrypt/
  .codex-plugin/plugin.json
  README.md
  docs/github-publish-guide.md
  skills/ipguard-download-export-encrypt/
```

其中：

- `skills/` 是智能体可复用的技能说明
- `docs/` 是发布到 GitHub 和交付给别人使用的说明
- `.codex-plugin/` 是 Codex 可识别的插件描述

## 不只限 Codex

这个目录虽然带有 Codex 插件结构，但用途不只限于 Codex：

- Codex 可以直接安装
- 其他智能体可以直接读取技能和参考文档做适配
- 实施、运维、开发人员可以把它当作交付说明包使用

## Codex 安装方式

```powershell
codex plugin marketplace add https://github.com/SuperChao-Cybe/chao.git --ref main
codex plugin add ipguard-download-export-encrypt@ipguard-marketplace
```

## 参考文档

- `docs/github-publish-guide.md`
- `skills/ipguard-download-export-encrypt/references/usage-guide.md`
- `skills/ipguard-download-export-encrypt/references/release-package-checklist.md`
