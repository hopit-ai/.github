<h1 align="center">Hopit AI</h1>
<p align="center"><b>The intelligence layer fashion commerce runs on.</b></p>
<p align="center">
  <a href="https://hopit.ai">hopit.ai</a> ·
  <a href="https://hopit-ai.github.io/Moda/">Retrieval benchmarks</a> ·
  <a href="https://hopit-ai.github.io/Moda_ner/">Attribute benchmarks</a> ·
  <a href="https://huggingface.co/HopitAI">Models</a> ·
  <a href="https://hopitai.substack.com/">Research</a>
</p>

---

We build fashion-native retrieval, attribute extraction and trend intelligence — and
we measure it in public. Every number below is **full corpus, one harness, competitors included,
losses shown**.

### Retrieval: which product did they mean?

| Model | Task | Size | Availability |
|---|---|---|---|
| [**MODA**](https://huggingface.co/HopitAI/moda-fashionsiglip-multiview-203m) | text → product | 203M | open source + open weights |
| [**MODA Pro Lite+**](https://huggingface.co/HopitAI/moda-pro-lite-plus) | text → product | 213M | open weights + recipe |
| [**MODA Duo**](https://huggingface.co/HopitAI/moda-duo) | text → product | routes two encoders | open recipe |
| [**MODA Pro Lite**](https://huggingface.co/HopitAI/moda-pro-lite) | text → product | 213M | open weights |
| **MODA Pro** | text → product | — | closed · [hosted](https://hopit.ai) |
| [**MODA-SigLIP-Distilled**](https://huggingface.co/HopitAI/moda-fashion-distilled) | image → product | 203M | open weights |
| [**Matryoshka**](https://huggingface.co/HopitAI/moda-fashion-matryoshka) · [**512d**](https://huggingface.co/HopitAI/moda-fashion-distilled-512d) · [**FP16 vision**](https://huggingface.co/HopitAI/moda-fashion-vision-fp16) | image → product | 203M / 93M | open weights |

**Where they stand.** MODA-SigLIP-Distilled is the top open model on
[LookBench](https://serendipityoneinc.github.io/look-bench-page/) image
retrieval, above a 1.24B-parameter model. On text-to-image, **MODA Pro Lite+**
leads every model at ≤250M parameters on catalogue search (KAGL +10.9%, Polyvore
+8.7% over MODA), and **MODA Duo** routes each query to whichever open model
suits its shape, beating both on mixed traffic. Our hosted MODA Pro is rank 1 or
2 on five of six full-corpus benchmarks — an 878M model beats us on four of them,
and that is in the tables too.

Every cell is MAP@10 at full corpus under one evaluator (`pytrec_eval
map_cut.10`), competitors included.

Full tables, including every cell we lose:
**[hopit-ai.github.io/Moda](https://hopit-ai.github.io/Moda/)**

### Attribute extraction: what is this garment?

Turning a fashion image into structured product data. Four frozen tracks, never
averaged, because a model can be strong on clean product shots and weak on
full-body photos.

| Model | Input | Size | Availability |
|---|---|---|---|
| [**MODA_NER(V) Crop**](https://huggingface.co/HopitAI/moda-ner-v-crop) | cropped garment | 203M | open weights (MIT) + open code |
| [**MODA_NER(V) Catalog**](https://huggingface.co/HopitAI/moda-ner-v-catalog) | catalogue product image | linear heads | open weights (CC BY-NC 4.0) |
| [**MODA_NER(V) Full-body**](https://huggingface.co/HopitAI/moda-ner-v-fullbody) | full-body photo | 203M | open weights (CC BY-NC 4.0) |
| **MODA_NER(T)** | product title or description | 150M | benchmark published, weights held |
| **MODA_NER Pro** | declared schema | routes four schemas | closed · [hosted](https://hopit.ai) |

**Where they stand.** Two wins and two ties against the comparators, no losses.
On `catalog`, 0.8292 against 0.6657 for FashionCLIP 2.0 with matched supervised
heads. On `fullbody`, 0.6917 against 0.5943, and the applicability decision —
knowing an attribute is not visible rather than inventing it — is scored
separately at 0.6637. Field by field that is all 10 catalogue attributes and 17
of 18 on full-body, 31% and 19% better on average. Do not read across those
rows: different images, different fields, different metrics.

Two of the tracks are evaluated against research-only corpora whose terms reach
derived data, so those weights are non-commercial. That binds us too: they are
not part of our paid product.

MODA_NER Pro is the hosted tier: the same extraction, trained on your catalogue
and mapped to your taxonomy rather than the benchmarks'.

Full tables, protocol and prediction files:
**[hopit-ai.github.io/Moda_ner](https://hopit-ai.github.io/Moda_ner/)**

### Repositories

- **[Moda](https://github.com/hopit-ai/Moda)** — the open benchmark and model
  family: harness, evaluation code, and the write-ups, including the
  experiments that failed.
- **[Moda_ner](https://github.com/hopit-ai/Moda_ner)** — the attribute
  extraction suite: four track scorers, the manifest builders that recreate the
  frozen splits, prediction files with their hashes, and the published weights.
- **[india-trade-cli](https://github.com/hopit-ai/india-trade-cli)** — agentic
  research over Indian equities. Different domain, same conviction: publish the
  method, measure the result.

### How we work

- **Tracks are never averaged.** A weak result on one track cannot be absorbed
  by a strong result on another.
- **Full corpus only.** No subsampled galleries; screening runs are never mixed
  with full-corpus rows.
- **One harness.** Ours and competitors' models run identical preprocessing and
  protocol — we reproduce published baselines before comparing against them.
- **Losses shown.** Every model card links the benchmarks it loses.
- **Negative results published.** Three training approaches failed before the
  fourth worked; all three are written up.

<p align="center"><sub>Made with ♥ in NYC and India</sub></p>
