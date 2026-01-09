# PROGRESS.md - The Save Game

## Architecture Snapshot

A React retirement planning calculator with two main phases:

1. **Accumulation** - Projects account growth from current age to retirement
2. **Withdrawal** - Simulates tax-optimized withdrawals in retirement

**Key Files:**
- `@src/App.tsx` - Main state holder, localStorage persistence, dark mode
- `@src/utils/projections.ts` - Accumulation phase calculations
- `@src/utils/withdrawals.ts` - Tax-optimized withdrawal strategy
- `@src/utils/taxes.ts` - Federal, capital gains, and state tax brackets
- `@src/types/index.ts` - Core types (Account, Profile, Assumptions, Results)
- `@src/hooks/useRetirementCalc.ts` - Orchestrates all calculations

**Data Flow:** App.tsx (state) -> useRetirementCalc (calculations) -> Chart components (Recharts)

---

## Completed Tasks

- [x] Initial project setup with Vite + React + TypeScript
- [x] Accumulation phase calculations
- [x] Withdrawal phase with tax-optimized strategy
- [x] Tax calculations (federal, capital gains, state)
- [x] Chart visualizations with Recharts
- [x] Dark mode support
- [x] localStorage persistence
- [x] Tailwind v4 integration
- [x] GitHub Pages / Docker deployment support
- [x] Project scaffold files (PROGRESS.md, ARCHIVE.md, EXIT_RULES.md)

---

## Current Status

**Last Session (2026-01-08):** Initialized project scaffold with session management files. Created PROGRESS.md (save game), ARCHIVE.md (trashcan), and EXIT_RULES.md (exit protocol). Kept existing CLAUDE.md with project-specific instructions intact.

---

## Immediate Next Steps

1. _Awaiting next feature request_
2. _TBD_
3. _TBD_

---

## Mental Threads

_Hidden logic, gotchas, and traps to remember:_

- **RMDs start at age 73** - Traditional accounts require minimum distributions
- **Withdrawal order matters** - RMD -> Fill 12% bracket -> Roth -> Taxable -> HSA -> Traditional fallback
- **Dark mode prop** - All chart components need `isDarkMode` prop for proper styling
- **Tailwind v4 dark mode** - Requires `@custom-variant dark (&:where(.dark, .dark *));` directive
- **Session workflow** - Use /cleanup, /save, then trash can icon to reset session
- **No tasks.md** - Project does not have a tasks.md file; use PROGRESS.md for task tracking
