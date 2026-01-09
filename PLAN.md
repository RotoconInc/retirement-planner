# PLAN.md - Feature Roadmap

## Planned Features

### 1. 2025 Tax Year Update
Update all tax constants to 2025 IRS values:
- Federal tax brackets (MFJ and Single)
- Standard deductions ($30,000 MFJ / $15,000 Single)
- Capital gains brackets
- **File:** `src/utils/constants.ts`

### 2. Contribution Limit Tracking
Add 2025 retirement account contribution limits:
- 401k: $23,500 (catch-up: $7,500 for 50+, $11,250 for 60-63)
- IRA: $7,000 (catch-up: $1,000 for 50+)
- HSA: $4,300 single / $8,550 family
- Could validate user inputs against these limits
- Could auto-apply catch-up contributions based on age

### 3. Roth Conversion Modeling
Allow users to simulate strategic Roth conversions:
- Model conversions during accumulation phase
- Model conversions in early retirement (before RMDs at 73)
- Show tax impact of conversion amounts
- Optimize to fill lower tax brackets
- Compare scenarios with/without conversions

### 4. Social Security Optimization
Model different claiming strategies:
- Compare claiming at 62, 67 (FRA), and 70
- Show breakeven ages
- Factor in spousal benefits
- Visualize cumulative lifetime benefits
- Consider impact on portfolio longevity

### 5. Inflation-Adjusted Spending View
Add "real dollars" visualization option:
- Toggle between nominal and inflation-adjusted values
- Show purchasing power over time
- Display real vs nominal withdrawal amounts
- Help users understand true spending capacity

### 6. Scenario Comparison
Save and compare multiple retirement scenarios:
- Name and save different configurations
- Side-by-side comparison view
- Compare metrics: portfolio longevity, total taxes, legacy amount
- Example scenarios: retire at 60 vs 65, aggressive vs conservative returns

### 7. Monte Carlo Simulation
Add probability-based projections:
- Replace fixed return rates with distribution of outcomes
- Show success probability (e.g., "85% chance of not running out")
- Display confidence bands on charts (10th, 50th, 90th percentile)
- Sequence of returns risk modeling
- Configurable number of simulations

### 8. IRMAA Thresholds
Model Medicare premium surcharges:
- Track Modified Adjusted Gross Income (MAGI)
- Show when income triggers IRMAA brackets
- Calculate additional Medicare Part B/D premiums
- Factor into total retirement costs
- 2025 IRMAA thresholds and premium amounts

---

## Implementation Priority

| Priority | Feature | Complexity | Impact |
|----------|---------|------------|--------|
| 1 | 2025 Tax Year Update | Low | High |
| 2 | Contribution Limit Tracking | Low | Medium |
| 3 | Inflation-Adjusted View | Medium | Medium |
| 4 | Social Security Optimization | Medium | High |
| 5 | Roth Conversion Modeling | High | High |
| 6 | IRMAA Thresholds | Medium | Medium |
| 7 | Scenario Comparison | High | High |
| 8 | Monte Carlo Simulation | High | High |

---

## Additional Core Features (Ranked by User Value)

### 9. Pension Income Modeling
Support defined benefit pensions:
- Monthly pension amount with start age
- COLA adjustments (fixed % or CPI-linked)
- Survivor benefit options (50%, 75%, 100%)
- Lump sum vs annuity comparison
- Multiple pension support (military, government, corporate)

### 10. Healthcare Cost Projection
Model healthcare expenses through retirement:
- Pre-Medicare costs (age 65 gap coverage)
- Medicare Parts A, B, D premiums
- Medigap/Medicare Advantage premiums
- Out-of-pocket maximums and deductibles
- Healthcare inflation rate (historically ~5-6%)
- Long-term care cost estimates

### 11. Required Minimum Distribution Optimization
Enhance RMD handling:
- Project future RMDs based on account growth
- Identify years where RMDs push into higher brackets
- Suggest pre-emptive Roth conversions to reduce RMDs
- QCD (Qualified Charitable Distribution) modeling
- Aggregate RMDs across multiple traditional accounts

### 12. Tax-Loss Harvesting Tracker
Track taxable account tax efficiency:
- Cost basis tracking by lot
- Identify harvestable losses
- Wash sale rule awareness (30-day window)
- Estimate tax savings from harvesting
- Carryforward loss tracking

### 13. Estate Planning Projections
Model wealth transfer:
- Project estate value at life expectancy
- Federal estate tax exemption tracking ($13.99M in 2025)
- State estate/inheritance tax modeling
- Beneficiary account projections (inherited IRA rules)
- Annual gift exclusion tracking ($19,000 in 2025)

### 14. Part-Time Income / Phased Retirement
Model transitional retirement income:
- Part-time work income by year
- Consulting/freelance income projections
- Rental income streams
- Impact on Social Security earnings test (before FRA)
- Gradual income reduction schedules

### 15. Debt Payoff Integration
Factor debts into retirement readiness:
- Mortgage payoff timeline
- Student loans (including PSLF scenarios)
- Auto loans and other consumer debt
- Debt-free target date alignment with retirement
- Interest savings from early payoff vs investing

### 16. Emergency Fund / Cash Reserve Modeling
Model liquidity needs:
- Target emergency fund size (months of expenses)
- Cash bucket strategy for sequence risk
- CD ladder or bond tent modeling
- Separate from investment portfolio
- Drawdown priority during market downturns

### 17. Spousal Planning / Survivor Scenarios
Two-person household modeling:
- Dual income projections
- Separate retirement ages
- Survivor Social Security benefits
- Expense reduction on first death
- Widow(er) tax bracket changes (MFJ to Single)

### 18. Asset Location Optimization
Optimize which assets go in which accounts:
- Tax-efficient fund placement recommendations
- Bonds in traditional vs stocks in Roth analysis
- Rebalancing across account types
- Tax drag calculations by asset location
- Projected tax savings from optimal location

### 19. Annuity Modeling
Evaluate annuity options:
- SPIA (Single Premium Immediate Annuity) quotes
- Deferred income annuities (DIAs/QLACs)
- Variable annuity projections
- Compare annuity vs systematic withdrawal
- Longevity insurance for late-life income floor

### 20. Dividend and Interest Income Tracking
Model investment income:
- Qualified vs ordinary dividend treatment
- Tax-exempt municipal bond income
- Interest income from bonds/CDs
- REIT distribution tax treatment
- Dividend growth projections

### 21. Geographic / Tax Residency Planning
Model state tax impact:
- State income tax comparison
- No-income-tax state scenarios (FL, TX, NV, etc.)
- State tax on retirement income (some exempt pensions/SS)
- Property tax estimates by state
- Cost of living adjustments by region

### 22. Backdoor Roth / Mega Backdoor Strategies
Model advanced contribution strategies:
- Backdoor Roth IRA process
- Mega backdoor Roth (after-tax 401k conversions)
- Pro-rata rule tracking for backdoor Roth
- Annual contribution optimization
- Employer plan eligibility requirements

### 23. Social Security Taxation Modeling
Detailed SS tax calculations:
- Provisional income calculation
- 50% vs 85% SS taxation thresholds
- Combined income optimization
- Roth vs traditional withdrawal to minimize SS tax
- State taxation of Social Security (13 states tax it)

### 24. Retirement Spending Patterns
Model realistic spending curves:
- "Go-go, slow-go, no-go" phases
- Higher early retirement spending (travel, hobbies)
- Declining spending in later years
- Healthcare cost spike in final years
- Custom spending profiles by category

### 25. Catch-Up Contribution Optimization
Maximize contributions for 50+ savers:
- Age-based catch-up eligibility tracking
- Super catch-up for 60-63 (SECURE 2.0)
- Optimal catch-up allocation (traditional vs Roth)
- HSA catch-up contributions (55+)
- Project impact of maximizing catch-ups

### 26. Sequence of Returns Risk Analysis
Evaluate early retirement vulnerability:
- Historical worst-case sequence testing
- Guardrails strategy (flexible spending rules)
- Bond tent / rising equity glide path
- Bucket strategy effectiveness
- Probability of recovery after bad sequence

### 27. Net Unrealized Appreciation (NUA) Strategy
Optimize employer stock distributions:
- NUA tax benefit calculation
- Compare NUA vs rollover to IRA
- Lump-sum distribution requirements
- Capital gains vs ordinary income comparison
- Optimal timing for NUA distribution

### 28. Charitable Giving Optimization
Tax-efficient philanthropy:
- QCD from IRA (age 70.5+, up to $105,000 in 2025)
- Donor-advised fund strategies
- Bunching deductions across years
- Appreciated stock donations
- Charitable remainder trusts modeling

---

## Implementation Priority (Updated)

| Priority | Feature | Complexity | Impact |
|----------|---------|------------|--------|
| 1 | 2025 Tax Year Update | Low | High |
| 2 | Contribution Limit Tracking | Low | Medium |
| 3 | Healthcare Cost Projection | Medium | High |
| 4 | Pension Income Modeling | Medium | High |
| 5 | Social Security Optimization | Medium | High |
| 6 | Spousal Planning / Survivor Scenarios | High | High |
| 7 | Inflation-Adjusted View | Medium | Medium |
| 8 | Roth Conversion Modeling | High | High |
| 9 | RMD Optimization | Medium | High |
| 10 | Social Security Taxation Modeling | Medium | Medium |
| 11 | Retirement Spending Patterns | Medium | High |
| 12 | Part-Time Income / Phased Retirement | Low | Medium |
| 13 | IRMAA Thresholds | Medium | Medium |
| 14 | Sequence of Returns Risk Analysis | High | High |
| 15 | Emergency Fund / Cash Reserve | Low | Medium |
| 16 | Debt Payoff Integration | Medium | Medium |
| 17 | Estate Planning Projections | Medium | Medium |
| 18 | Geographic / Tax Residency Planning | Medium | Medium |
| 19 | Backdoor Roth / Mega Backdoor | Medium | Medium |
| 20 | Monte Carlo Simulation | High | High |
| 21 | Asset Location Optimization | High | Medium |
| 22 | Scenario Comparison | High | High |
| 23 | Catch-Up Contribution Optimization | Low | Medium |
| 24 | Tax-Loss Harvesting Tracker | High | Medium |
| 25 | Dividend and Interest Tracking | Medium | Low |
| 26 | Annuity Modeling | High | Medium |
| 27 | NUA Strategy | Medium | Low |
| 28 | Charitable Giving Optimization | Medium | Medium |

---

## Notes

- Features 1-2 are data updates, minimal code changes
- Features 3-4 enhance existing calculations
- Features 5-8 are significant new functionality
- All features should maintain dark mode support
- Consider mobile responsiveness for new UI elements
