# AAPL Options Expiration Tracker

> Weekly tracking repository for Apple (AAPL) options chain statistics, maintained for the risk desk. All market figures below are pulled from live Yahoo Finance data at the time of this weekly review.

## 1. Company Snapshot (Apple Inc. — AAPL)

| Field | Value |
| --- | --- |
| **Headquarters street address** | One Apple Park Way, MS 927-4GC |
| **City** | Cupertino, CA 95014, United States |
| **Sector** | Technology |
| **Industry** | Consumer Electronics |
| **Current share price** | $355.63 (Yahoo Finance,Regular Market Price; market state POSTPOST) |
| **Previous close** | $348.51 |
| **Day range** | $349.325 – $355.90 |
| **52-week range** | $243.42 – $355.90 |
| **Market cap** | ~$5.17T |
| **Exchange** | NasdaqGS (NMS) |
| **trailing PE / forward PE** | 39.60 / 33.72 |
| **Analyst recommendation** | Buy (mean 2.22, 40 analysts) |
| **CEO** | John Ternus |
| **Website** | https://www.apple.com |

**Source:** Yahoo Finance company profile (get_stock_info) for ticker AAPL.

## 2. Expiration Map (AAPL Option Expiration Dates)

The option expiration dates currently available for AAPL (in date order):

| # | Expiration Date |
| --- | --- |
| 1 | 2026-11-13 |
| 2 | 2026-11-16 |
| 3 | 2026-11-18 |
| 4 | 2026-11-20 |
| 5 | 2026-11-27 |
| 6 | 2026-12-04 |
| 7 | 2026-12-11 |
| 8 | 2026-12-18 |
| 9 | 2026-12-24 |
| 10 | 2027-01-15 |
| 11 | 2027-02-19 |
| 12 | 2027-03-19 |
| 13 | 2027-04-16 |
| 14 | 2027-06-17 |
| 15 | 2027-09-17 |
| 16 | 2027-12-17 |
| 17 | 2028-01-21 |
| 18 | 2028-03-17 |
| 19 | 2028-06-16 |
| 20 | 2028-12-15 |
| 21 | 2029-01-19 |

**Source:** Yahoo Finance option expiration dates for ticker AAPL (`get_option_expiration_dates`).

## 3. Per-Expiration Chain Stats

**Share price used for ATM determination across all expirations:** **$355.63** (Yahoo Finance regular market price at time of pull).

ATM rule applied: the strike closest to the current share price ($ |strike − 355.63| minimized). For all three expirations reviewed, strike **355** was the closest listed strike (distance 0.63), versus 357.5 (distance 1.87).

### Expiration 2026-11-13

| Metric | Value |
| --- | --- |
| **At-the-money strike (call & put)** | **355** |
| **Highest open-interest call strike** | **360** (OI 16,819; last $0.89; volume 22,553) |
| **Highest open-interest put strike** | **265** (OI 10,654; last $0.01; volume 3) |
| Share price used | $355.63 |

### Expiration 2026-11-16

| Metric | Value |
| --- | --- |
| **At-the-money strike (call & put)** | **355** |
| **Highest open-interest call strike** | **355** (OI 5,737; last $3.60; volume 2,545) |
| **Highest open-interest put strike** | **330** (OI 1,537; last $0.10; volume 490) |
| Share price used | $355.63 |

### Expiration 2026-11-18

| Metric | Value |
| --- | --- |
| **At-the-money strike (call & put)** | **355** |
| **Highest open-interest call strike** | **362.5** (OI 7,037; last $1.53; volume 438) |
| **Highest open-interest put strike** | **340** (OI 439; last $0.62; volume 576) |
| Share price used | $355.63 |

### Notes on Data Quality (report exactly what the source returned)

- **2026-11-13 put OI at strike 265 (10,654)** is deep out-of-the-money (stock at $355.63) and is the largest put OI in the chain as returned by Yahoo Finance. Reported exactly as returned.
- **2026-11-13 call OI at strike 360 (16,819)** is also out-of-the-money; reported exactly as returned.
- **2026-11-16 call at 355 (OI 5,737)** is at-the-money and is itself the highest-OI call, which is typical ahead of expiry.
- **2026-11-18 call at 362.5 (OI 7,037)** is slightly OTM; reported exactly as returned.
- Open interest values are as reported by the Yahoo Finance option chain endpoint at pull time and may shift minute to minute.

## 4. Tracking Issues in This Repository

| Issue | Title | Expiration | Key Stats |
| --- | --- | --- | --- |
| #1 | Expiry 2026-11-13 | 2026-11-13 | ATM 355; top call OI 360 (16,819); top put OI 265 (10,654) |
| #2 | Expiry 2026-11-16 | 2026-11-16 | ATM 355; top call OI 355 (5,737); top put OI 330 (1,537) |
| #3 | Expiry 2026-11-18 | 2026-11-18 | ATM 355; top call OI 362.5 (7,037); top put OI 340 (439) |

## 5. Repository Contents

- `expirations.md` — this file (added via PR from `add-expirations-matrix` branch)
- `CONTRIBUTING.md` — contribution guidelines (added to `main` after PR opened)
- `.github/workflows/manual-ci.yml` — minimal manually-triggerable workflow (echo job)

## 6. Weekly Process

1. Pull live AAPL company snapshot and option chain data from Yahoo Finance.
2. Create one tracking issue per upcoming expiration (titled `Expiry YYYY-MM-DD`).
3. Add `expirations.md` on a feature branch and open a pull request into `main`.
4. Add `CONTRIBUTING.md` to `main`, then update the PR branch to keep it in sync.
5. Add a minimal `workflow_dispatch`-triggered workflow, run it once, note duration, and delete the run's logs to keep the repo tidy.
6. Check repository discussion categories (none configured at time of writing — report as-is).

---

*Data source: Yahoo Finance (AAPL). Pulled live for this weekly risk-meeting review. Repository: mcpmark-eval-liuhezi/weekly-aapl-expiration-tracker.*
