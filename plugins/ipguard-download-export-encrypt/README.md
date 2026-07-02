# IP-guard 加密技能插件

这是一个可直接发布到 GitHub 的 Codex 插件包，用于处理 IP-guard 预览加密、下载加密、导出加密，以及相关发布排障。

## 目录说明

仓库里必须保留以下结构：

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
      skills/
        ipguard-download-export-encrypt/
          SKILL.md
          agents/
            openai.yaml
          references/
```

## GitHub 发布

发布到 GitHub 时，至少要提交这两部分内容：

- `.agents/plugins/marketplace.json`
- `plugins/ipguard-download-export-encrypt/**`

推荐做法：

1. 单独建一个干净仓库，只放这套插件发布包。
2. 不要把客户密码、SSH 口令、密钥、token、内网地址清单提交到仓库。
3. 每次更新技能后，先本地校验，再推送到 GitHub。

详细步骤见：

- [GitHub 发布与安装说明](./docs/github-publish-guide.md)

## 别人如何安装

先添加 marketplace：

```powershell
codex plugin marketplace add https://github.com/<owner>/<repo> --ref main
```

再安装插件：

```powershell
codex plugin add ipguard-download-export-encrypt@ipguard-marketplace
```

如果是私有仓库，可以改用 SSH Git 地址：

```powershell
codex plugin marketplace add git@github.com:<owner>/<repo>.git --ref main
```

## 安装后怎么用

可直接在对话里提出这类任务：

- 给 ERP 附件下载加 IP-guard 加密
- 排查公网预览加密但下载未加密
- 实现导出文件加密
- 整理 IP-guard 本地维护工具发布包

也可以显式调用技能名：

```text
Use $ipguard-download-export-encrypt to implement or troubleshoot IP-guard preview/download/export encryption.
```

## 当前名称

- marketplace：`ipguard-marketplace`
- plugin：`ipguard-download-export-encrypt`
