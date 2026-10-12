# India-Stocks-331-360-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 331 to 360)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-331-360-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (331 to 360)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 331 | `FINCABLES` | Finolex Cables Ltd. | `FINCABLES.NS` |
| 332 | `FSL` | Firstsource Solutions Ltd. | `FSL.NS` |
| 333 | `FIVESTAR` | Five-Star Business Finance Ltd. | `FIVESTAR.NS` |
| 334 | `FORCEMOT` | Force Motors Ltd. | `FORCEMOT.NS` |
| 335 | `FRACTAL` | Fractal Analytics Ltd. | `FRACTAL.NS` |
| 336 | `GABRIEL` | Gabriel India Ltd. | `GABRIEL.NS` |
| 337 | `GALLANTT` | Gallantt Ispat Ltd. | `GALLANTT.NS` |
| 338 | `GRSE` | Garden Reach Shipbuilders & Engineers Ltd. | `GRSE.NS` |
| 339 | `GILLETTE` | Gillette India Ltd. | `GILLETTE.NS` |
| 340 | `GLAND` | Gland Pharma Ltd. | `GLAND.NS` |
| 341 | `GPIL` | Godawari Power & Ispat Ltd. | `GPIL.NS` |
| 342 | `GRANULES` | Granules India Ltd. | `GRANULES.NS` |
| 343 | `GRAPHITE` | Graphite India Ltd. | `GRAPHITE.NS` |
| 344 | `GRAVITA` | Gravita India Ltd. | `GRAVITA.NS` |
| 345 | `GESHIP` | Great Eastern Shipping Co. Ltd. | `GESHIP.NS` |
| 346 | `GMDCLTD` | Gujarat Mineral Development Corporation Ltd. | `GMDCLTD.NS` |
| 347 | `HBLENGINE` | HBL Engineering Ltd. | `HBLENGINE.NS` |
| 348 | `HEGAM` | HEG Advanced Materials Ltd. | `HEGAM.NS` |
| 349 | `HFCL` | HFCL Ltd. | `HFCL.NS` |
| 350 | `HSCL` | Himadri Speciality Chemical Ltd. | `HSCL.NS` |
| 351 | `HOMEFIRST` | Home First Finance Company India Ltd. | `HOMEFIRST.NS` |
| 352 | `HONASA` | Honasa Consumer Ltd. | `HONASA.NS` |
| 353 | `HONAUT` | Honeywell Automation India Ltd. | `HONAUT.NS` |
| 354 | `IDBI` | IDBI Bank Ltd. | `IDBI.NS` |
| 355 | `IFCI` | IFCI Ltd. | `IFCI.NS` |
| 356 | `IIFL` | IIFL Finance Ltd. | `IIFL.NS` |
| 357 | `INOXINDIA` | INOX India Ltd. | `INOXINDIA.NS` |
| 358 | `IRB` | IRB Infrastructure Developers Ltd. | `IRB.NS` |
| 359 | `IRCON` | IRCON International Ltd. | `IRCON.NS` |
| 360 | `ITI` | ITI Ltd. | `ITI.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream FINCABLES 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-331-360-Historical-Data/main/FINCABLES/1m/2026/10/FINCABLES_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
