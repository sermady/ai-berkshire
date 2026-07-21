---
name: ai-berkshire
description: Berkshire Hathaway-style investment research system — multi-master deep analysis, earnings review, industry research, management assessment, portfolio review.
version: 2.3
metadata:
  hermes:
    tags: [investment, berkshire, buffett, munger, value-investing, deep-research, portfolio]
    related_skills: [a-stock-deep-research, a-stock-data]
---

# AI Berkshire: 价值投资深度研究系统 v2.3 | 更新：2026-07-21

基于巴菲特、芒格、段永平、李录四位大师方法论的结构化投研工具集。对 $ARGUMENTS 指定的公司执行系统化投资分析。

## v2.3 更新要点

### 新增：分析顺序方法论（2026-07-21五标的实战验证）

> ⚠️ **本轮最重要教训：资金面信号≠基本面真相。** 汇川技术3.5亿机构资金流入是"诱饵信号"——财务穿透后发现Q1净利-24%+FCFF-14亿。如果不穿透到财务报表，资金流入会误导买入一个基本面恶化的公司。

**正确的分析顺序（不可跳过）**：
```
① 物理瓶颈定位（Serenity镜片层/陈立武模型6）
② 财务穿透验证（income/fina_indicator/forecast）
③ 资金面信号（确认/证伪第②步）
④ 技术位置（择时）
⑤ 执行层门禁（规则链）
```

### 新增避坑规则
- **资金流入≠基本面好转**：moneyflow净流入可能是基本面恶化期的"左侧抄底"诱饵
- **Forward PE必须计算**：增速>50%时TTM PE分母滞后。生益科技TTM PE 89.9x → Forward PE 46.8x
- **毛利率趋势>绝对值**：生益26.5%→28.1%（上升=定价权增强）vs 贝岭利润暴跌80%（恶化）
- **低PE可能是价值陷阱**：上海贝岭PE 67x是利润暴跌80%后分母缩小被推高

### 段永平裁决优先级（v2.3强化）

```
段永平评分 ≥ 7？
├─ YES → 检查巴菲特(ROE>15%?) + 李录(增长趋势?)
│        → 都通过 → ✅ 研究层认可
└─ NO → ❌ 价格不对，不入场（即使总分最高）
```

五标的验证：东方电缆(段8✅) > 生益(段5❌价格) > 菲利华(段5❌) > 汇川(段6⚠️) > 贝岭(段3❌)

## 完整文档

完整SKILL.md（含10步采集流程、19项增强数据源、避坑清单、子技能索引）请参见本地安装版本。

## 使用方法

```bash
# 安装
git clone https://github.com/sermady/ai-berkshire.git ~/.claude/skills/ai-berkshire

# 使用（Claude Code内）
/ai-berkshire 300458      # 单只标的
/ai-berkshire 300458,002922  # 多标的横向对比
```

## 四大师框架

| 大师 | 维度 | 核心标准 | A股权重 |
|------|------|---------|:------:|
| 巴菲特 | 生意质地 | ROE>15%? CF>NI? 分红? | 中 |
| 芒格 | 护城河 | 技术壁垒? 定价权? Lollapalooza? | 中 |
| **段永平** | 价格/A股 | PEG<1? 52W<60%? **本分?** | **最高** ⭐ |
| 李录 | 增长/长期 | CAGR? ROIC>WACC? | 第二 |

## 数据源

- **tushareMcp**: 258个工具（行情/财务/资金/龙虎榜/融资/股东/解禁/筹码）
- **a-stock-data**: 7层28端点（mootdx+腾讯+东财+同花顺+巨潮）
- **万讯智研知识星球**: 产业信息+投资框架（7935帖+附件）
- **global-stock-data**: 美股港股（Sina+Yahoo+SEC EDGAR）

## 关键避坑清单（摘要）

- PE(TTM)>300x + 净利率<3% = 题材炒作
- 52W位置必须前复权（tushare adj_factor）
- 先看扣非再看表报（归母净利可能被美化）
- 经营CF vs 净利背离是红旗
- **资金面信号≠基本面真相**（v2.3核心教训）
- **Forward PE必须计算**（v2.3新增）
- **毛利率趋势>绝对值**（v2.3新增）

## 诚实边界

- 四大师方法论为A股适配而非原创设计
- 四维评分回测胜率45%，仅辅助排序
- 三情景估值缺乏概率加权
- **非投资建议**，仅研究辅助工具

---

*Created with [女娲 · Skill造人术](https://github.com/alchaincyf/nuwa-skill)*
