# Bài 24: AI Content Provenance — Watermarking & C2PA

## Current State (Mid-2026)

**OpenAI (May 19, 2026):**
- Every image carries **2 invisible signals**: C2PA + SynthID
- Survives screenshots, compression, format changes
- Free public verification tool available

**Google:**
- C2PA support in Chrome (rolling out)
- Image checks in Lens, AI Mode, Circle to Search
- Pixel 10: first smartphone with native C2PA on camera capture

## Technology Stack

| Tech | What It Does |
|------|-------------|
| **C2PA** | Cryptographic provenance metadata — signed manifest |
| **SynthID** (Google) | Invisible watermark via logits perturbation |
| **Detection tools** | Hive (~94%), Illuminarty (~91%) accuracy |

## EU Requirement

- AI Act: Watermarking obligations deadline **December 2, 2026**
- Code of Practice (March 2026): Single technique **not sufficient**
- Must combine: C2PA + imperceptible watermarking
- Must survive: cropping, compression, screenshotting

## Limitations

- C2PA and watermarking are **technically independent**
- Can create "authenticated contradictions"
- **85-94%** detection accuracy = 6-15% miss rate

## SynthID for Text

- Subtly perturbs token probabilities during generation
- Encodes watermark **without model retraining**
- Can detect AI text without seeing original prompt

## References

- [OpenAI: Advancing Content Provenance](https://openai.com/index/advancing-content-provenance/)
- [Google: C2PA Expansion in Chrome](https://tpiros.dev/blog/c2pa-content-credentials-google-expansion)
- [OpenAI + Google SynthID Partnership](https://cryptobriefing.com/openai-synthid-watermarking-ai-detection/)
- [Arxiv: Why C2PA Falls Short](https://arxiv.org/html/2604.24890v1)
