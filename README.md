# ARC Solutions

## ARC v1

| Author(s) | Score | Estimated Cost Per task | Paper | Code | Description |
| --------- | ----- | ----------------------- | ----- | ---- | ----------- |
| Puget | 17% (estimate on public eval) [^1] | $0.03 [^2] | [A 2D nGPT model for ARC prize](https://github.com/jfpuget/ARC-AGI-Challenge-2024/blob/main/arc.pdf) | [Github](https://github.com/jfpuget/ARC-AGI-Challenge-2024/) | Trains a small (42M params; GPT2-like) transformer to predict output of ARC tasks. |
| Berman | 53.6% (semi private); 58.5% (public eval) | $20 [^3] | [Evolutionary Test-time Compute](https://jeremyberman.substack.com/p/how-i-got-a-record-536-on-arc-agi) | [Github](https://github.com/jerber/arc_agi); [Kaggle](https://www.kaggle.com/code/jerber/jeremy-arc) | Uses LLMs (Claude) to create Python programs and evolves these based on fitness function (how many examples solved completely; how many individual cells the function got correct). |

[^1]: The solution achieves up to 26% accuracy on constant-sized tasks on the public eval set. Performance on the private eval set is unknown. 
[^2]: According to the paper, 100 tasks takes around 2 hours to run on Kaggle on (assumed) 1xP100 at ~$1.50 per hour.
[^3]: Assuming maximum budget used for semi-private leaderboard (500 tasks for $10,000).
