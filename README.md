# Work Skills

这是 Chad Liu 维护的本地 Codex/OpenClaw skills 仓库。每个 skill 放在独立目录中，并在自己的目录下维护使用说明。

## 仓库结构

```text
.
├── README.md
├── LICENSE
├── RELEASE_NOTES.md
└── tech-trend-radar
```

## 可用 Skills

| Skill | 用途 | 文档 |
|-------|------|------|
| `tech-trend-radar` | 基于可信来源、模型榜单、GitHub 热度和公司策略变化，生成技术与市场趋势报告。 | [`tech-trend-radar/README.md`](tech-trend-radar/README.md) |

## 仓库约定

- 根目录 README 只放仓库级说明和 skill 索引。
- 发布说明记录在 [`RELEASE_NOTES.md`](RELEASE_NOTES.md)。
- 每个 skill 的使用示例、输出格式、维护说明放在对应目录下。
- 新增 skill 时，使用顶层目录，并至少包含 `SKILL.md` 和本地 `README.md`。

## 维护

提交文档变更前，先检查工作区状态：

```bash
git status --short
```
