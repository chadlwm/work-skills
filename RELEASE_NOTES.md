# Release Notes

## V1.3.0 2026-04-19

聚合提交：

- `3c52423` feat: track ai people signals
- `d7d2592` feat: track major ai product launches

### 新增

- 新增 AI 领域知名人物动态追踪，例如 Andrej Karpathy、Ilya Sutskever、Fei-Fei Li、Yann LeCun、Geoffrey Hinton、Andrew Ng 等。
- 报告模板新增 `AI People Watch`，记录人物、机构、事件、领域、周期、状态和影响。
- 新增重磅 AI 产品发布追踪，覆盖 Claude Design、ChatGPT apps、Gemini 产品、Microsoft Copilot 产品面、agent workspace 和 coding workspace。
- 报告模板新增 `Major Product Launch Watch`，要求输出产品形态、发布类型、核心工作流变化、影响用户、竞品对比和建议动作。
- 事件 payload 新增 `majorProductLaunches` 字段，关键词配置新增 `Major Product Launches`。

### 改进

- 人物动态只收录公开、可溯源、对研究、产品或公司策略有影响的事件。
- 重磅产品发布需说明产品形态、核心工作流变化、影响用户、竞品对比和建议动作。

## V1.2.0 2026-04-17

聚合提交：

- `6b74bb1` localize readme docs

### 文档

- 将根目录 `README.md` 和 `tech-trend-radar/README.md` 改为中文说明。
- 根 README 保留仓库级说明和 skill 索引。
- `tech-trend-radar/README.md` 保留该 skill 的能力范围、使用示例、研究来源、报告质量规则和输出路径。

## V1.1.0 2026-04-16

聚合提交：

- `064ac55` track gemma model trends

### 新增

- 将 Google Gemma 系列纳入模型趋势、open-weight 模型和公司策略追踪。
- 在模型 reranking 和关键词配置中补充 Gemma 相关检查项。

### 文档

- 更新 `tech-trend-radar/README.md` 中的 Gemma 相关说明。

## V1.0.0 2026-04-15

聚合提交：

- `7443242` Initial commit
- `cea8680` init project
- `5feb4f4` update tech trend radar
- `45d01d1` add model ranking
- `cde47e2` doc: update readme
- `70a5753` feat: uniform path prefix
- `77c8b86` feat: large Agent Platform Ecosystem scope
- `8b2bdb6` feat: update strategy
- `5030724` feat: add domestic models

### 新增

- 初始化仓库，添加基础 `README.md` 和 `LICENSE`。
- 初始化 `tech-trend-radar` skill，用于生成技术、AI、SaaS、开发者工具、云、安全、创业公司、融资和监管趋势报告。
- 新增 `AGENTS.md` contributor guide。
- 新增模型 reranking 追踪，覆盖 LMArena/Text Arena、Artificial Analysis、LiveBench、SWE-bench、OpenRouter 等榜单。
- 新增国内模型和公司趋势追踪，覆盖 Qwen/通义千问、GLM/智谱、DeepSeek、Kimi、ERNIE/文心、Hunyuan/混元、Doubao/豆包。
- 新增 `tech-trend-radar/README.md`，将 skill 自身说明放到 skill 目录下。

### 改进

- 扩展 `tech-trend-radar` 的研究流程、报告结构、信号评分、证据、行动项和分类深挖要求。
- 月报和季报必须包含当前 Top 10 模型排名表，并解释核心变化。
- 增强公司策略追踪，要求月报覆盖 OpenAI、Anthropic、Alibaba Qwen、Zhipu AI 等重点公司。
- 将监控范围扩展为通用的 `Agent Platform Ecosystem`，覆盖 Anthropic、OpenAI、Alibaba Qwen、Zhipu GLM、Google Gemini/Gemma、GitHub Copilot、MCP、OpenClaw、HarnessClaw 等生态信号。
- 统一报告路径前缀为 `tech-trend-radar-*`，例如 `memory/research/tech-trend-radar-YYYY-WXX.md`。
