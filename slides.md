# Quarterly Earnings Brief
23f3000048@ds.study.iitm.ac.in

- Technical consultant update
- Modern, interactive presentation
- Published on GitHub Pages

Notes:
Open with the macro context and remind stakeholders of strategic KPIs.

---

## Highlights (Q/Q)
- Revenue growth: <span class="fragment">Diversified products</span>
- Cost discipline: <span class="fragment">Supplier renegotiations</span>
- Risk: <span class="fragment">Credit provisioning stabilizing</span>

Notes:
Advance one fragment at a time; pause after each headline.

---

## KPI Snapshot
- Net interest margin: <span class="fragment">Improved</span>
- Fee income: <span class="fragment">Cross-sell uplift</span>
- Opex: <span class="fragment">Automation tailwinds</span>

Notes:
If asked about seasonality, highlight last quarter’s baseline.

---

## Financial Formulae (Math)
We model loan amortization and risk-adjusted return using:

- Interest accrual (discrete):
  \[
  A = P \left(1 + \frac{r}{m}\right)^{mt}
  \]

- Risk-adjusted return on capital (RAROC):
  \[
  \mathrm{RAROC} = \frac{\text{Expected\ Profit}}{\text{Economic\ Capital}}
  \]

- Present value of cash flows:
  \[
  PV = \sum_{t=1}^{T} \frac{CF_t}{(1+r)^t}
  \]

Notes:
Explain assumptions: r as effective rate, m compounding periods, EC from internal model.

---

## Code Samples

### Python: amortization schedule

```python
def amortization_schedule(principal, annual_rate, periods):
    r = annual_rate / 12
    pmt = principal * (r * (1 + r)**periods) / ((1 + r)**periods - 1)
    balance = principal
    rows = []
    for n in range(1, periods + 1):
        interest = balance * r
        principal_paid = pmt - interest
        balance -= principal_paid
        rows.append((n, round(pmt, 2), round(interest, 2), round(principal_paid, 2), round(balance, 2)))
    return rows
```    
