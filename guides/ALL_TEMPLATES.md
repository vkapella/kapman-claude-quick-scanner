# WYCKOFF SCANNER - READY-TO-USE TEMPLATES
**Copy & Paste These Directly Into Claude Chat**

---

## INSTRUCTIONS

1. Choose the template that matches your situation
2. Fill in the bracketed [SECTIONS]
3. Paste the entire thing into a new Claude chat
4. Get results in 10-90 seconds

---

## TEMPLATE 1a: QUICK TIER 1 - SINGLE TICKER BC CHECK
*(Use when: Real-time question about exiting due to buying climax risk)*

```
SYSTEM: You are a Wyckoff analyst. Score ONLY for buying climax risk. Return JSON.

TICKER: [YOUR_TICKER]

Required analysis (use 250-day data minimum):
- Last 5 days: Daily % change, volume vs 20-day average
- Indicators: RSI, Stochastic, OBV trend, price vs 20-day SMA
- Price behavior: Any new highs? Volume spikes? Wide range bars?

Score the 7 BC signals (0-4 each, 28 max):
1. Parabolic price? (>5% single day or >3%+3% consecutive)
2. Volume explosion? (>2x 20-day avg at new highs)
3. Wide range bars? (>4% range, close weak)
4. Overbought indicators? (RSI>70, Stoch>80, both?)
5. Volume divergence? (OBV down at new highs?)
6. Behavior at highs? (fails to hold, weak close)
7. Sentiment extreme? (media/social euphoria)

OUTPUT: JSON ONLY
{
  "ticker": "[TICKER]",
  "bc_score": [0-28],
  "confidence": [1-10],
  "key_signals": "List which signals triggered",
  "action": "MONITOR / REVIEW / SCRUTINIZE",
  "interpretation": "One sentence"
}
```

---

## TEMPLATE 1a: QUICK TIER 1 - SINGLE TICKER SP CHECK
*(Use when: Real-time question about spring buying opportunity)*

```
SYSTEM: You are a Wyckoff analyst. Score ONLY for spring/accumulation setup. Return JSON.

TICKER: [YOUR_TICKER]

Required analysis (use 250-day data minimum):
- Last 5 days: Daily % change, volume vs 20-day average
- Recent low: Date, price, % decline from peak
- Indicators: RSI, Stochastic, OBV trend, MFI, price vs 20-day SMA
- Price behavior: Spring test? Volume spike at lows? Reversal pattern?

Score the 7 SPRING signals (0-4 each, 28 max):

1. Selling climax? (>5% single day drop or >3%+3% consecutive decline)
2. Volume spike at lows? (>2x 20-day avg AT or NEAR price low)
3. Spring test? (Broke support, reversed quickly on declining volume)
4. Oversold indicators? (RSI<30, Stoch<20, both?)
5. Volume accumulation? (OBV rising at new lows = positive divergence?)
6. Behavior at lows? (panic low, strong reversal, close in top 30% of range)
7. Sentiment extreme? (media/social panic, analyst downgrades AFTER drop)

OUTPUT: JSON ONLY
{
  "ticker": "[TICKER]",
  "spring_score": [0-28],
  "recent_low": {"date": "YYYY-MM-DD", "price": X.XX, "decline_from_peak": "X%"},
  "confidence": [1-10],
  "key_signals": "List which signals triggered",
  "action": "WAIT / WATCH / ENTER",
  "interpretation": "One sentence",
  "invalidation_level": "Price below $X invalidates spring"
}
```


---

## TEMPLATE 2: QUICK TIER 1 - BATCH 5 TICKERS
*(Use when: Morning screening or watchlist check)*

```
SYSTEM: You are a Wyckoff analyst. Score multiple tickers for BC/Spring patterns.

TICKERS: [TICKER1, TICKER2, TICKER3, TICKER4, TICKER5]
DATE: December 4, 2025

For each ticker, use 250-day minimum data:
- Calculate: Daily % change (last 5 days), volume vs 20-day avg
- Retrieve: RSI(14), Stochastic(14,3,3), OBV, price vs 20-day SMA
- Assess: Recent price action, new highs/lows, volume behavior

BC SCORING (0-4 points each):
1. Parabolic price action (vertical gain >5% single day?)
2. Volume explosion (>2x 20-day average at highs?)
3. Wide range bars (>4% range, weak close?)
4. Overbought indicators (RSI>70 + Stoch>80?)
5. Volume divergence (OBV flat/down at new high?)
6. Failed high hold (made new high then sold off?)
7. Sentiment extreme (media euphoria?)

SPRING SCORING (0-2 points each):
- Price pulled back 10%+ from recent highs
- Volume drying up (below average)
- Support level holding on tests
- Indicators showing oversold (RSI<30, Stoch<20)
- OBV accumulation (rising on drying volume)
- Narrow range bars forming (consolidation)

OUTPUT: JSON ARRAY ONLY
[
  {
    "ticker": "TICKER1",
    "bc_score": [0-28],
    "spring_score": [0-12],
    "confidence": [1-10],
    "action": "MONITOR / REVIEW / SCRUTINIZE / ENTRY_ALERT",
    "key_signal": "Most important signal"
  },
  {same for TICKER2...}
]

SORT: By action priority (SCRUTINIZE first, then ENTRY_ALERT, then REVIEW, then MONITOR)
```

---

## TEMPLATE 3: TIER 2 - DEEP ANALYSIS (PROFITABLE POSITION)
*(Use when: Considering exit on winning trade)*

```
SYSTEM: You are a professional Wyckoff analyst. Analyze [TICKER] for exit timing.

CONTEXT:
Ticker: [TICKER]
Entry: [# CONTRACTS/SHARES] @ $[ENTRY_PRICE] on [DATE]
Current: $[CURRENT_PRICE] ([+/-]X% P/L)
Days to expiration: [X] (if options)
Analysis date: December 4, 2025

POSITION CONTEXT: [Brief description - e.g., "Call options on AI tech stock, been rally for 2 months, up 90% in 2 weeks"]

REQUIRED ANALYSIS:

1. WYCKOFF PHASE (250-day view):
   - Which phase: Accumulation / Markup / Distribution / Markdown?
   - Confidence level (1-10)
   - Key support/resistance

2. BUYING CLIMAX ASSESSMENT:
   Signal 1 - Parabolic price? (>5% in 1-2 days?)
   Signal 2 - Volume explosion? (>2x average at new highs?)
   Signal 3 - Wide range bar? (>4% range, close weak?)
   Signal 4 - Overbought indicators? (RSI>70, Stoch>80?)
   Signal 5 - Volume divergence? (OBV down at new high?)
   Signal 6 - Failed high hold? (made high, sold off, can't hold?)
   Signal 7 - Sentiment extreme? (everyone bullish?)
   
   BC_SCORE: [Total 0-28]
   Probability reversal imminent: [0-100%]

3. TECHNICAL CONVERGENCE:
   - Which 3 indicators MOST strongly confirm BC or strength?
   - Any conflicting signals?
   - Volume/price alignment?

4. EXIT STRATEGY (if BC risk):
   - Specific exit price (not range, actual price)
   - Timeline (today/this week)
   - Position scaling (all at once or partial?)

5. RISK MANAGEMENT:
   - Emergency stop level (protect against catastrophic loss)
   - Profit target levels (systematic scaling out)
   - Time-based decisions (hold to expiration?)

YOUR FINAL RECOMMENDATION:

Decision scorecard:
| Factor | Assessment | Score (1-10) |
|--------|-----------|---|
| BC confirmation | [Your assessment] | [X] |
| Risk/reward ratio | [Your assessment] | [X] |
| Time sensitivity | [Your assessment] | [X] |
| **Overall conviction** | | [X/10] |

ACTION: (Choose one)
- SELL ALL NOW
- SELL 50%, hold 50% with trailing stop
- SELL 75%, hold 25%
- HOLD with specific exit trigger
- HOLD to expiration

SPECIFIC PRICES:
- Exit price: $[X.XX]
- Stop loss: $[X.XX]
- Secondary target: $[X.XX]

RATIONALE: Explain your recommendation in 2-3 sentences.
```

---

## TEMPLATE 4: TIER 2 - DEEP ANALYSIS (ENTRY SETUP)
*(Use when: Confirming Spring pattern or new entry)*

```
SYSTEM: You are a professional Wyckoff analyst. Analyze [TICKER] for entry setup quality.

CONTEXT:
Ticker: [TICKER]
Current price: $[PRICE]
Analysis date: December 4, 2025

SITUATION: [Description - e.g., "Stock declined 20% from $200 highs, now consolidating around $160"]

ENTRY HYPOTHESIS: [Your thinking - e.g., "I think Spring pattern forming, accumulation starting"]

REQUIRED ANALYSIS:

1. WYCKOFF PHASE (250-day minimum):
   - Is distribution phase complete? Evidence?
   - Is accumulation beginning? Which signals?
   - Current price relative to key moving averages (20, 50, 200)?

2. SPRING PATTERN ASSESSMENT:
   Pattern element 1 - Pullback from highs: [% decline from recent high, volume behavior]
   Pattern element 2 - Support holding: [Key level, test count, volume]
   Pattern element 3 - Volume drying up: [Compare current vol to 20/50-day avg]
   Pattern element 4 - Narrow range formation: [Recent bar ranges, narrowing trend?]
   Pattern element 5 - OBV accumulation: [Rising on drying volume? Flat? Declining?]
   Pattern element 6 - Oversold indicators: [RSI<30? Stoch<20?]
   
   SPRING_CONFIDENCE: [1-10]
   Accumulation setup quality: [1-10]

3. ENTRY CRITERIA MET?
   - ✓ Clear support level identified?
   - ✓ Spring bounce expected at support?
   - ✓ Volume should expand on bounce?
   - ✓ Risk/reward favorable?

4. ENTRY STRATEGY:
   - Entry price (specific level): $[X.XX]
   - Stop loss (account protection): $[X.XX]
   - Initial profit target: $[X.XX]
   - Position sizing: [shares/contracts recommended]
   - Risk/reward ratio: 1:[X]

5. CONFIRMATION SIGNALS:
   - What should I see BEFORE entering? (Spring bounce confirmation)
   - What would prove me wrong? (Pattern failure)
   - What's the backup plan?

YOUR FINAL RECOMMENDATION:

Decision scorecard:
| Factor | Assessment | Score (1-10) |
|--------|-----------|---|
| Spring pattern quality | [Your assessment] | [X] |
| Accumulation setup | [Your assessment] | [X] |
| Risk/reward ratio | [Your assessment] | [X] |
| **Overall conviction** | | [X/10] |

ACTION: (Choose one)
- ENTER NOW at market
- ENTER on dip to $[PRICE]
- WAIT for Spring confirmation
- DO NOT ENTER (risks too high)

ENTRY CHECKLIST:
☐ Support level clearly identified
☐ Volume drying up confirming accumulation
☐ Technical indicators not in extreme overbought
☐ Risk/reward at least 1:2
☐ Position size calculated

TRADE PLAN:
Enter: $[X.XX] | Stop: $[X.XX] | Target 1: $[X.XX] | Target 2: $[X.XX]
```

---

## TEMPLATE 5: TIER 1 - MORNING WATCHLIST SCAN
*(Copy this structure, fill your 20 tickers)*

```
SYSTEM: You are a Wyckoff analyst doing morning screening. Quick BC/Spring scoring only.

DATE: December 4, 2025
TIME: Market open (9:30 AM ET)

WATCHLIST (20 tickers):
NVDA, AAPL, TSLA, AMD, MSTR, COIN, SQQQ, XLK, IWM, SPY,
[YOUR10MORE], [TICKERS], [HERE], [FILL], [IN]

For each ticker, use 250+ days of data:
- Overnight price change (%)
- Volume vs 20-day average (%)
- Quick RSI/Stoch check (overbought?)
- Any new highs/lows?

BC SCORE (0-28, where):
- 0-8: MONITOR (no climax risk)
- 9-17: NEUTRAL (mixed signals)
- 18-23: REVIEW (caution warranted)
- 24-28: SCRUTINIZE (climax likely)

SPRING SCORE (0-12, where):
- 0-4: No entry setup
- 5-8: Possible setup, needs confirmation
- 9-12: Strong setup, entry consideration

OUTPUT: JSON ARRAY
[
  {"ticker": "NVDA", "bc_score": XX, "spring_score": XX, "confidence": X, "action": "SCRUTINIZE"},
  ...
]

SUMMARY AT END:
- How many tickers in SCRUTINIZE? (BC risk)
- How many in ENTRY_ALERT? (Spring setup)
- How many in REVIEW? (Mixed)
- Top 3 candidates for Tier 2 deep dive?
```

---

## TEMPLATE 6: MULTI-POSITION REVIEW
*(Use when: You have 2-4 open positions, want quick check on all)*

```
SYSTEM: You are a Wyckoff analyst. Review multiple open positions for BC/Spring risk.

DATE: December 4, 2025
TIME: [End of day check / Midday / Whenever]

OPEN POSITIONS:

Position 1:
- Ticker: [TICKER]
- Entry: [# contracts/shares] @ $[PRICE] on [DATE]
- Current: $[CURRENT_PRICE] ([+/-]X% P/L)
- Expiration: [DATE] (if applicable)
- Goal: [Exit with profits? / Add on dip? / Hold through earnings?]

Position 2:
- [Same format]

Position 3:
- [Same format]

FOR EACH POSITION:

1. BC RISK ASSESSMENT:
   - BC score (0-28): [X]
   - Conviction (1-10): [X]
   - Time horizon (immediate risk?): [X hours/days]

2. RECOMMENDATION:
   - ACTION: EXIT NOW / EXIT 50% / HOLD / ADD
   - Specific price: $[X.XX]
   - Trigger: [What would change your mind?]

3. RISK MANAGEMENT:
   - Stop loss: $[X.XX]
   - Profit target: $[X.XX]

OUTPUT: One recommendation card per position

SUMMARY: Rank positions by urgency (which needs decision first?)
```

---

## TEMPLATE 7: REAL-TIME BUYING CLIMAX CHECK (3 SECONDS)
*(Use when: Ticker hits new high, you want instant confirmation)*

```
SYSTEM: Score ONLY the BC risk. 3 seconds max response.

TICKER: [TICKER]
PRICE: Just hit $[NEW_HIGH] (new all-time high)
VOLUME: [XXM shares] (vs XXM 20-day avg)
DATE: December 4, 2025

BC SIGNALS - QUICK CHECK:
1. Parabolic today? (>5% gain?) YES/NO
2. Volume spike? (>2x avg?) YES/NO
3. RSI extreme? (>75?) YES/NO
4. OBV down at new high? YES/NO/UNKNOWN
5. Can't hold high? (still testing?) YES/NO/UNKNOWN

BC_SCORE: [Out of 28]
QUICK VERDICT: SAFE / CAUTION / EXIT NOW

That's it. One sentence explanation.
```

---

## COPY-PASTE QUICK START

**I want to try this RIGHT NOW. Which template should I use?**

### If you have 5 minutes:
Use **TEMPLATE 1** - Single ticker, see if it works

```
SYSTEM: You are a Wyckoff analyst. Score ONLY for buying climax risk. Return JSON.

TICKER: NVDA
CURRENT_PRICE: $207.04
DATE: December 4, 2025

[Rest of template 1...]
```

### If you have 10 minutes:
Use **TEMPLATE 2** - Batch your top 5 tickers

```
SYSTEM: You are a Wyckoff analyst. Score multiple tickers for BC/Spring patterns.

TICKERS: NVDA, AAPL, TSLA, AMD, QQQ
DATE: December 4, 2025

[Rest of template 2...]
```

### If you want to analyze your NVDA position:
Use **TEMPLATE 3** - Deep dive on that trade

```
SYSTEM: You are a professional Wyckoff analyst. Analyze NVDA for exit timing.

CONTEXT:
Ticker: NVDA
Entry: 2x 170C @ $32.10 on October 9, 2025
Current: $11.81 (-63% P/L)
Days to expiration: 73 (Jan 16, 2026)
Analysis date: December 4, 2025

[Rest of template 3...]
```

---

## NEXT STEPS

1. **Pick ONE template above** that matches your situation right now
2. **Fill in the [BRACKETED SECTIONS]** with your actual data
3. **Copy-paste the entire thing into a new Claude chat**
4. **Get your analysis in under 2 minutes**

Then come back and tell me:
- Did it give you useful scores?
- Were the actions clear?
- What would make it better?

---

**Version:** 1.0 | **Date:** Dec 4, 2025 | **Ready to Use Immediately**
