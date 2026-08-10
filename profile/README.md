<h1 align="center">Hopit AI</h1>
<p align="center"><b>The intelligence layer fashion commerce runs on.</b></p>
<p align="center">
  <a href="https://hopit.ai">hopit.ai</a> ·
  <a href="https://hopit-ai.github.io/Moda/">Benchmarks</a> ·
  <a href="https://huggingface.co/HopitAI">Models</a> ·
  <a href="https://hopitai.substack.com/">Research</a>
</p>

---

We build fashion-native retrieval and trend intelligence — and we measure it in
public. Every number below is **full corpus, one harness, competitors included,
losses shown**.

### Models

| Model | Task | Size | Availability |
|---|---|---|---|
| [**MODA**](https://huggingface.co/HopitAI/moda-fashionsiglip-multiview-203m) | text → product | 203M | open source + open weights |
| [**MODA Pro Lite**](https://huggingface.co/HopitAI/moda-pro-lite) | text → product | 213M | open weights |
| **MODA Pro** | text → product | — | closed · [hosted](https://hopit.ai) |
| [**MODA-SigLIP-Distilled**](https://huggingface.co/HopitAI/moda-fashion-distilled) | image → product | 203M | open weights |
| [**Matryoshka**](https://huggingface.co/HopitAI/moda-fashion-matryoshka) · [**512d**](https://huggingface.co/HopitAI/moda-fashion-distilled-512d) · [**FP16 vision**](https://huggingface.co/HopitAI/moda-fashion-vision-fp16) | image → product | 203M / 93M | open weights |

**Where they stand.** MODA-SigLIP-Distilled is the top open model on
[LookBench](https://serendipityoneinc.github.io/look-bench-page/) image
retrieval, above a 1.24B-parameter model. MODA Pro is rank 1 or 2 on 9 of 10
text-to-image benchmark cells across three venues — the only system in our
comparison without a bad benchmark. MODA Pro Lite beats MODA on catalog search
(KAGL +10.2%, Polyvore +7.3%) as a plain bi-encoder, no serving recipe.

Full tables, including every cell we lose:
**[hopit-ai.github.io/Moda](https://hopit-ai.github.io/Moda/)**

### Repositories

- **[Moda](https://github.com/hopit-ai/Moda)** — the open benchmark and model
  family: harness, evaluation code, and the write-ups, including the
  experiments that failed.
- **[india-trade-cli](https://github.com/hopit-ai/india-trade-cli)** — agentic
  research over Indian equities. Different domain, same conviction: publish the
  method, measure the result.

### How we work

- **Full corpus only.** No subsampled galleries; screening runs are never mixed
  with full-corpus rows.
- **One harness.** Ours and competitors' models run identical preprocessing and
  protocol — we reproduce published baselines before comparing against them.
- **Losses shown.** Every model card links the benchmarks it loses.
- **Negative results published.** Three training approaches failed before the
  fourth worked; all three are written up.

<p align="center"><sub>Made with ♥ in NYC and India</sub></p>
