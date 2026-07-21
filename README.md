# AI Berkshire: 价值投资深度研究系统

> Berkshire Hathaway-style investment research system for A-share stocks.

基于巴菲特、芒格、段永平、李录四位大师方法论的结构化投研工具集。

## v2.4 更新（2026-07-21）

### 新增：财务穿透标准流程（Phase 2.5）
- **4步验证链**：income → fina_indicator → forecast → report_rc
- **必须在资金面信号之前执行**——资金面≠基本面真相
- 判定矩阵：健康/待确认/恶化/价值陷阱四级

### 新增避坑规则
- report_rc时效陷阱（可能只返回2010-2018旧报告）
- 多源交叉验证协议（tushare+global-stock-data+CRW+wigolo）
- Tushare income字段稀疏陷阱（补查fina_indicator）
- 万讯帖数搜索（merged JSON历史推荐验证）

### 强化：段永平裁决（Phase 2 Step 8）
- 正式化为分析步骤（原v2.3附属section）
- 决策树：段永平≥7→检查巴菲特+李录→✅；段永平<7→❌价格不对不买

## 四大师框架

| 大师 | 维度 | 核心标准 | A股权重 |
|------|------|---------|:------:|
| 巴菲特 | 生意质地 | ROE>15%? CF>NI? | 中 |
| 芒格 | 护城河 | 技术壁垒? 定价权? | 中 |
| **段永平** | 价格/A股 | PEG<1? 52W<60%? 本分? | **最高** ⭐ |
| 李录 | 增长/长期 | CAGR? ROIC>WACC? | 第二 |

## 使用方法

```bash
git clone https://github.com/sermady/ai-berkshire.git ~/.claude/skills/ai-berkshire
```

## 数据源

- tushareMcp: 258个工具
- a-stock-data: 7层28端点
- global-stock-data: 美股港股
- 万讯智研知识星球: 7935帖+附件

## 诚实边界

- 四维评分回测胜率45%
- 非投资建议，仅研究辅助工具

---

*Created with [女娲 · Skill造人术](https://github.com/alchaincyf/nuwa-skill)*
