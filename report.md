# nanochat training report

Generated: 2026-03-19 16:18:45

## Environment

### Git Information
- Branch: master
- Commit: 5019acc (clean)
- Message: fix scaling laws scripts after the bigram embeddings were removed

### Hardware
- Platform: Linux
- CPUs: 80 cores (160 logical)
- Memory: 1763.8 GB
- GPUs: 8x NVIDIA B200
- GPU Memory: 1426.8 GB total
- CUDA Version: 12.8
- Hourly Rate: $16.00/hour

### Software
- Python: 3.10.20
- PyTorch: 2.9.1+cu128


### Bloat
- Characters: 533,791
- Lines: 11,738
- Files: 47
- Tokens (approx): 133,447
- Dependencies (uv.lock lines): 3,618

Run started: 2026-03-19 16:18:45

---

## Tokenizer training
timestamp: 2026-03-19 16:20:17

- max_chars: 2,000,000,000
- doc_cap: 10,000
- vocab_size: 32,768
- train_time: 61.2350
- num_special_tokens: 9
- token_bytes_min: 1
- token_bytes_max: 32
- token_bytes_mean: 6.5821
- token_bytes_std: 2.8129


## Tokenizer evaluation
timestamp: 2026-03-19 16:20:28

### Comparison with GPT-2

| Text Type | Bytes | GPT-2 Tokens | GPT-2 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 404 | 4.50 | 405 | 4.49 | -0.2% |
| korean | 893 | 745 | 1.20 | 741 | 1.21 | +0.5% |
| code | 1259 | 576 | 2.19 | 396 | 3.18 | +31.2% |
| math | 1834 | 936 | 1.96 | 911 | 2.01 | +2.7% |
| science | 1112 | 260 | 4.28 | 247 | 4.50 | +5.0% |
| fwe-train | 2948778 | 631304 | 4.67 | 622511 | 4.74 | +1.4% |
| fwe-val | 3024593 | 653067 | 4.63 | 644939 | 4.69 | +1.2% |

### Comparison with GPT-4

| Text Type | Bytes | GPT-4 Tokens | GPT-4 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 387 | 4.70 | 405 | 4.49 | -4.7% |
| korean | 893 | 364 | 2.45 | 741 | 1.21 | -103.6% |
| code | 1259 | 309 | 4.07 | 396 | 3.18 | -28.2% |
| math | 1834 | 832 | 2.20 | 911 | 2.01 | -9.5% |
| science | 1112 | 249 | 4.47 | 247 | 4.50 | +0.8% |
| fwe-train | 2948778 | 611619 | 4.82 | 622511 | 4.74 | -1.8% |
| fwe-val | 3024593 | 631183 | 4.79 | 644939 | 4.69 | -2.2% |


## Base model training
timestamp: 2026-03-19 18:41:04

- run: dummy
- device_type: 
- fp8: True
- fp8_recipe: tensorwise
- depth: 24
- aspect_ratio: 64
- head_dim: 128
- max_seq_len: 2048
- window_pattern: SSSL
- num_iterations: -1
- target_flops: -1.0000
- target_param_data_ratio: 8.0000
- device_batch_size: 16
- total_batch_size: -1
- embedding_lr: 0.3000
- unembedding_lr: 0.0080
- weight_decay: 0.2800
- matrix_lr: 0.0200
- scalar_lr: 0.5000
- warmup_steps: 40
- warmdown_ratio: 0.6500
- final_lr_frac: 0.0500
- resume_from_step: -1
- eval_every: 250
- eval_tokens: 41,943,040
- core_metric_every: 2000
- core_metric_max_per_task: 500
- sample_every: 2000
- save_every: -1
- model_tag: None
- Number of parameters: 1,384,122,122
- Number of FLOPs per token: 4.775225e+09
- Calculated number of iterations: 5568
- Number of training tokens: 5,838,471,168
- Tokens : Scaling params ratio: 8.0000
- DDP world size: 8
- warmup_steps: 40
- warmdown_ratio: 0.6500
- final_lr_frac: 0.0500
- Minimum validation bpb: 0.7180
- Final validation bpb: 0.7180
- CORE metric estimate: 0.2714
- MFU %: 20.07%
- Total training flops: 2.788002e+19
- Total training time: 128.37m
- Peak memory usage: 52705.69MiB


## Base model evaluation
timestamp: 2026-03-19 18:46:17

- model: base_model (step 5568)
- CORE metric: 0.2621
- train bpb: 0.7173
- val bpb: 0.7154
- hellaswag_zeroshot: 0.3993
- jeopardy: 0.0827
- bigbench_qa_wikidata: 0.4536
- arc_easy: 0.5746
- arc_challenge: 0.1763
- copa: 0.2600
- commonsense_qa: 0.0561
- piqa: 0.4897
- openbook_qa: 0.2347
- lambada_openai: 0.4427
- hellaswag: 0.4086
- winograd: 0.3187
- winogrande: 0.1460
- bigbench_dyck_languages: 0.1470
- agi_eval_lsat_ar: 0.1087
- bigbench_cs_algorithms: 0.4424
- bigbench_operators: 0.1714
- bigbench_repeat_copy_logic: 0.0625
- squad: 0.3865
- coqa: 0.3150
- boolq: -0.0856
- bigbench_language_identification: 0.1745
- sample 0: <|bos|>The capital of France is Paris. It is the largest city in France and the second largest city in Europe
- sample 1: <|bos|>The chemical symbol of gold is Au. It is a soft, malleable, and ductile metal. It
- sample 2: <|bos|>If yesterday was Friday, then tomorrow will be Saturday. If yesterday was Monday, then tomorrow will be Sunday. If yesterday was
- sample 3: <|bos|>The opposite of hot is cold. The opposite of cold is hot. The opposite of hot is cold.
- sample 4: <|bos|>The planets of the solar system are: Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, Ne
- sample 5: <|bos|>My favorite color is blue. I love the color blue. I love the color blue. I love
- sample 6: <|bos|>If 5*x + 3 = 13, then x is a multiple of 5. If 5*x + 3 = 
- unconditioned 0: <|bos|>JRP450 - Mrs.Arthuranglo
Economics Assignment #3 Due 3-09-2010.
1.) Shopping Superstores
2.) Middle Class Economies:
aWhen goods are produced in a number of factories, it increases the speed of production and lowers the price but it leads to a higher level of work supply. The country's economy in this case is not improving but it is.
b.If a country economy is delivering more goods of a particular good at a reasonable price, than it means that mean number of workers involved in the production is higher so the market economy is not good but
- unconditioned 1: <|bos|>Add Incentives: Running Fanatics offers a range of incentives to encourage members to share their work and build a loyal fan base. These incentives may include exclusive access to early access to new regions, limited-time prize packs, and special content rewards.
Maximize Engagement: Encourage interaction and feedback by creating a dedicated fan page or community on Running Fanatics. Promote announcements such as shareable videos, exclusive content previews, and personalized messages for members to interact with each other. This will help create a vibrant community of fanatics who love running and support fellow fans.
Inject Fun Elements: Make running fanatics feel like guests at
- unconditioned 2: <|bos|>They say learning is the act of filling your brain with information about the environment around you. You need to recognize, associate with and remember what is happening in a given situation and how to adapt your behaviors to fit in it. It should prepare you to handle life in the workplace and be able to find your way around after leaving that place. Here is the story of one recruited worker whose relationship with the company was beyond satisfactory because of the lack of skills he brought to the table.

Connect with a Veterinarian

Mission: It happened half a year ago. You work as a GPS for the accounting standard for the construction company. You
- unconditioned 3: <|bos|>Testimonials
Here are some snapshots of valuable benefits.
Chris Paton
Berkshire
Below are some of the testimonials from our clients
Sensory Support Services run by Elaine Boyle, an Occupational Therapist with an eye towards helping people to learn to use their senses again to really thrive so that they can do what they love doing and this provides enjoyment wherever they are, whether that be at home, at work, or in any other setting. Telehealth is also greatly helpful for us being able to offer treatment when clients are not in the same household because we are allowing for everyone involved to continue living their normal lives at
- unconditioned 4: <|bos|>Explain the difference between safe and unsafe electricity
Electricity safety lesson electrical systems safe and unsafe means there's an electrical system in the home that's safe for humans, but unsafe. Explain the difference between safe and unsafe electricity: any material is an electrical some time ago, when people had to stay away from electricity and. Understanding electrical safety standard sg 11-705 governs the mandatory minimum systems safe electricity portable appliance wash and dry ramps. Difference between work and unsafe wet work the need for your safety electricians constantly need to get new machines going. Pdf the purpose of understanding arrangement is to provide all staff members as well as
- unconditioned 5: <|bos|>What is PRI1W. Great household blender to make healthy smoothies, shakes and soup! The PRI1W can crush up cabbage and green beans, make gorgeous cocktails, harmonize tossed salads and make creamy soups.Upgrade your blender, it feels an upgrade.Crew larger power drill *not included...Made in China.
- unconditioned 6: <|bos|>How To Protect Your Eyes from Harmful Light

Today, up to 80% of the population will experience visual problems because they spend more than 9 hours a day looking at a computer screen or watching television. With the transition of computers to tablets and Chromebooks, people are spending even more time looking at what they call 'phonebooks': the combination of tablets and laptops.

It is estimated that half of the people nowadays spend more than 4.5 hours a day using a computer at work or at home.

But all of us, educated or not, neglect to take the fact of long computer in our eyes. That is why
- unconditioned 7: <|bos|>Carbon tax takes aim at carbon in Dubai
A Carbon tax that would take a cue from countries in South America before the line into vested street taxing countries, including Colombia and the U.S. has been proposed by Energy and Environment Minister Abdul Hamid bin Khalifa.
The tax, to be imposed on carbon and other emissions would be phased in over a four year period. Dubai is paving the way for this in a similar approach to the car tax in other countries, said Bin Khalifa.
U.S. Department of Energy spokesperson Heidi Storch said:
The good news is that there


## Chat evaluation sft
timestamp: 2026-03-19 19:10:44

- source: sft
- task_name: None
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- device_type: 
- ARC-Easy: 0.6263
- ARC-Challenge: 0.4881
- MMLU: 0.3724
- GSM8K: 0.0735
- HumanEval: 0.1280
- SpellingBee: 0.9961
- ChatCORE metric: 0.3633


## Summary

- Characters: 533,791
- Lines: 11,738
- Files: 47
- Tokens (approx): 133,447
- Dependencies (uv.lock lines): 3,618

| Metric          | BASE     | SFT      | RL       |
|-----------------|----------|----------|----------|
| CORE            | 0.2621   | -        | -        |
| ARC-Challenge   | -        | 0.4881   | -        |
| ARC-Easy        | -        | 0.6263   | -        |
| GSM8K           | -        | 0.0735   | -        |
| HumanEval       | -        | 0.1280   | -        |
| MMLU            | -        | 0.3724   | -        |
| ChatCORE        | -        | 0.3633   | -        |

Total wall clock time: 2h51m
