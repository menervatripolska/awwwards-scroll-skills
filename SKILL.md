---
name: brand-voice-keeper
description: Define, preserve, and apply a consistent brand voice across Telegram, Instagram, TikTok, Reels, carousels, captions, scripts, launch posts, and content calendars. Use when Codex needs to infer voice from samples, rewrite content in a brand style, create voice rules, or keep multi-platform content from sounding generic.
---

# Brand Voice Keeper

## Purpose

Use this skill to keep content recognizable across platforms while still adapting format and pacing. The goal is consistency without flattening everything into the same copy.

## Voice Fingerprint

When samples are available, extract:

- Energy: calm, sharp, playful, luxurious, academic, rebellious, warm.
- Sentence rhythm: short, flowing, direct, narrative, clipped.
- Proof style: data, case, craft, founder opinion, client words, visual proof.
- Vocabulary: signature phrases, preferred terms, banned terms.
- Humor: none, dry, meme-native, elegant, sarcastic, friendly.
- Authority posture: teacher, insider, challenger, curator, operator, host.
- CTA style: soft invite, direct command, question, DM prompt, application.

If no samples exist, create a provisional voice guide and label it as such.

## Rewrite Workflow

1. Preserve the strategic job of the content.
2. Remove generic filler and mismatched platform language.
3. Apply the voice fingerprint.
4. Keep claims factual and sourced.
5. Adapt pacing per platform:
   - Telegram: fuller thought and trust.
   - Instagram: visual packaging and save/share clarity.
   - TikTok: spoken rhythm and immediate tension.

## Output Format

Provide:

`voice diagnosis | rewrite | what changed | words to keep | words to avoid`

For teams, create:

`voice rule | do | avoid | example`

## Rules

- Do not make every brand sound premium, bold, disruptive, or inspirational by default.
- Keep multilingual tone natural; do not translate catchphrases literally when they sound stiff.
- Use `$social-publishing-qa` if brand voice changes could create factual, legal, or reputational risk.
