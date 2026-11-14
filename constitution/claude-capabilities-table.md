# Claude Free Tier Capabilities Table (Floor 1)

**Group Members:** [Insert your names here]

## 1. Free Tier Capabilities Comparison (Based on Documentation)

| Capability / Limitation | Available in Free? | Description | Source of Claim | Source Reliability |
| :--- | :--- | :--- | :--- | :--- |
| Creating Projects (`Projects`) | Yes (up to 5 projects) | Allows setting base system prompts (`Set project instructions`) and uploading reference files (`Project knowledge`). | Official Anthropic Documentation: *What are Projects?* (accessed: 14.11.2026) | High (official developer documentation) |
| Custom Skills (`Skills`) | Yes | Uploading ZIP archives containing `skill.md` and scripts via `Customize -> Skills`. | Official Anthropic Documentation: *Using Skills in Claude* (accessed: 14.11.2026) | High (official developer documentation) |
| Code Execution & File Creation | Yes | Running code and calculations when the `Code execution and file creation` toggle is enabled in `Settings -> Capabilities`. | Official Anthropic Documentation: *Create and Edit Files with Claude* (accessed: 14.11.2026) | High (official developer documentation) |
| Message Quota (Rate Limit) | Limited | Dynamic daily/session message quota depending on context length and server load. | Blog review: *DEV Community — Claude Free Plan vs Pro 2026* (accessed: 14.11.2026) | Medium (third-party technical review; exact message count is not disclosed by Anthropic) |
| Deep Research Mode | No | Autonomous multi-step search across academic databases is unavailable in the Free tier. | Course Materials (Meeting 1, Slide 56) & *DEV Community — Claude Free Plan vs Pro 2026* | Medium / Internal course source |

## 2. Verification of Claude's Self-Description (Step 2 per Slide 59)
- **Prompt sent to Claude:** "Describe accurately which features are available in your Free tier (`Projects`, `Skills`, `Code Execution`, message limits) and which are unavailable."
- **Comparison with the table:** Without uploaded documentation, Claude frequently confuses its current pricing tiers (for example, claiming that `Projects` or `Skills` are exclusive to the paid Pro plan because its training data is outdated). Conclusion: the tool itself is unreliable when describing its own technical limits and requires verification against official Anthropic documentation.
