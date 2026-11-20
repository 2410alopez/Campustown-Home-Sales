# Agent log

Add a dated entry each time you work with your AI coding agent, with the newest entry at the bottom. Each entry records what you asked the agent, what it produced, and what you checked or changed. Paste your key prompts in exactly as you typed them. Include at least one time the agent got something wrong, and how you caught it.

Copy this outline for each entry:

```markdown
## YYYY-MM-DD: What you worked on

- **Asked:** "Paste your prompt here."
- **Agent produced:** What it made or changed.
- **Checked or changed:** How you checked it, and what you fixed.
```

## 2026-11-19: Fix and refine median price chart

- **Asked:** "Pull the latest main first, then read AGENTS.md and docs/data_description_sheet.md.\
\
Update my website to match the attached screenshots: keep the clean layout and large heading from the first image, and use the working teal horizontal bars from the second image.\
\
Design:\
- Light gray background, dark navy text, and a centered content area.\
- Small teal “COLLEGE-TOWN HOME SALES” label above the heading.\
- Large heading: “What homes sell for in college towns”.\
- Short introduction explaining the comparison.\
- White chart card with rounded corners and a subtle border.\
- Cities and states on the left, horizontal bars in the middle, and whole-dollar median prices on the right.\
- Teal bars over pale gray tracks. Scale each bar proportionally to its median price, with the highest median filling the track.\
- Rank cities from highest to lowest median price.\
- Include a matching table below the chart.\
- Make the layout readable on desktop and mobile.\
\
Data:\
- Calculate everything from the actual provided dataset.\
- Exclude sales below $10,000 and clearly state that rule. Correct the $1,000 note shown in the first screenshot.\
- Show the actual number of cities and qualifying sales.\
- Calculate medians before rounding; display prices as whole-dollar USD amounts.\
- Use the same calculated values in the chart and table.\
- Do not hardcode the screenshot’s prices or counts.\
- Do not edit the original dataset files.\
\
Fix the empty bars visible in the first screenshot. Check the rendered page to verify that the teal fills are visible, their lengths vary correctly, and the chart and table agree.\
\
Keep the existing GitHub Pages publishing setup working. Update AGENT_LOG.md, then explain what changed and how you verified it."
- **Agent produced:** Fast-forwarded to the latest `main`, then updated `index.html` with the $10,000 minimum sale-price rule, dataset-derived coverage counts, proportionally scaled teal bars, and a matching city table. Kept the page static and the existing Pages workflow unchanged.
- **Checked or changed:** The previous chart's bars were empty because the CSS width was applied to an inline span; the screenshot exposed that issue. Changed the fill to `display: block`. Checked the rendered chart: all 18 teal fills are visible, lengths vary with median price, and the top bar fills its track. Recomputed qualifying rows and medians independently from the CSV (35,402 qualifying sales across 18 cities) and confirmed the rendered table uses the same ordered results as the chart. `git diff --check` passed.
