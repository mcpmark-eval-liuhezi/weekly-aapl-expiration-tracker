# Contributing to aapl-expiration-tracker

Thanks for your interest in contributing to this AAPL options expiration tracking repository! This guide covers how to submit changes for this weekly risk-desk tracker.

## How to Submit a Change

1. **Create a feature branch** off `main` (e.g., `add-<topic>`).
2. **Commit your changes** with a clear, descriptive commit message.
3. **Open a pull request** into `main`. Title it clearly (e.g., `Add <what> for expiry YYYY-MM-DD`).
4. **Reference linked issues** in the PR description where applicable (e.g., tracking issues #1, #2, #3).

## What WeTrack Here

- Weekly AAPL (Apple Inc.) options chain statistics pulled from live Yahoo Finance data.
- Per-expiration At-The-Money (ATM) strikes, highest-open-interest call strikes, and highest-open-interest put strikes.
- Company snapshot (headquarters, sector, industry, share price) and the full expiration map.

## Data Handling Rules

- **All market figures must come from live data.** Do not hard-code prices or stats from memory — pull fresh values from Yahoo Finance (or the appropriate source) and update the files accordingly.
- **Report exactly what the source returns.** If a number looks odd (e.g., a deep out-of-the-money strike showing the highest open interest), note it in the PR description and in the file comments rather than silently "correcting" it.
- Share price used for ATM determination should be stated explicitly in any stats you add.

## Pulll Request Checklist

- [ ] Changes are on a feature branch off `main`.
- [ ] PR description references the relevant tracking issue(s).
- [ ] Any odd-looking source values are flagged with a note.
- [ ] `expirations.md` (or equivalent) is updated if chain stats change.

## Workflow

A minimal manually-triggerable workflow (`.github/workflows/manual-ci.yml`) is included. It can be run via **Actions → workflow_dispatch**. Keep runs tidy by deleting run logs after use.

## Discussion

This repository currently has no discussion categories configured. If the team wants to use GitHub Discussions for Q&A, enabling them is a repo Settings change outside the scope of code contributions.

---

*Repository: mcpmark-eval-liuhezi/weekly-aapl-expiration-tracker · Data source: Yahoo Finance (AAPL).*
