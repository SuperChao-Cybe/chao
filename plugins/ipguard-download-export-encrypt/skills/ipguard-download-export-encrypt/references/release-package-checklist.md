# IP-guard Skill 发布包目录清单

## 发布包建议目录

```text
ipguard-download-export-encrypt/
├─ SKILL.md
├─ agents/
│  └─ openai.yaml
├─ references/
│  └─ usage-guide.md
├─ docs/
│  └─ (可选) 客户维护手册、部署说明、常见问题
└─ assets/
   └─ (可选) 图标、截图、模板
```

## 最小必需文件

- `SKILL.md`
- `agents/openai.yaml`
- `references/usage-guide.md`

## 推荐一起打包

- 本地维护工具
- Jar 发布脚本
- 部署说明
- 常见问题排查记录
- 最近一次发布的 Jar 名和 MD5

## 交付前检查

- `SKILL.md` 在根目录
- `agents/openai.yaml` 能正常读取
- `references/usage-guide.md` 可直接给别人看
- 目录名保持 `ipguard-download-export-encrypt`
- 没有把密码、token、密钥写进文档

## 发给别人时怎么说

把整个目录复制给对方，让对方放到自己的 Codex skills 目录下，然后重启 Codex 或刷新技能列表即可。
