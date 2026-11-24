# Part C: Results and interpretation

Results come from Part A's final logistic model, fitted on the training set (n = 12,004). All effects are predictive associations, not causal effects. Predicted probabilities are for a typical first-time creator: Media & Entertainment, images, no video, 7 reward tiers.

---

## Slide 1: Which pre-launch factors move the odds of success?
**Figure:** `fig1_or_forest.png`

**Key points**
- **Funding goal (H1):** each doubling of the goal cuts the odds of success by 38% (OR 0.62).
- **Duration (H2):** each extra 10 days cuts the odds by 15% (OR 0.85), for a campaign with an average goal.
- **Creator track record (H4):** the strongest positive signal. A previous success roughly triples the odds (OR 3.14).
- **Presentation (H5):**
  - Each extra reward tier raises the odds by 10% (OR 1.10).
  - Images and video are not significant. 91% of campaigns already have images, so having them does not set a campaign apart.
- **Category:** after controlling for goal and track record, Creative Arts has lower odds than Media & Entertainment (OR 0.71), even though its raw success rate is the highest (88%). Its high raw rate comes from smaller goals (median $1,868) and more repeat creators (61%). Food has the lowest raw rate (63%), but it is not significantly different once we control for its much larger goals (median $11,111).

**Speaker notes (~50 s):** "Each dot is an odds ratio: left of the line lowers the odds of success, right of the line raises them. The goal is the biggest lever creators control: every doubling cuts the odds by about 38%. Longer campaigns also hurt. The strongest signal is the creator's track record, which roughly triples the odds. For presentation, more reward tiers help, but simply having images or video doesn't, because almost everyone has them. One surprise: Creative Arts looks like the most successful category in raw numbers, but once we control for goal size and track record, it actually does worse than Media. Its high raw success rate comes from small goals and experienced creators."

---

## Slide 2: Longer campaigns hurt more when the goal is high (H3)
**Figure:** `fig2_interaction.png`

| Goal | 15 days | 30 days | 45 days |
|---|---|---|---|
| 25th pct ($751) | 93.7% | 92.6% | 91.5% |
| Median ($2,961) | 86.5% | 83.1% | 79.1% |
| 75th pct ($7,806) | 78.1% | 71.8% | 64.5% |

**Key points**
- **H3 is supported in the main model:** interaction OR 0.97 (p = 0.004). The likelihood-ratio test also favors keeping the interaction (p = 0.004).
- **But it is fragile (Part D):** dropping the 20 most influential campaigns raises p to 0.105, and dropping goals under $100 or over $1M raises it to 0.43. So the interaction is driven largely by extreme goals.
- **Effect of +10 days on the odds:**
  - small goal: −10%;
  - median goal: −16%;
  - large goal: −20%.
- **Going from 15 to 45 days costs:**
  - only about 2 points of success probability for a small goal;
  - about 14 points for a large goal.

**Speaker notes (~45 s):** "This was the hypothesis we added after the PoC. Because goal and duration are correlated, we let the effect of duration depend on the goal. The lines show it clearly. For a small goal, the line is almost flat, so duration barely matters. For a large goal, stretching from 15 to 45 days drops the predicted success rate from 78% to 65%. A long campaign seems to signal weak demand, and that matters most when the creator is asking for a lot. One caution from our diagnostics: this interaction depends heavily on campaigns with extreme goals, so we treat it as suggestive rather than conclusive. The main effects of goal and duration, on the other hand, are robust."

---

## Slide 3: A track record offsets a much bigger goal (H1 + H4)
**Figure:** `fig3_goal_by_creator.png`

| Goal (30 days) | First-time creator | Repeat creator |
|---|---|---|
| $1,000 | 91% | 97% |
| $5,000 | 78% | 92% |
| $10,000 | 68% | 87% |
| $20,000 | 57% | 81% |
| $50,000 | 42% | 69% |

**Key point:** a repeat creator asking for $20,000 has about the same predicted chance (81%) as a first-time creator asking for about $3,700. The gap widens as the goal grows, so a track record matters most for ambitious campaigns.

**Speaker notes (~35 s):** "Putting H1 and H4 together: both groups lose probability as the goal grows, but first-time creators lose it much faster. At $50,000, a first-timer has a 42% chance and a repeat creator 69%. In other words, a successful past campaign buys you roughly five times the goal at the same level of risk."

---

## Slide 4: Hypothesis scorecard
**Figure:** `fig4_hypothesis_table.png`

| | Hypothesis | Evidence | Verdict |
|---|---|---|---|
| H1 | Higher goal → lower success | OR 0.62 per doubling (p<0.001) | Supported |
| H2 | Longer duration → lower success | OR 0.85 per +10 days (p<0.001) | Supported |
| H3 | Duration hurts more for high goals | OR 0.97 (p=0.004); p=0.43 without extreme goals | Supported in main model, not robust |
| H4 | Previous success → higher success | OR 3.14 (p<0.001) | Supported |
| H5 | Richer page → higher success | Reward tiers OR 1.10 (p<0.001); images and video n.s. | Partly supported |

**Honest caveat to mention:** H3 is significant in the main model, but it is not robust: it loses significance when extreme goals are removed (Part D), and it adds almost no predictive power (test AUC 0.814 vs 0.813, Part B). We report it as suggestive. H1, H2, H4 and the reward-tier effect are robust in every check.

---

## Slide 5: Recommendations

**For creators**
1. **Set the smallest goal that funds the project.** Use stretch goals for anything extra: each doubling of the goal cuts the odds by 38%.
2. **Keep campaigns short, especially with a large goal.** A $7,800 goal at 45 instead of 30 days drops the predicted success rate from 72% to 65%.
3. **Offer more reward tiers.** Going from 3 to 10 tiers raises the predicted success rate from 77% to 87% at the median goal.
4. **First-time creators: start small to build a track record.** A previous success triples the odds on the next campaign.

**For backers and investors**
1. **Treat a creator's track record as the strongest credibility signal.**
2. **Flag first-time, high-goal, long-duration campaigns as the highest risk.**
3. **Don't rely on media alone.** Having images or video does not predict success.

**Speaker notes (~40 s):** read the bold lines and give one number for each.

---

## Limitations (for E's slide or the report)
- **Predictive, not causal:** for example, a short campaign may succeed because confident creators choose short campaigns.
- **Sample selection:** the dataset seems to include only projects with at least 10 backers, so the 83% success rate is inflated and the predicted probabilities are likely too high in absolute terms. The relative effects (odds ratios) are more reliable.
- **Pre-launch information only:** early momentum during the campaign is not captured (see the two-stage system in next steps).

---

## 中文提示（给自己看的）
- **展示时间：**C 部分大约 3 分钟。Slide 4（打分表）可以快速带过，或者和 Slide 1 合并。
- **最有亮点的两处：**
  - Slide 2：H3 是 PoC 之后新加的假设，结果被支持。
  - Slide 1 里 Creative Arts 的"反转"：原始成功率最高，控制目标和创作者历史后反而更低。这一条很能体现 insight。
- **主动承认交互项的局限：**交互项在主模型里显著，但去掉极端目标后就不显著了（D 的稳健性检验），对 AUC 也几乎没有提升。讲成"有迹象但不稳健（suggestive）"。
- **所有概率的前提：**都是在"典型首次创作者"这个画像下算的，图下面已经注明了。
