# 金蝶 AI 星空旗舰版 IP-guard 加密交付仓库

这是一个面向 **金蝶 AI 星空旗舰版** 的 IP-guard 加密方案交付仓库。

它对应的业务目标，不是普通网站插件，而是给金蝶 AI 星空旗舰版附件链路增加以下能力：

- 外网附件预览加密
- 外网附件下载加密
- 附件或单据导出加密
- 内外网链路区分处理，避免内网预览被误加密后出现乱码
- 发布、开关、排障、版本说明标准化

## 适用系统

适用于以下场景：

- 金蝶 AI 星空旗舰版
- 基于苍穹 / Cosmic 技术栈的附件预览、下载、导出链路
- 需要与 IP-guard 做集成的 ERP 文件安全场景

如果你的系统不是金蝶 AI 星空旗舰版相关环境，这个仓库里的内容通常不直接适用。

## 使用后会有什么效果

在业务系统正确接入并发布对应 Jar、配置好运行时开关后，最终效果通常是：

1. 外网用户访问附件预览时，可按配置走 IP-guard 加密链路。
2. 外网用户下载附件时，可按配置返回加密后的文件。
3. 单据导出或附件导出时，可按配置执行加密。
4. 内网访问可根据策略保持正常预览，避免未保存附件或内网链路被错误加密。
5. 运维和实施人员可以按统一流程发布、核验、回看版本记录和排障。

## 这个仓库里包含什么

这个仓库目前主要承载两类内容：

### 1. 金蝶 AI 星空旗舰版 IP-guard 方案说明和交付资料

包括：

- 方案使用说明
- 发布说明
- GitHub 分发说明
- 交付包目录清单

### 2. 智能体可复用的技能插件包

仓库内同时提供了一个可安装的 Codex marketplace / plugin 包，用于让智能体快速理解并处理：

- 预览加密
- 下载加密
- 导出加密
- Jar 发布
- 运行时开关
- 旧 Pod 清理
- 生产排障

## 不是只给 Codex 用

这个仓库 **不应被理解为只能给 Codex 安装**。

更准确地说：

- 对 **Codex** 来说，它可以直接按 marketplace 方式安装。
- 对 **其他智能体** 来说，可以直接读取仓库里的技能说明、发布文档和参考资料，再按各自平台支持的方式导入或适配。
- 对 **实施、运维、二开人员** 来说，也可以直接把这个仓库当成交付文档仓库使用。

也就是说，**Codex 安装只是其中一种消费方式，不是唯一使用方式。**

## Codex 安装方式

```powershell
codex plugin marketplace add https://github.com/SuperChao-Cybe/chao.git --ref main
codex plugin add ipguard-download-export-encrypt@ipguard-marketplace
```

## 非 Codex 使用方式

如果不是用 Codex，也可以这样使用：

1. 直接下载这个 GitHub 仓库源码或 ZIP。
2. 阅读仓库内说明文档，理解金蝶 AI 星空旗舰版的接入目标、发布方式和排障步骤。
3. 按你自己的智能体平台、知识库平台或实施流程，复用其中的说明、技能和参考资料。

## 仓库目录

```text
<repo-root>/
  .agents/
    plugins/
      marketplace.json
  plugins/
    ipguard-download-export-encrypt/
      .codex-plugin/
        plugin.json
      README.md
      docs/
      skills/
```

## 核心文档

- `plugins/ipguard-download-export-encrypt/README.md`
- `plugins/ipguard-download-export-encrypt/docs/github-publish-guide.md`
- `plugins/ipguard-download-export-encrypt/skills/ipguard-download-export-encrypt/SKILL.md`

## 当前标识

- marketplace：`ipguard-marketplace`
- plugin：`ipguard-download-export-encrypt`
