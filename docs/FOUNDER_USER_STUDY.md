# Founder User Study

> Date: 2026-09-16  
> Purpose: use the founder as User #1 to generate hypotheses and observe a media-first Japanese learning profile before external validation.

## Why this study exists

The product idea originated from a real learning pattern: substantial exposure to J-POP/anime and conversational Japanese sounds, but much weaker script decoding—especially katakana/kanji—and uneven formal grammar knowledge.

This creates a useful first-party dataset for early discovery. It is valuable for **hypothesis generation, prototype shaping, and longitudinal observation**, but it is **not a substitute for external user research or usability testing** because the founder already knows the product intent and is unusually invested in the solution.

## Recommended research framing

Use this as a combination of:

- **Autoethnographic observation** — record real learning moments from daily J-content use.
- **Diary study** — log what was encountered, what was understood by sound, what could/could not be read, and how it was resolved.
- **Think-aloud diagnostic tasks** — verbalize how a phrase is inferred while reading/listening.
- **Repeated skill snapshots** — periodically test hiragana, katakana, kanji, grammar, phrase comprehension, and sound-to-script mapping.

Avoid calling this the project's final “user test.” It is better labeled **Founder/User #1 Study** or **Pilot Study**.

## Initial observations

### 1. Uneven skill profile

Current diagnostic tasks suggest a non-linear proficiency profile:

- hiragana decoding: partially functional
- katakana decoding: very weak
- kanji: limited and often inferred through Korean/known vocabulary
- grammar intuition: stronger than script literacy
- sentence-level meaning inference: stronger than isolated character recognition
- media/conversational phrases: frequently recognized from repeated exposure
- sound-to-script mapping: inconsistent

The learner may therefore know expressions above a beginner textbook sequence while still missing basic script knowledge.

### 2. Whole-word recognition can bypass character decoding

Example behavior:

- `カメラ` was not decoded successfully as katakana.
- `カーテンコール` was recognized as “Curtain Call” because the phrase was already familiar from context/exposure.

This suggests that lexical familiarity and context can allow recognition even when character-level decoding is weak.

### 3. Reading aloud and understanding are separate links

Example:

- `かいました` could be read aloud as *kaimashita*, but its meaning was confused with “went.”

This indicates that successful script → sound conversion does not necessarily imply sound → meaning mapping.

### 4. Context helps reconstruct partial meaning

In short N5-style passages, unknown words/scripts did not always prevent understanding of the overall event structure. Known particles, familiar verbs, and contextual clues were used to reconstruct meaning.

## Data model for future sessions

For every encountered phrase, record:

| Field | Example |
|---|---|
| Source/context | J-POP title / anime dialogue / real conversation |
| Raw remembered sound | 카와라나이 모노 |
| Can recognize meaning by sound? | Yes / partial / no |
| Can read original script? | full / partial / no |
| Can identify each character? | full / partial / no |
| Can reproduce script from sound? | full / partial / no |
| Can explain grammar/word structure? | full / partial / no |
| Current workaround | search / subtitles / translator / ask AI / ignore |
| Time/steps to resolve | estimate |
| Saved for later? | yes/no |
| Recall after 1 day / 1 week | correct / partial / failed |

## Suggested pilot protocol

1. Collect 20–30 real expressions encountered naturally over 1–2 weeks.
2. For each expression, capture the fields above before looking up the answer.
3. Group errors by broken link:
   - sound → script
   - script → sound
   - sound → meaning
   - script → meaning
   - grammar/context disambiguation
4. Prototype one learning flow that repairs the most frequent broken link.
5. Re-test the same expressions after 1 day and 1 week.
6. Use findings to create hypotheses for external interviews and usability tests.

## Research limitation

Because the founder is also the designer and understands the product concept, results are vulnerable to:

- confirmation bias
- solution bias
- familiarity with intended flows
- atypical motivation and domain interest

Therefore external Korean media-first Japanese learners are still required before finalizing the problem definition or product scope.

## Current hypothesis

The strongest early opportunity may be to diagnose **which connection is missing**, rather than assigning one linear proficiency level.

Potential product framing:

> You do not necessarily need to relearn all of beginner Japanese. The product identifies which links between sound, script, meaning, and recall are weak, then uses expressions you already care about to repair those links.
