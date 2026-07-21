---
name: ai-berkshire
description: Berkshire Hathaway-style investment research system — multi-master deep analysis, earnings review, industry research, management assessment, portfolio review.
version: 2.4
metadata:
  hermes:
    tags: [investment, berkshire, buffett, munger, value-investing, deep-research, portfolio]
    related_skills: [a-stock-deep-research, a-stock-data]
---

# AI Berkshire: 价值投资深度研究系统 v2.4 | 更新：2026-07-21

> **v2.4 变更**（基于2026-07-21完整五标的实战：东方电缆/菲利华/生益科技/汇川/上海贝岭）：
> - 新增「财务穿透标准流程 Phase 2.5」——income→fina_indicator→forecast→report_rc的4步验证链
> - 新增「段永平裁决 Phase 2 Step 8」——正式化为A股最终裁决步骤
> - 新增4条避坑规则（report_rc时效/多源交叉/万讯帖数/income字段稀疏）
> - 修复v2.3中段永平裁决表的断裂问题

基于巴菲特、芒格、段永平、李录四位大师方法论的结构化投研工具集。

## 核心方法论

### 分析顺序（不可跳过）

```
① 物理瓶颈定位 → ② 财务穿透验证 → ③ 资金面信号 → ④ 技术择时 → ⑤ 执行层门禁
```

> ⚠️ **核心教训**：资金面信号≠基本面真相。汇川3.5亿资金流入是诱饵——Q1净利-24%+FCFF-14亿。

### 段永平裁决（A股最终裁决者）

```
段永平评分 ≥ 7？
├─ YES → 检查巴菲特(ROE>15%? FCFF正?) + 李录(增长趋势?) → ✅
└─ NO → ❌ 价格不对，不入场（即使总分最高）
```

| 标的 | 综合 | 段永平 | 裁决 |
|------|:---:|:---:|------|
| 东方电缆(持仓) | 7.25 | **8** | ✅通过 |
| 生益科技 | **7.5** | 5 | ❌价格不对 |
| 菲利华 | 6.75 | 5 | ❌价格不对 |
| 汇川技术 | 6.25 | 6 | ⚠️待定 |
| 上海贝岭 | 3.75 | 3 | ❌否决 |

### 财务穿透判定矩阵

| 信号 | 判定 | 案例 |
|------|------|------|
| ROE>15% + FCFF正 + 利润正增长 | ✅ 健康 | 东方电缆 |
| ROE>15% + 利润暴跌但H1预告反转 | ⚠️ 待确认 | 生益科技 |
| 利润负增长 + FCFF负 | 🔴 恶化 | 汇川/贝岭 |
| 利润暴跌80% + 毛利<30% | 🔴🔴 价值陷阱 | 上海贝岭 |

## 四大师框架

| 大师 | 维度 | 核心标准 | A股权重 |
|------|------|---------|:------:|
| 巴菲特 | 生意质地 | ROE>15%? CF>NI? 分红? | 中 |
| 芒格 | 护城河 | 技术壁垒? 定价权? Lollapalooza? | 中 |
| **段永平** | 价格/A股 | PEG<1? 52W<60%? **本分?** | **最高** ⭐ |
| 李录 | 增长/长期 | CAGR? ROIC>WACC? | 第二 |

## 关键避坑清单

- PE(TTM)>300x + 净利率<3% = 题材炒作
- 52W位置必须前复权（tushare adj_factor）
- 先看扣非再看表报
- 经营CF vs 净利背离是红旗
- **资金面信号≠基本面真相**（v2.3核心教训）
- **Forward PE必须计算**（v2.3，增速>50%时TTM失真）
- **毛利率趋势>绝对值**（v2.3）
- **低PE可能是价值陷阱**（v2.3）
- **report_rc时效陷阱**（v2.4，可能只返回旧报告）
- **多源交叉验证**（v2.4，tushare+global-stock-data+CRW+wigolo）
- **income字段稀疏**（v2.4，补查fina_indicator）
- **万讯帖数≠选股因子**（r=-0.014）

## 使用方法

```bash
git clone https://github.com/sermady/ai-berkshire.git ~/.claude/skills/ai-berkshire
```

## 数据源

- tushareMcp: 258个工具（行情/财务/资金/龙虎榜/融资/股东/解禁/筹码）
- a-stock-data: 7层28端点（mootdx+腾讯+东财+同花顺+巨潮）
- global-stock-data: 美股港股（Sina+Yahoo+SEC EDGAR）
- 万讯智研知识星球: 7935帖+附件
- lan-web-tools: CRW+Firecrawl OSS+Stealth三层爬虫

## 诚实边界

- 四大师方法论为A股适配而非原创设计
- 四维评分回测胜率45%，仅辅助排序
- 三情景估值缺乏概率加权
- **非投资建议**，仅研究辅助工具

---

*完整380行SKILL.md含：10步采集流程、19项增强数据源API、子技能索引、特殊场景流程。本地安装版包含全部细节。*

*Created with [女娲 · Skill造人术](https://github.com/alchaincyf/nuwa-skill)*
