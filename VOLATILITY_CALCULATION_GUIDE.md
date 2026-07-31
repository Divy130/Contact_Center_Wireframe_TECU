# 📊 Volatility Calculation Guide

## What is Volatility?

**Volatility** = A measure of how much a metric **varies or fluctuates** over time.

It answers the question: **"How stable/consistent is this metric?"**

---

## 🧮 The Math Behind Volatility

### **Method 1: Standard Deviation (Most Common)**

**Standard Deviation** measures how spread out data points are from the average.

```
Formula:
σ (sigma) = √[ Σ(x - μ)² / N ]

Where:
σ = Standard Deviation (volatility measure)
x = Each data point
μ (mu) = Average/Mean of all data points
N = Number of data points
Σ = Sum of all values
```

---

## 📈 Worked Example: Sentiment Volatility

### **Scenario: 6 Weeks of Sentiment Data**

```
Week 1: 72% positive
Week 2: 74% positive
Week 3: 75% positive
Week 4: 76% positive
Week 5: 77% positive
Week 6: 78% positive
```

### **Step 1: Calculate the Average (Mean)**

```
Average = (72 + 74 + 75 + 76 + 77 + 78) ÷ 6
Average = 452 ÷ 6
Average = 75.33%
```

### **Step 2: Find Difference from Average for Each Week**

```
Week 1: 72 - 75.33 = -3.33
Week 2: 74 - 75.33 = -1.33
Week 3: 75 - 75.33 = -0.33
Week 4: 76 - 75.33 = +0.67
Week 5: 77 - 75.33 = +1.67
Week 6: 78 - 75.33 = +2.67
```

### **Step 3: Square Each Difference**

```
Week 1: (-3.33)² = 11.09
Week 2: (-1.33)² = 1.77
Week 3: (-0.33)² = 0.11
Week 4: (+0.67)² = 0.45
Week 5: (+1.67)² = 2.79
Week 6: (+2.67)² = 7.13

Sum of squared differences = 11.09 + 1.77 + 0.11 + 0.45 + 2.79 + 7.13 = 23.34
```

### **Step 4: Calculate Standard Deviation**

```
Standard Deviation = √(23.34 ÷ 6)
Standard Deviation = √3.89
Standard Deviation = 1.97%
```

### **Result: Volatility = 1.97%**

**Interpretation:**
- 1.97% is **VERY LOW**
- Data points vary by only ~2% from average
- Sentiment is **STABLE** ✓
- **Volatility Level: LOW**

---

## 🔄 Volatility Scale (How to Interpret)

```
Standard Deviation    Volatility Level    What It Means
─────────────────────────────────────────────────────────
0% - 2%              🟢 VERY LOW          Extremely stable
2% - 5%              🟢 LOW               Stable, consistent
5% - 10%             🟡 MEDIUM            Some variation
10% - 15%            🟡 HIGH              Significant swings
15%+                 🔴 VERY HIGH         Highly unpredictable
```

---

## 📊 Example 2: High Volatility (Problem Case)

### **Scenario: Same Data but Inconsistent**

```
Week 1: 95% positive
Week 2: 52% positive
Week 3: 88% positive
Week 4: 63% positive
Week 5: 91% positive
Week 6: 58% positive
```

### **Step 1: Calculate Average**

```
Average = (95 + 52 + 88 + 63 + 91 + 58) ÷ 6
Average = 447 ÷ 6
Average = 74.5%
```

### **Step 2: Differences from Average**

```
Week 1: 95 - 74.5 = +20.5
Week 2: 52 - 74.5 = -22.5
Week 3: 88 - 74.5 = +13.5
Week 4: 63 - 74.5 = -11.5
Week 5: 91 - 74.5 = +16.5
Week 6: 58 - 74.5 = -16.5
```

### **Step 3: Square the Differences**

```
Week 1: (+20.5)² = 420.25
Week 2: (-22.5)² = 506.25
Week 3: (+13.5)² = 182.25
Week 4: (-11.5)² = 132.25
Week 5: (+16.5)² = 272.25
Week 6: (-16.5)² = 272.25

Sum = 1785.5
```

### **Step 4: Calculate Standard Deviation**

```
Standard Deviation = √(1785.5 ÷ 6)
Standard Deviation = √297.58
Standard Deviation = 17.25%
```

### **Result: Volatility = 17.25%**

**Interpretation:**
- 17.25% is **VERY HIGH**
- Data points vary by ~17% from average
- Sentiment is **UNPREDICTABLE** ⚠️
- **Volatility Level: VERY HIGH** 🔴

---

## 🎯 Comparing the Two Examples

```
Stable Sentiment:
Average: 75.33%
Volatility: 1.97%
Pattern: 72% → 74% → 75% → 76% → 77% → 78% (smooth upward)
Status: ✓ STABLE - Easy to manage

Unstable Sentiment:
Average: 74.5%
Volatility: 17.25%
Pattern: 95% → 52% → 88% → 63% → 91% → 58% (zigzag)
Status: ✗ UNPREDICTABLE - Needs investigation
```

---

## 📱 Alternative Method: Coefficient of Variation (CV)

Sometimes volatility is shown as a **percentage relative to the average**:

```
Formula:
CV = (Standard Deviation ÷ Mean) × 100

Example 1 (Stable):
CV = (1.97 ÷ 75.33) × 100 = 2.62%

Example 2 (Unstable):
CV = (17.25 ÷ 74.5) × 100 = 23.16%
```

**Interpretation:**
- 2.62% = Low volatility (consistent)
- 23.16% = High volatility (inconsistent)

---

## 🧪 Real-World Contact Center Example

### **Daily Sentiment Over 2 Weeks**

```
Day 1:  78% positive
Day 2:  79% positive
Day 3:  77% positive
Day 4:  78% positive
Day 5:  80% positive
Day 6:  77% positive
Day 7:  79% positive
Day 8:  76% positive
Day 9:  78% positive
Day 10: 81% positive
Day 11: 77% positive
Day 12: 79% positive
Day 13: 78% positive
Day 14: 80% positive
```

### **Quick Analysis**

```
Average: 78.5%
Range: 76% to 81% (only 5 point spread)
Standard Deviation: ~1.2%

Result: ✓ LOW VOLATILITY
Interpretation: Sentiment is stable around 78-79%
Status: No action needed
```

---

## 📊 Volatility in Your Dashboard

### **Current Status**
```
Member Sentiment Tab
├── Positive Sentiment: 78% ↑
├── Volatility: Low
└── Status: Steady
```

### **What This Means**

| Component | Calculation | Result |
|-----------|-----------|--------|
| **Positive %** | (Positive interactions ÷ Total) × 100 | 78% |
| **Volatility** | Standard Deviation of sentiment over 6 weeks | 1-2% (LOW) |
| **Status** | Comparing to previous period | Steady (±2%) |

---

## 🔍 How to Calculate for Your Data

### **Using Excel/Google Sheets**

```
Step 1: Enter daily/weekly sentiment %:
A1: 72
A2: 74
A3: 75
A4: 76
A5: 77
A6: 78

Step 2: Calculate Standard Deviation:
=STDEV(A1:A6)

Result: 1.97%

Step 3: Interpret:
1.97% = LOW volatility ✓
```

### **Using Python**

```python
import statistics

sentiment_data = [72, 74, 75, 76, 77, 78]

# Calculate standard deviation
volatility = statistics.stdev(sentiment_data)
print(f"Volatility: {volatility:.2f}%")

# Result: Volatility: 1.97%

# Interpret
if volatility < 5:
    print("Status: LOW VOLATILITY ✓")
elif volatility < 10:
    print("Status: MEDIUM VOLATILITY")
else:
    print("Status: HIGH VOLATILITY ⚠️")
```

### **Using Power BI**

```dax
-- Create a measure for volatility
Volatility = 
CALCULATE(
    STDEV.S(Sentiment[PercentPositive]),
    DATESBETWEEN(Sentiment[Date], TODAY()-42, TODAY())
)

-- Create a measure for volatility level
VolatilityLevel = 
IF([Volatility] < 5, "Low", 
IF([Volatility] < 10, "Medium", "High"))
```

---

## 📈 Visual Understanding

### **Low Volatility (Stable)**
```
Sentiment %
     |      ━━━━━━━━━━━
  80 |    ╱╱
  75 |  ╱╱          ← Smooth, predictable line
  70 |╱╱
     |________________ Days
     Standard Dev: 1-2%
```

### **High Volatility (Unstable)**
```
Sentiment %
     |    ╱╲    ╱╲  ╱╲
  80 |   ╱  ╲  ╱  ╲╱  ╲  ← Jagged, unpredictable
  70 |  ╱    ╲╱
  60 |╱
     |________________ Days
     Standard Dev: 15%+
```

---

## 🎯 Key Takeaways

### **Volatility Calculation Summary**

| Step | What to Do | Example |
|------|-----------|---------|
| 1 | Collect data points | Sentiment: 72%, 74%, 75%, 76%, 77%, 78% |
| 2 | Calculate average | (72+74+75+76+77+78)÷6 = 75.33% |
| 3 | Find deviation from average | 72-75.33 = -3.33, 74-75.33 = -1.33, etc. |
| 4 | Square each deviation | (-3.33)²=11.09, (-1.33)²=1.77, etc. |
| 5 | Find average of squared deviations | Sum ÷ count = 23.34 ÷ 6 = 3.89 |
| 6 | Take square root | √3.89 = 1.97% |
| 7 | Interpret | 1.97% = LOW ✓ |

---

## 💡 Why This Matters for Contact Centers

### **Low Volatility Benefits**
- ✅ Predictable performance
- ✅ Easier to plan staffing
- ✅ Stable customer expectations
- ✅ Easier to measure improvement

### **High Volatility Red Flags**
- ❌ Something is inconsistent
- ❌ Quality varies widely
- ❌ Hard to predict outcomes
- ❌ Investigation needed

### **Common Causes of High Volatility**

| Cause | How to Fix |
|-------|-----------|
| Inconsistent agent quality | Training & coaching |
| Different issue types day-to-day | Better routing/triage |
| Staffing changes | Stable schedule |
| System performance varies | Infrastructure improvements |
| Seasonal/external factors | Plan for known patterns |

---

## 🔗 Related Metrics

| Metric | Measures | Example |
|--------|----------|---------|
| **Volatility** | How much variation? | 1.97% = Low |
| **Trend** | Direction up or down? | 72% → 78% = Upward |
| **Consistency** | Same as volatility | Low volatility = consistent |
| **Predictability** | Can we forecast it? | Low volatility = predictable |

---

## 📋 Dashboard Implementation

### **In Your Contact Center Dashboard**

The dashboard shows:
```
Sentiment Tab
├── Positive Sentiment: 78% ↑ 4% (Trend)
├── Neutral Sentiment: 15% → Stable
├── Negative Sentiment: 7% ↓ 2% (Trend)
├── Overall Score: 4.1/5
├── Volatility: Low ← Calculated using Standard Deviation
└── Status: Steady
```

### **How It's Calculated in Dashboard**

```javascript
// Pseudocode showing how volatility is calculated
const sentimentData = [72, 74, 75, 76, 77, 78]; // 6 weeks

function calculateVolatility(data) {
    const mean = data.reduce((a,b) => a+b) / data.length;
    const variance = data.reduce((a,b) => a + (b-mean)²) / data.length;
    const stdev = Math.sqrt(variance);
    
    return stdev < 5 ? "Low" : stdev < 10 ? "Medium" : "High";
}

const volatilityLevel = calculateVolatility(sentimentData);
// Result: "Low"
```

---

## ✅ Quick Reference

**To calculate volatility:**

1. **Get your data** (sentiment %, volume, AHT, whatever metric)
2. **Calculate the average**
3. **Find how far each point is from average**
4. **Square those differences**
5. **Average the squared differences**
6. **Take the square root** (this is your standard deviation/volatility)
7. **Interpret:**
   - 0-5% = Low ✓
   - 5-10% = Medium
   - 10%+ = High ⚠️

---

## 📞 Questions?

**Q: Can I use different formulas?**
A: Yes! STDEV.S (sample), STDEV.P (population), or Coefficient of Variation all work

**Q: How often should I calculate?**
A: Weekly for operations, Daily for real-time monitoring

**Q: What if volatility is high?**
A: Investigate the cause and fix the inconsistency

**Q: Can I have low volatility but still improve?**
A: Yes! Low volatility + Upward trend = Consistent improvement

---

**Updated:** July 31, 2024 | **Method:** Standard Deviation (Most Common)
