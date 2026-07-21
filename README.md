# AI Berkshire: 价值投资深度研究系统

> Berkshire Hathaway-style investment research system for A-share stocks.

基于巴菲特、芒格、段永平、李录四位大师方法论的结构化投研工具集。

## v2.3 更新（2026-07-21）

### 新增：分析顺序方法论
- **资金面信号≠基本面真相**：五标的实战验证——汇川3.5亿资金流入是"诱饵"，Q1净利-24%
- **正确的分析链**：物理瓶颈 → 财务穿透 → 资金面 → 技术择时 → 执行层门禁
- **段永平裁决优先级**：价格不对不买（即使总分最高）

### 新增避坑规则
- Forward PE必须计算（增速>50%时TTM PE失真）
- 毛利率趋势 > 毛利率绝对值
- 低PE可能是价值陷阱（利润暴跌后分母缩小）

## 四大师框架

| 大师 | 维度 | 核心标准 |
|------|------|--------|
| 巴菲特 | 生意质地 | ROE>15%? CF>NI? 分红? |
| 芒格 | 护城河 | 技术壁垒? 定价权? Lollapalooza? |
| **段永平** ⭐ | 价格/A股 | PEG<1? 52W<60%? **本分?** |
| 李录 | 增长/长期 | CAGR? ROIC>WACC? |

> ⚠️ 四大师冲突时，以段永平（本分/能力圈）为A股最高权重。

## 使用方法

将本目录放入 `~/.claude/skills/ai-berkshire/`，Claude Code 会自动识别。

## 数据源

- tushareMcp: 258个工具
- a-stock-data: 7层28端点
- 万讯智研知识星球

## 诚实边界

- 四维评分回测胜率45%，仅辅助排序
- 非投资建议，仅研究辅助工具

---

*Created with [女娲 · Skill造人术](https://github.com/alchaincyf/nuwa-skill)*