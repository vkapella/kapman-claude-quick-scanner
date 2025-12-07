# WYCKOFF ENHANCED ANALYSIS - QUICK REFERENCE CARD

---

## 📞 API CALLS (7 Total)

```python
# Base (4 calls - existing)
price_data = get_stock_aggregates(ticker, timespan='day', limit=250)
indicators = get_all_ta_indicators(ticker, days=250)
market_status = get_market_status()
news = get_stock_news(ticker, limit=5)

# Institutional (3 calls - NEW)
dealer = get_dealer_metrics(ticker)
volatility = get_volatility_metrics(ticker)
price = get_price_metrics(ticker, period=20)
```

**Cost:** $1.55 → $1.70 (+$0.15 per analysis)

---

## 🌱 SPRING SCORING (0-25)

### Base Wyckoff (0-12)
- Volume pattern: 0-3
- Price structure: 0-3
- Technical indicators: 0-3
- Phase context: 0-3

### Enhancement 1: Dealer Support (0-6)
- At put wall + short gamma: +3
- DGPI < -30: +2
- Below gamma flip: +1

### Enhancement 2: Vol Compression (0-4)
- RVOL <0.8 + VSI <0: +3
- IV skew >2.0: +2
- HV-IV diff >10: +1

### Enhancement 3: Accumulation (0-3)
- Short gamma + DGPI <-30: +3
- P/C >1.2 + VSI <0: +2
- IV skew >2.0: +2

### Thresholds
- **0-8:** Skip
- **9-15:** Monitor
- **16-20:** Consider (50-75% position)
- **21-25:** High conviction (full position) ✅

---

## 🔴 BC SCORING (0-41)

### Base 7 Signals (0-28)
1. Parabolic price (>5% day): 0-4
2. Volume explosion (>200% avg): 0-4
3. Wide range bars (>4%): 0-4
4. Overbought (RSI>70, etc): 0-4
5. Volume divergence (OBV declining): 0-4
6. Behavior at highs (failed hold): 0-4
7. Sentiment extremes (euphoria): 0-4

### Enhancement 1: Dealer Resistance (0-7)
- At call wall + long gamma: +4
- DGPI >30: +3
- Negative GEX + above flip: +2

### Enhancement 2: Vol Expansion (0-4)
- RVOL >1.5 + VSI >2.0: +4
- HV >30%: +3
- IV skew <-1.0: +2

### Enhancement 3: Distribution (0-2)
- Long gamma + DGPI >30: +4
- P/C <0.7 + RVOL >1.5: +3
- IV skew <-1.0: +2
- OI ratio >8.0: +2

### Thresholds
- **0-12:** Hold
- **13-24:** Watch
- **25-32:** Caution (prepare exits)
- **33-37:** Exit 75% ⚠️
- **38-41:** Exit 100% 🚨

---

## 📊 KEY METRICS CHEAT SHEET

| Metric | Spring Target | BC Target | Source |
|--------|--------------|-----------|--------|
| RVOL | <0.8 (quiet) | >1.5 (surge) | price_metrics |
| VSI | <0 (below avg) | >2.0 (2σ surge) | price_metrics |
| DGPI | <-30 (support) | >30 (resistance) | dealer_metrics |
| Position | short_gamma | long_gamma | dealer_metrics |
| IV Skew | >2.0 (fear) | <-1.0 (greed) | volatility_metrics |
| P/C Ratio | >1.2 (fear) | <0.7 (euphoria) | volatility_metrics |
| HV-IV Diff | >10 (calm) | <-50 (stressed) | price_metrics |

---

## 🎯 DECISION MATRIX

### Spring Entry
```
Score 21-25 → Enter full position
Score 16-20 → Enter 50-75%, tight stop
Score 9-15 → Wait for confirmation
Score 0-8 → Skip entirely
```

### BC Exit
```
Score 38-41 → Market order EXIT 100% within 1 hour
Score 33-37 → Limit order EXIT 75% immediately
Score 25-32 → Contingent stop orders, prepare to exit
Score 0-24 → Monitor, hold with stops
```

---

## ⚡ CRITICAL REMINDERS

1. **Verify dates FIRST** - show verification block before analysis
2. **250-day minimum** - shorter windows miss context
3. **Find BC peak in history** - don't analyze current price
4. **All 7 endpoints required** - don't skip institutional data
5. **Mechanical thresholds** - no discretion, follow rules
6. **Data quality check:**
   ```python
   assert dealer['metadata']['contracts_analyzed'] > 50
   assert dealer['confidence'] in ['high', 'medium']
   ```

---

## 🔍 NVDA CASE STUDY (Oct 29, 2025)

**What Actually Happened:**
- Base BC: 25/28 (all 7 signals)
- Held through distribution
- Loss: **-$3,019 per contract**

**What Enhanced Analysis Shows:**
- Base: 25/28
- Dealer: +7 (call walls, DGPI +85)
- Vol: +4 (RVOL 2.1x, VSI 3.2σ)
- Divergence: +2 (P/C 0.65)
- **Total: 38/41 → "EXIT 100%"**
- **Would have saved $3,019 per contract**

---

## 📁 COMPLETE DOCUMENT SET

1. **COMPLETE_LLM_PROMPT_TEMPLATE.md** ← Start here for LLM implementation
2. **EXECUTIVE_SUMMARY.md** ← High-level overview
3. **polygon_mcp_integration_analysis.md** ← Full technical details
4. **production_implementation_guide.md** ← Code examples
5. **THIS CARD** ← Quick reference during analysis

---

## 💰 ROI SUMMARY

- **Monthly cost increase:** $7.50 (50 analyses)
- **Value:** Avoiding one $500 mistake = **67x ROI**
- **Your NVDA lesson:** $3,019 cost vs $0.15 per analysis
- **Break-even:** First prevented false signal

---

**Version:** 2.0 Enhanced | **Date:** Dec 7, 2025 | **Status:** Production Ready ✅
