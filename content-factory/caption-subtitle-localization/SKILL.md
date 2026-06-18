---
name: caption-subtitle-localization
description: Create captions, subtitles, SRT/VTT files, burned-in subtitle text, localized variants, bilingual social captions, and translation notes for shortform video and social posts. Use when Codex needs to subtitle, translate, adapt, or localize content for Telegram, Instagram, TikTok, Reels, and multilingual audiences.
---

# Caption Subtitle Localization

## Purpose

Use this skill to make spoken or written content readable, accessible, and natural in another language or platform context. Localize meaning, not just words.

## Workflow

1. Identify the output:
   - Social caption.
   - Burned-in subtitle lines.
   - SRT or VTT file.
   - Bilingual post.
   - Localized script.
   - Hook variants in another language.

2. Preserve the source:
   - Keep claims, names, numbers, and dates accurate.
   - Do not add promises or proof that the source did not contain.
   - Mark unclear audio, missing timestamps, or ambiguous terms.

3. Localize:
   - Use natural phrasing for the target audience.
   - Keep jokes, idioms, and slang only when they still land.
   - Adapt CTA wording to platform behavior and language norms.
   - Keep subtitles short enough to read on mobile.

## Subtitle Formatting

For SRT/VTT requests, output valid blocks with timestamps if timestamps are supplied. If timestamps are absent, provide clean subtitle text segmented by spoken beats and note that timing is needed before final export.

For burned-in captions, provide:

`beat | subtitle text | emphasis word | safe-zone note`

## Quality Rules

- Avoid literal translation when it sounds stiff.
- Avoid over-localizing technical terms that the audience expects in English.
- Keep line breaks readable.
- Use `$brand-voice-keeper` when the brand has a defined voice.
- Use `$social-publishing-qa` before multilingual publication.
