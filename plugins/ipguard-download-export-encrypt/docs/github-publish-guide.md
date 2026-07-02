# GitHub 发布与安装说明

## 1. 目的

这份说明用于把 `ipguard-download-export-encrypt` 插件发布到 GitHub，并让其他 Codex 智能体从 GitHub 安装使用。

## 2. 发布前检查

发布前先确认仓库内有以下内容：

```text
<repo-root>/
  .agents/plugins/marketplace.json
  plugins/ipguard-download-export-encrypt/.codex-plugin/plugin.json
  plugins/ipguard-download-export-encrypt/skills/ipguard-download-export-encrypt/SKILL.md
```

重点检查：

- `marketplace.json` 里插件名是 `ipguard-download-export-encrypt`
- `plugin.json` 里插件名也是 `ipguard-download-export-encrypt`
- 没有提交密码、token、私钥、客户环境配置

## 3. 推荐仓库方式

推荐单独建立一个 GitHub 仓库，例如：

```text
ipguard-download-export-encrypt-marketplace
```

原因：

- 仓库内容干净，便于公开或共享
- 不会把业务源码和插件发布包混在一起
- 后续版本管理更清晰

## 4. 推送到 GitHub

### 4.1 新建远端仓库

在 GitHub 上创建一个空仓库，不要预置敏感文件。

### 4.2 推送本地内容

把以下目录和文件推送到仓库：

- `.agents/plugins/marketplace.json`
- `plugins/ipguard-download-export-encrypt/`

如果仓库根目录还需要说明文档，可把当前插件目录下的 `README.md` 复制为仓库根 README。

## 5. 其他人如何安装

### 5.1 公共 GitHub 仓库

先添加 marketplace：

```powershell
codex plugin marketplace add https://github.com/<owner>/<repo> --ref main
```

再安装插件：

```powershell
codex plugin add ipguard-download-export-encrypt@ipguard-marketplace
```

### 5.2 私有 GitHub 仓库

如果是私有仓库，建议使用 SSH Git 地址，并提前在本机配置好 GitHub 访问权限：

```powershell
codex plugin marketplace add git@github.com:<owner>/<repo>.git --ref main
codex plugin add ipguard-download-export-encrypt@ipguard-marketplace
```

## 6. 后续更新怎么发

插件内容修改后，按下面顺序处理：

1. 更新 `skills/`、`README.md`、相关说明文档
2. 本地做一次插件校验
3. 提交 Git
4. 推送 GitHub
5. 使用方执行 marketplace 刷新

刷新命令：

```powershell
codex plugin marketplace upgrade
```

必要时可重新安装插件：

```powershell
codex plugin add ipguard-download-export-encrypt@ipguard-marketplace
```

## 7. 常见问题

### 7.1 为什么别人安装不到插件

常见原因：

- 仓库里缺少 `.agents/plugins/marketplace.json`
- `marketplace.json` 的 `source.path` 不对
- 插件目录名和 `plugin.json` 里的 `name` 不一致
- GitHub 仓库没推完整

### 7.2 为什么建议单独建仓库

因为这是“插件分发包”，不是业务工程本体。单独仓库更适合给别人直接安装，也更适合开源或对外共享。

### 7.3 发布时最该防什么

最重要的是不要把以下内容推上去：

- SSH 用户名密码
- 二次验证口令
- token
- 客户内网地址清单
- 客户 jar 包和环境私有配置

## 8. 当前插件标识

- marketplace：`ipguard-marketplace`
- plugin：`ipguard-download-export-encrypt`
