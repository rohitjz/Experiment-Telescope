# Experiment Lab

**Design statistically rigorous A/B tests. Know your sample size before you start, not after you've wasted traffic.**

A sample size calculator built for product teams that actually explains the math. Covers four metric types, teaches core concepts through real analogies, and includes worked case studies so you understand the "why" behind every number.

**Live site:** [rohitjz.github.io/experiment-telescope](https://rohitjz.github.io/Experiment-Telescope/)

<img width="1109" height="1271" alt="image" src="https://github.com/user-attachments/assets/3b4d5487-072a-4b9f-a542-6d174b03c1e7" />


## What It Does

### Four Calculator Modes

| Mode | Metric Type | Example Use Cases |
|------|-------------|-------------------|
| **Conversion** | Binary (yes/no) | Signup rate, click-through rate, purchase rate, day-N retention |
| **Averages** | Continuous (numeric) | Session duration, page load time, average order value, NPS |
| **Counts** | Discrete occurrences | Pages viewed, items added to cart, messages sent, support tickets |
| **Revenue** | Zero-inflated | Revenue per visitor, spend per session, donations per user |

Each mode gives you:
- **Sample size per group and total**, calculated from your inputs
- **Duration estimate** based on your daily traffic
- **Sensitivity table** showing how adjusting MDE changes sample size
- **Pro tips** and warnings specific to your metric's characteristics
- **Plain-English explanation** of what the result means

### Learn Tab

Not just a calculator. The Learn section covers:

- **6 core concepts** (SD, MDE, Confidence, Power, Sample Size, Distributions), each explained through multiple real-world analogies
- **4 worked case studies** across e-commerce checkout, content engagement, mobile push notifications, and marketplace trust badges
- **Pre-launch checklist** covering the 7 things teams get wrong most often

### Configurable Settings

- Confidence level (90%, 95%, 99%)
- Statistical power (70%, 80%, 90%)
- One-sided vs two-sided hypothesis
- Number of variants (A/B, A/B/C, etc.)
- Daily traffic for duration estimates

## Why This Exists

Most sample size calculators give you a number and nothing else. Teams plug in values they don't understand, get a result they can't interpret, and run underpowered tests that miss real effects. This tool teaches you the tradeoffs as you use it.

## Tech

Single React component (740 lines). No external dependencies beyond React itself.

- Statistical engine: normal PPF approximation for z-scores, handles binary/continuous/count/zero-inflated distributions
- Apple-inspired design system using Figtree + JetBrains Mono
- Inline styles with a token system (no CSS framework)
- Sensitivity analysis at 0.5x, 0.75x, 1x, 1.25x, 1.5x, 2x MDE
- Skew buffer (+30%) for non-normal continuous metrics
- Zero-inflation buffer (+40%) for revenue metrics
- Overdispersion detection for count metrics (variance/mean ratio)

## Run Locally

This is a JSX file that needs React. Quickest way to run it:

```bash
npm create vite@latest experiment-lab -- --template react
cd experiment-lab
# Replace src/App.jsx with experiment-lab.jsx
cp /path/to/experiment-lab.jsx src/App.jsx
npm install
npm run dev
```

Or load it in any existing React project by importing the default export.

## License

MIT
