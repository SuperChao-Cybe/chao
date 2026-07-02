---
name: ipguard-download-export-encrypt
description: 处理金蝶/苍穹/星空项目中的 IP-guard 预览加密、下载加密、导出加密、本地维护工具、Jar 发布与排障；适用于需要修改代码、做部署脚本、检查日志或整理客户局域网维护流程的场景。
---

# IP-guard 下载/导出加密

## 适用场景

- 给附件预览加密、下载加密、列表导出加密
- 维护或修改本地一体化维护工具
- 排查 Jar 发布、旧包残留、Pod 版本不一致、SSH 发布失败
- 处理 IP-guard 配置、开关、版本记录、部署手册

## 工作方式

1. 先区分需求是“改代码”还是“做部署/排障”。
2. 优先查看现有模块：`java/zssy/zssy-conm-ext`、`java/zssy/docs`、`ops/ipguard`。
3. 修改要收敛，优先复用现有 `IpGuardSdkClientImpl`、`FileServiceExt`、列表/表单插件和维护工具。
4. 若涉及客户侧工具，默认输出可直接给客户使用的说明、脚本和打包结果。
5. 若涉及生产环境，先确认目标是：预览加密、下载加密、导出加密中的哪一项，避免误改链路。

## 关键原则

- 不主动读取数据库。
- 不输出或硬编码敏感信息。
- 不做无关重构，只改必须的点。
- 发现旧 Jar、旧 Pod、旧配置时，优先给出清理和发布顺序。

## 常用参考位置

- `java/zssy/README.md`
- `java/zssy/docs/销售合同IP-guard对接-部署说明.md`
- `java/zssy/zssy-conm-ext/src/main/java/zssy/conm/ext/ipguard/`
- `ops/ipguard/`（若存在）
## 使用说明

- 参考 [references/usage-guide.md](references/usage-guide.md)
