# ARC Solutions

## ARC v1

| Author(s) | Score | Estimated Cost Per task | Paper | Code | Description |
| --------- | ----- | ----------------------- | ----- | ---- | ----------- |
| Puget | 17% (estimate on public eval) [^1] | $0.03 [^2] | [A 2D nGPT model for ARC prize](https://github.com/jfpuget/ARC-AGI-Challenge-2024/blob/main/arc.pdf) | [Github](https://github.com/jfpuget/ARC-AGI-Challenge-2024/) | Trains a small (42M params; GPT2-like) transformer model to predict output of ARC tasks directly. The transformer's attention mechanism is designed such that a grid cell attends to all cells in the same row, and also the same column. |
| Berman | 58.5% (public eval); 53.6% (semi-private) | $20 [^3] | [Evolutionary Test-time Compute](https://jeremyberman.substack.com/p/how-i-got-a-record-536-on-arc-agi) | [Github](https://github.com/jerber/arc_agi); [Kaggle](https://www.kaggle.com/code/jerber/jeremy-arc) | Uses LLMs (Claude) to create Python programs and evolves these based on fitness function (how many examples solved completely; how many individual cells the function got correct). Uses a combination of single-parent evolution and a “pooling” approach that combines multiple parent functions into a single revision prompt. |
| Li et al. | 56.75% (public eval); 19% (private, limited by compute) | Unknown (>$0.18 per task for public eval [^4]) |[Combining Induction and Transduction for Abstract Reasoning](https://arxiv.org/abs/2411.02272) | [Github](https://github.com/xu3kev/BARC) | Uses an ensemble of program induction and transduction (direct solution prediction) approaches. Models based on Llama3.1-8B-instruct were fine-tuned on hundreds of thousands of synthetic examples. Test-time training was also employed. 1st Place Paper Award Winner |
| Akyürek et al. | 53% (public eval); 62.8% (public eval, ensembled with Li at al.); 47.5% (semi-private, ensembled with Li et al.) | $0.44[^5] | [The Surprising Effectiveness of Test-Time Training for Abstract Reasoning](https://arxiv.org/abs/2411.07279) | [Github](https://github.com/mhn/arc24); [Kaggle](https://www.kaggle.com/code/xu3cpn/ensemble-induction-and-transduction) | Employs test-time training by fine-tuning 8B Llama 3 model on task variations, including example omissions and geometrical transformations. Also employs a hierarchical voting strategy at test-time, and initial fine-tuning of the model. Best score is an ensemble with Li et al. 2nd Place Paper Award Winner |
| Bonnet et al. | 9.9% (public eval); 3% (private) | Unknown |[Searching Latent Program Spaces](https://github.com/clement-bonnet/lpn/blob/7f86b1d11ea37ba173700dbac8604393eac6da37/paper.pdf) | [Github](https://github.com/clement-bonnet/lpn) | Introduces a Latent Program Network (LPN), which is a neural network that learns the latent space of possible programs. In addition, gradient-based test-time search is performed on the latent space. 3rd Place Paper Award Winner. |
| Franzen et al. (The ARChitects) | 53.5% (private) 56.5% (private, after competition deadline) | $0.08 [^6] | [The LLM ARChitect: Solving ARC-AGI Is a Matter of Perspective](https://github.com/da-fr/arc-prize-2024/blob/main/the_architects.pdf) | [Github](https://github.com/da-fr/arc-prize-2024); [Kaggle](https://www.kaggle.com/code/gregkamradt/arc-prize-v8?scriptVersionId=211457842) | Uses fine-tuning and test-time training of NeMo-Minitron-8B LLM to perform transduction (direct output prediction). Two phases of fine-tuning are performed before test time on re-arc and geometric transformations, and one phase is performed at test time on geometric and example omission / reordering. A depth-first search scoring method is employed, along with a probabalistic approach for final candidate selection. The number of tokens in the LLM is reduced to 64 symbols. |
| Barbadillo | 40% (private) | $0.18 [^7] | [Omni-ARC](https://arxiv.org/abs/2412.04604v2) | [Kaggle](https://www.kaggle.com/code/ironbar/single-task-test-time-fine-tuning-for-arc24?scriptVersionId=199282752) | Fine-tunes a Qwen2.5-0.5B-Instruct LLM based on a large dataset of various ARC and ARC-like tasks, included data augmentation. Test-time training is performed, also using data augmentation. Final predictions are obtained using a voting system. The solution is ensembled with some solutions from the 2020 competition. |
| Liukis | 40% (private) | $0.18 [^8] | [ARC Prize 2024 4th place solution¶](https://www.kaggle.com/code/gregkamradt/arc-prize-2024-solution-4th-place-score-40-811b7) | [Kaggle](https://www.kaggle.com/code/gregkamradt/arc-prize-2024-solution-4th-place-score-40-811b72) | A guided brute-force approach to try various algorithms / functions was ensembled with some solutions from the 2020 competition. |
| Mikhalev et al. (PoohAI) | 37% (Private Evaluation Set) | $0.18 [^9] | [Solution by PoohAI](https://drive.google.com/file/d/1kTom9M54LVfLbPDQHpGgfUs3y1IYIpy2/view) | [Kaggle](https://www.kaggle.com/code/gregkamradt/arc-prize-2024-8th-place-solution) | Various approaches from the 2020 competition were ensembled. Post-processing filters are used to remove bad attempts from the ensemble of solutions. |
| Greenblatt | 43% (semi-private); 42% (public eval) | $20 [^10] | [Getting 50% (SoTA) on ARC-AGI with GPT-4o](https://redwoodresearch.substack.com/p/getting-50-sota-on-arc-agi-with-gpt) | [Kaggle](https://www.kaggle.com/code/rgreenblatt/rg-basic-ported-submission) | Uses GPT-4o generate a large number of Python implementations (around 5,000) for each task. GPT-4o is then asked to revise the code to make it correct, based on what a subset of the most promising programs actually produces. A further ~3,000 programs are then generated to attempt to fix the original programs. |
| OpenAI o3 (high-efficiency) | 75.7% (semi-private) 82.6% (public eval) | $20 (semi-private); $17 (public) [^11]  | Not available yet | [OpenAI o3 Breakthrough High Score on ARC-AGI-Pub](https://arcprize.org/blog/oai-o3-pub-breakthrough) | Uses OpenAI's o3 model. Prompting details are not (yet) known. |
| OpenAI o3 (low-efficiency) | 87.5% (semi-private) 91.5%	(public eval) | $3440 (semi-private); $2924 (public) [^12]  | Not available yet | [OpenAI o3 Breakthrough High Score on ARC-AGI-Pub](https://arcprize.org/blog/oai-o3-pub-breakthrough) | Uses OpenAI's o3 model. Prompting details are not (yet) known. |
| Wind (icecuber) | 20.6% (private) | $0.03 [^13] | [2020 1st Place Solution Documentation](https://github.com/top-quarks/ARC-solution/blob/master/ARC-solution_documentation.pdf)  | [Github](https://github.com/top-quarks/ARC-solution); [Kaggle](https://www.kaggle.com/code/icecuber/arc-1st-place-solution) | Uses brute force program search and a hand-crafted DSL of grid transformation operations. Uses C++, for speed. |
| Fletcher-Hill | 41% (public eval subset) | Unknown | [Mini-ARC: Solving Abstraction and Reasoning Puzzles with Small Transformer Models](https://arxiv.org/abs/2412.04604) | [pfletcherhill/mini-arc](https://github.com/pfletcherhill/mini-arc) | Uses a transformer model with an embedding layer to convert discrete colours to vectors, a and custom positional encoding scheme that represents a cell’s 2-D position as well as it’s position in the larger context. The model has ~67 million parameters, and is (currently) limited to a maximum grid size of 12x12. The model was trained on a dataset of ~830,000 puzzles from various sources. Test-time training was employed by sampling input-output pairs from the examples to make "new" puzzles. |

| Author(s) | Score | Estimated Cost Per Task | Paper | Code | Description |
|---|---|---|---|---|---|





| Ouellette | Not Listed | Not Listed | [Towards Efficient Neurally-Guided Program Induction for ARC-AGI](https://arxiv.org/abs/2411.17708) | [SimonOuellette35/GridCoder2024](https://github.com/SimonOuellette35/GridCoder2024) | Explores efficient neurally-guided program induction for ARC-AGI. |

[^1]: The solution achieves up to 26% accuracy on constant-sized tasks on the public eval set. Performance on the private eval set is unknown. 
[^2]: According to the paper, 100 tasks takes around 2 hours to run on Kaggle. Assuming 1xP100 at ~$1.50 per hour (specific GPU is not known).
[^3]: Assuming maximum budget used for semi-private leaderboard (500 tasks for $10,000).
[^4]: The paper states that "Our flagship model is too expensive to run on the private test set hosted by Kaggle", so this must exceed ~$0.18 per task (12 hours x $1.50 for a P100 GPU, for 100 tasks).
[^5]: Based on paper's stated runtime of "12 hours/100 tasks runtime on an A100 GPU for Llama 8B", and A100 GPU cost of $3.67 per hour.
[^6]: Assuming maximum runtime of 12 hours for private leaderboard with 2xT4 GPUs at $0.70 per hour.
[^7]: Assuming maximum runtime of 12 hours for private leaderboard with 1xP100 GPU at $1.50 per hour (specific GPU is not known).
[^8]: Assuming maximum runtime of 12 hours for private leaderboard with 1xP100 GPU at $1.50 per hour (specific GPU is not known).
[^9]: Assuming maximum runtime of 12 hours for private leaderboard with 1xP100 GPU at $1.50 per hour (specific GPU is not known).
[^10]: Assuming maximum budget used for semi-private leaderboard (500 tasks for $10,000).
[^11]: Based on figures on https://arcprize.org/blog/oai-o3-pub-breakthrough
[^12]: Based on figures on https://arcprize.org/blog/oai-o3-pub-breakthrough and the statement that the high compute version used compute that was "roughly 172x the low-compute configuration" (this assumes that costs of compute grows linearly).
[^13]: Based on 9 hours runtime on CPU with specs from https://www.kaggle.com/docs/notebooks). Estimated CPU cost is $0.32 per hour.

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

