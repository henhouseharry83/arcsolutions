# ARC Solutions

## ARC v1

| Author(s) | Score | Estimated Cost Per task | Paper | Code | Description |
| --------- | ----- | ----------------------- | ----- | ---- | ----------- |
| Puget | 17% (estimate on public eval) [^1] | $0.03 [^2] | [A 2D nGPT model for ARC prize](https://github.com/jfpuget/ARC-AGI-Challenge-2024/blob/main/arc.pdf) | [Github](https://github.com/jfpuget/ARC-AGI-Challenge-2024/) | Trains a small (42M params; GPT2-like) transformer model to predict output of ARC tasks directly. A grid cell attends to all cells in the same row, and the same column. |
| Berman | 53.6% (semi private); 58.5% (public eval) | $20 [^3] | [Evolutionary Test-time Compute](https://jeremyberman.substack.com/p/how-i-got-a-record-536-on-arc-agi) | [Github](https://github.com/jerber/arc_agi); [Kaggle](https://www.kaggle.com/code/jerber/jeremy-arc) | Uses LLMs (Claude) to create Python programs and evolves these based on fitness function (how many examples solved completely; how many individual cells the function got correct). |
| Li et al. | 56.75% (public eval); 19% (private eval, limited by compute) | Unknown (>$0.18 per task for public eval [^4]) |[Combining Induction and Transduction for Abstract Reasoning](https://arxiv.org/abs/2411.02272) | [Github](https://github.com/xu3kev/BARC) | Ensembles program induction and transduction (direct solution prediction). Models based on Llama3.1-8B-instruct fine-tuned on hundreds of thousands of synthetic examples, with test-time training. 1st Place Paper Award Winner |

| Author(s) | Score | Estimated Cost Per Task | Paper | Code | Description |
|---|---|---|---|---|---|

| Akyürek et al. | 61.9% (Public Evaluation Set)¹ | $0.28 - $2.80² | [The Surprising Effectiveness of Test-Time Training for Abstract Reasoning](https://arxiv.org/abs/2411.07279) | [mhn/arc24](https://github.com/mhn/arc24) | 2nd Place Paper Award Winner. Employs test-time training for abstract reasoning. |
| Bonnet & Macfarlane | Not Listed | Not applicable |([https://arxiv.org/abs/2311.14359](https://arxiv.org/abs/2311.14359)) | Not Listed | 3rd Place Paper Award Winner. Focuses on searching latent program spaces. |
| the ARChitects (Franzen et al.) | 53.5% (Private Evaluation Set) | Not Listed | [The LLM ARChitect: Solving ARC-AGI Is a Matter of Perspective](https://arxiv.org/abs/2412.04604v2) | [ARChitects/arc-prize-2024](https://github.com/ARChitects/arc-prize-2024) | 1st Place High Score Winner. Leverages LLMs to guide program search and combines it with test-time training. |
| Guillermo Barbadillo | 40% (Private Evaluation Set) | $0.004 - $0.40³ | [Omni-ARC](https://arxiv.org/abs/2412.04604v2) | [gbarbadillo/omni-arc](https://github.com/gbarbadillo/omni-arc) | 2nd Place High Score Winner. Employs a hybrid approach combining program synthesis with a transduction model. |
| alijs | 40% (Private Evaluation Set) | Not Listed | Not Listed | [alijs/arc-prize-2024](https://github.com/alijs/arc-prize-2024) | 3rd Place High Score Winner. Details of the approach not publicly available. |
| William Wu | 37% (Private Evaluation Set) | Not Listed | Not Listed | [wuziheng/arc-prize-2024](https://github.com/wuziheng/arc-prize-2024) | 4th Place High Score Winner. Details of the approach not publicly available. |
| PoohAI | 37% (Private Evaluation Set) | Not Listed | Not Listed | [pooh-ai/arc-prize-2024](https://github.com/pooh-ai/arc-prize-2024) | 5th Place High Score Winner. Details of the approach not publicly available. |
| MARA(BARC) + MIT (Akyürek et al.) | 47.5% (Semi-Private Evaluation Set) | Not Listed | [The Surprising Effectiveness of Test-Time Training for Abstract Reasoning](https://arxiv.org/abs/2311.11394) | [mhn/arc24](https://github.com/mhn/arc24) | 2nd Place on the ARC-AGI-Pub leaderboard. Employs test-time training and fine-tuning on synthetic data. |
| Ryan Greenblatt | 43% (Semi-Private Evaluation Set) | $20⁵ | Not Listed | [ryangreenblatt/arc-agi-pub](https://github.com/ryangreenblatt/arc-agi-pub) | 3rd Place on the ARC-AGI-Pub leaderboard. Utilizes GPT-4o for LLM-guided program synthesis. |
| OpenAI o3 (high-efficiency) | 75.7% (Semi-Private Evaluation Set) | $20⁶ | Not Listed | Not Listed | Achieved a breakthrough score on the ARC-AGI-Pub Semi-Private Evaluation set using a high-efficiency configuration. |
| OpenAI o3 (low-efficiency) | 87.5% (Semi-Private Evaluation Set) | Not Listed | Not Listed | Not Listed | Achieved an even higher score on the ARC-AGI-Pub Semi-Private Evaluation set using a low-efficiency, high-compute configuration. |
| ironbar | 50% (Public Evaluation Set)⁷ | $0.16⁸ | Not Listed | [ironbar/arc24](https://github.com/ironbar/arc24) | Uses GPT-4 to generate Python implementations of the transformation rule and selects based on correctness. |
| mhn | 40% (Public Evaluation Set) | $0.02⁹ | Not Listed | [mhn/arc24](https://github.com/mhn/arc24) | Fine-tunes a transformer on multiple tasks related to ARC problems, incorporating test-time fine-tuning. |
| luciano | 30% (Public Evaluation Set) | $0.0001¹⁰ | Not Listed | [luciano/arc24](https://github.com/luciano/arc24) | Fine-tunes Qwen2.5-0.5B-Instruct on publicly available ARC datasets, uses test-time fine-tuning, data augmentation, and ensembles with the 2020 public solution. |
| 2020 Kaggle Winner (icecuber) | 20% (Private Evaluation Set) | Not applicable¹¹ | Not Listed | Not Listed | Used a DSL with 142 hand-crafted grid operations. |
| Fletcher-Hill | 41% (Public Evaluation Set, subset)¹³ | $0.08 - $0.80¹⁴ | [Mini-ARC: Solving Abstraction and Reasoning Puzzles with Small Transformer Models](https://arxiv.org/abs/2412.04604) | [pfletcherhill/mini-arc](https://github.com/pfletcherhill/mini-arc) | Focuses on solving ARC puzzles with small transformer models. |
| Ouellette | Not Listed | Not Listed | [Towards Efficient Neurally-Guided Program Induction for ARC-AGI](https://arxiv.org/abs/2411.17708) | [SimonOuellette35/GridCoder2024](https://github.com/SimonOuellette35/GridCoder2024) | Explores efficient neurally-guided program induction for ARC-AGI. |

[^1]: The solution achieves up to 26% accuracy on constant-sized tasks on the public eval set. Performance on the private eval set is unknown. 
[^2]: According to the paper, 100 tasks takes around 2 hours to run on Kaggle on (assumed) 1xP100 at ~$1.50 per hour.
[^3]: Assuming maximum budget used for semi-private leaderboard (500 tasks for $10,000).
[^4]: The paper states that "Our flagship model is too expensive to run on the private test set hosted by Kaggle", so this must exceed ~$0.18 per task.

¹ Accuracy on the public evaluation set[2].
² Assuming a runtime of 1-10 minutes per task on an NVIDIA Tesla T4 GPU, which costs $0.28 per hour on Google Cloud[2].
³ Assuming a runtime of 6-60 minutes per task on an NVIDIA Tesla T4 GPU[3].
⁴ Based on a cost of $200 for 75 minutes of runtime on the training set, extrapolated to the full evaluation set[4].
⁵ Based on consuming 33M tokens with a retail cost of $0.00006 per 1k tokens for OpenAI o3[5].
⁶ Based on consuming 33M tokens with a retail cost of $0.00006 per 1k tokens for OpenAI o3[6].
⁷ Accuracy on the public test set[7].
⁸ Based on 8,000 Python implementations per problem and assuming $0.00002 per 1k tokens for GPT-4[7].
⁹ Based on training a transformer model with an estimated cost of $8 per hour for 10 hours[7].
¹⁰ Based on fine-tuning Qwen2.5-0.5B-Instruct with an estimated cost of $0.10 per hour for 2 hours[7].
¹¹ Cost information not available for the 2020 Kaggle competition winner[8].
¹² Based on training for one day on an 8 A100 GPU machine, assuming a cost of $14 per hour per A100 GPU on Google Cloud[9].
¹³ Accuracy on a subset of the public evaluation set with grids no larger than 12x12[10].
¹⁴ Assuming a runtime of 5-50 minutes per task on an NVIDIA Tesla T4 GPU[10].

