# WYCKOFF BATCH SCANNER - INTERACTIVE MENU

## HOW TO USE

Simply paste these commands into Claude chat:

### Morning Screening (30 seconds)
```
SCAN 1 NVDA, AAPL, TSLA, AMD, QQQ
```

### Single Ticker BC Check
```
SCAN 1 [TICKER]
```

### Batch 5 Tickers
```
SCAN 1 TICKER1, TICKER2, TICKER3, TICKER4, TICKER5
```

### Exit Decision (Profitable Trade)
```
SCAN 2 [TICKER] | position: [# contracts @ price] | current: $[price] | context: is this buying climax?
```

### Entry Confirmation (Spring Pattern)
```
SCAN 2 [TICKER] | context: price declined, volume drying, looking for entry
```

### Multi-Position Review
```
SCAN 2
NVDA | 2x 170C @ $32.10 | current $11.81
AAPL | 2x 270C @ $18.00 | current $60.50
SLV | 100 shares @ $28 | current $29.50
```

### Real-Time BC Check (3 seconds)
```
SCAN 1 [TICKER] | bc-only
```

---

**Daily Time Commitment:** 2-5 minutes
**Daily Cost:** $0.03-0.06
