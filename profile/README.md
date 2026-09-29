<h1 align="center">Hopit</h1>
<p align="center"><b>AI that gets better at its job by doing it.</b></p>
<p align="center">
  <a href="https://hopit.ai">hopit.ai</a> ·
  <a href="https://huggingface.co/HopitAI">Models</a> ·
  <a href="https://hopit-ai.github.io/">Benchmarks</a> ·
  <a href="https://hopitai.substack.com/">Research notes</a>
</p>

---

Hopit is a continual-learning lab built in Asia-Pacific. We build models and
harnesses that learn new tasks, keep what they already know, and improve inside
the enterprises that use them.

### Decision models

Small models that answer a typed decision question in one forward pass, with a
calibrated probability for each option.

| Model | What it is | Where it stands |
|---|---|---|
| [**Hopper**](https://huggingface.co/HopitAI/hopper) | 4B decision model, LoRA on Qwen3.5-4B | #2 in JevBench's Jev-class capability ranking¹ |
| [**Hopper (G)**](https://huggingface.co/HopitAI/hopper-g) | General-purpose version, 4.66B served | Top five of 46 under 5B on the Jev Decision Index² |

Released for research and demonstration only; see each model card for its licence
and training data.

### Continual learning

Our update method lifted an internal tool-use evaluation from 57.9% to 66.1%
without losing earlier abilities on the retention suites we track. One seed and an
internal measurement — we will publish the protocol and artifacts before treating
it as established.

### Track record

Before continual learning, we built open models and public benchmark suites for
fashion retrieval and attribute extraction, and held ourselves to them in public.
They remain the standard our newer work has to clear.

### Repositories

- **[hopper](https://github.com/hopit-ai/hopper)** — the decision server behind
  Hopper and Hopper (G).
- **[Moda](https://github.com/hopit-ai/Moda)** — open retrieval models and their
  benchmark: harness, evaluation code, and the experiments that failed.
- **[Moda_ner](https://github.com/hopit-ai/Moda_ner)** — an open attribute-extraction
  suite: four frozen tracks, scorers, prediction files and their hashes.
- **[india-trade-cli](https://github.com/hopit-ai/india-trade-cli)** — agentic
  research over Indian equities. Different domain, same conviction: publish the
  method, measure the result.

### How we work

- **Every rank is quoted with its qualifier.** A leaderboard position without its
  scope is a claim nobody can check.
- **Frozen before inference.** Protocols are fixed and predictions hashed before
  labels open; scorers fail closed.
- **Losses shown.** The runs we lose are published beside the runs we win.

### Work with us

We deploy with a small forward-deployed team inside your environment. Your data
and your deployed models stay yours. The approach is ideal for regulated
enterprises. → **[hopit.ai](https://hopit.ai)**

<sub>¹ JevBench v1.4.2, 24 September 2026 snapshot, scored by an independent
maintainer. Second on capability; fifth on the composite score, which also weighs
speed and cost. ² Jev Decision Index 0.2.1, 28 September 2026: Hopper (G) 1.2 is
third of 46 systems under 5B on the chance-corrected headline score (40.77), within
0.1 of fourth, and 18th of 70 overall. The edition is 76% scored.</sub>

<p align="center"><sub>Built in Asia-Pacific</sub></p>
