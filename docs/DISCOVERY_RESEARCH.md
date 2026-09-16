# Discovery Research — Japanese Sound to Script

> Date: 2026-09-16  
> Stage: Research & Discovery (Steps 2–4)  
> Status: Secondary research complete / Primary interviews pending

## 0. Starting hypothesis

The initial product hypothesis came from a specific learning pattern:

- A learner has heard Japanese for years through J-POP, anime, dramas, travel, etc.
- They recognize the sound and often understand the rough meaning.
- Hiragana may be readable, but kanji/katakana and exact written forms lag behind listening familiarity.
- Example: `카와라나이 모노` is familiar by sound, but `変わらないもの` is not immediately recognized.
- Homophones/conjugated forms such as `いった` can be heard but are hard to map to `言った` / `行った` without context.

Initial learning-loop hypothesis:

`Sound → Script → Meaning → Recall`

This research tests whether the problem exists beyond one person, how current products solve adjacent problems, and where a defensible product opportunity may remain.

---

## 1. Market signals

### Japanese learning demand

The Japan Foundation's 2024 Survey on Japanese-Language Education Abroad counted **555,396 learners in Korea**, third globally after China and Indonesia. This was an increase of 85,062 learners (+18.1%) from 2021. The survey covers institution-based Japanese education and therefore does not represent the entire self-study market.

Duolingo's 2025 Language Report placed **Japanese #4 globally** among languages studied on the platform, overtaking German. English remained #1 globally.

These figures do not provide a direct TAM for this product, but they do show that Japanese is a large and active language-learning category and that Korea is a particularly strong Japanese-learning market.

### Media-driven learning is a real behavior

The Japan Foundation itself operates Japanese courses built around anime/manga and explicitly describes pop culture as a motivation for learning Japanese. Its B1/B2 Black Jack course uses an unaltered manga chapter, vocabulary/expression support, comprehension checks, output activities, and review.

A previous Japan Foundation report on Korea also noted that institution counts understate people who learn Japanese through other methods, including media-based self-study.

### Global language-learning direction

Large/general language platforms increasingly compete on:

- AI conversation and feedback
- personalized lessons
- real/native content
- learning from users' interests
- review generated from mistakes
- moving from passive knowledge into active use

Examples include Speak, Memrise, Busuu, LingQ, Migaku and others.

---

## 2. Japanese competitor landscape

### A. Search / dictionary

#### NAVER Japanese Dictionary

Already supports:

- direct Japanese input
- **Hangul pronunciation input** (`아리가토 → ありがとう`)
- romaji input
- handwriting input

**Finding:** Hangul phonetic lookup is not a novel feature by itself.

#### 난데스까? — 발음으로 찾는 일본어 사전

A Korean iPhone app launched in August 2026. It supports:

- Korean phonetic text/voice lookup
- fuzzy pronunciation recommendations
- Korean-meaning search
- 23,000+ listed words at launch
- examples/audio on part of the vocabulary set
- kanji information
- saving words
- vocabulary/listening quizzes
- recent-study records, goals and frequently missed words

This product is unusually close to the original HEARD concept.

**Finding:** `한글 발음 검색 → 단어 확인 → 저장 → 퀴즈` is already a competitive product pattern. Search + save + quiz alone is insufficient differentiation.

### B. Structured kanji / grammar learning

#### WaniKani

- 2,000+ kanji / 6,000+ vocabulary
- radicals + mnemonics
- SRS lessons/reviews
- tightly sequenced curriculum

Strength: systematic kanji literacy.  
Gap relative to our hypothesis: the curriculum starts from WaniKani's sequence, not from a phrase the learner just heard and already cares about.

#### Bunpro

- Japanese grammar SRS
- 10,000+ example sentences
- native audio
- mistake-focused reviews
- customizable review difficulty

Strength: systematic grammar retention.  
Gap: not centered on sound-first identification of an unknown written phrase.

### C. Media / immersion learning

#### Migaku

Supports learning from YouTube, Netflix and other authentic media, with word lookup, one-click flashcards, SRS, OCR and progress tracking.

#### LingQ

Lets users learn from or import content they care about: YouTube, songs, podcasts, books, TV, articles, etc. Content becomes an interactive lesson with transcripts, vocabulary saving and review.

#### jpdb

Japanese dictionary + SRS with vocabulary extraction from text and thousands of premade media decks, including anime.

**Finding:** “learn from content you love” and “your content becomes your curriculum” are already validated product directions. They are attractive, but not unique enough as a positioning statement.

### Competitive whitespace observed

Among the products reviewed, the workflow is usually split across categories:

- dictionary → identify a word
- kanji app → learn characters on a fixed sequence
- immersion tool → begin with media/text/subtitles
- SRS → review already-created cards
- general learning app → follow a predefined course

The potentially distinct workflow is narrower:

`remembered sound → identify plausible phrase(s) → use context to disambiguate → connect sound/script/meaning/grammar → test recognition/recall → save into personal review`

The opportunity is therefore **not phonetic search itself**, but turning already-acquired auditory knowledge into durable script literacy with minimal tool switching.

---

## 3. Secondary user research

> Method note: This is desk-based qualitative research using public learner discussions and product/user material. It is not a substitute for primary interviews with Korean target users.

### Pattern 1 — Listening familiarity and script knowledge can diverge

A highly relevant Japanese-learning discussion describes a learner who immediately knows a word's meaning after hearing its audio but feels as though the kanji is completely unfamiliar when seeing it. Other learners in the same thread report the exact opposite pattern: reading is strong while listening is weak.

**Interpretation:** the important variable is not simply “Japanese level.” Learners can develop uneven modality profiles depending on exposure.

This supports a narrow target rather than “all Japanese learners.”

### Pattern 2 — Recognition is not the same as retrieval/production

Cross-language research shows the same phenomenon. A 2025 study of adult L2 English learners found receptive and productive collocation knowledge to be related but distinct constructs; productive knowledge lagged receptive knowledge, particularly at lower proficiency.

Public language-learning discussions repeatedly show learners who can understand speech but cannot retrieve words or construct sentences when they need to respond.

**Interpretation:** a result card that only explains a phrase may produce understanding without durable learning. The product should include a small active-recall step and later review.

### Pattern 3 — Learners value personally meaningful context

Public language-learning discussions frequently describe better motivation/retention when vocabulary comes from songs, videos, books, games or situations the learner personally cares about. Products such as LingQ and Memrise are explicitly positioned around interests/authentic content.

**Interpretation:** personal relevance is valuable, but the market already understands this. It should be a product principle, not the only differentiator.

### Pattern 4 — Music is powerful context, but unreliable as the sole language standard

J-POP/song-based learners report that melody and repeated listening can make vocabulary memorable. At the same time, Japanese learners warn that lyrics may use metaphor, unusual word order, uncommon vocabulary, artistic readings and non-conversational language.

**Interpretation:** J-POP is best treated as a high-motivation source/context layer, not as the definition of “normal Japanese.” The product needs labels/warnings such as:

- lyrics / everyday conversation / writing
- common / literary / stylized
- natural in speech / uncommon in speech

### Pattern 5 — Tool-switching is part of the pain

Learners describe interrupting listening to guess an unknown sound, search a dictionary, inspect text, and then manually create review material. Other users keep private spreadsheets, lists or dictionary playlists of words they personally encountered.

**Interpretation:** the product can create value by shortening the transition from “I just heard this” to “I identified and learned this.”

### Pattern 6 — The target is probably not an absolute beginner

Media-first learners can benefit from their existing internal sound vocabulary. A true beginner does not yet have enough sound/meaning associations for a sound-to-script bridge to provide the same advantage.

**Interpretation:** likely initial segment = hobby/media-driven beginner-to-intermediate learner with meaningful prior exposure, not zero-base beginner and not necessarily exam-first advanced learner.

---

## 4. English / other L2 market comparison

The same broad learning problems appear outside Japanese, but products solve them differently because Japanese has a distinctive script barrier.

### Speak

Core loop: `Learn → Practice → Apply`.

It explicitly positions itself around moving passive knowledge into spoken use through AI conversation and feedback.

**Transferable lesson:** learning should culminate in retrieval/application, not stop at explanation.

### Memrise

Uses native-speaker video, interests/personalization, smart review and AI speaking practice.

**Transferable lesson:** authentic content + level-appropriate support + review is already a mainstream expectation.

### Busuu

Combines community corrections with AI conversations and personalized feedback.

**Transferable lesson:** learners need low-pressure practice between “I learned it” and “I can use it with a person.”

### LingQ

Lets the user's preferred media become learning material.

**Transferable lesson:** curriculum can be generated from personal interests rather than only from a fixed course.

### Cross-language user pattern

English/German/Spanish/other L2 learner communities repeatedly show asymmetry between comprehension and speaking/writing. Some users can understand films, podcasts or conversation but cannot retrieve language quickly enough to respond; others have the reverse problem.

**Transferable lesson:** language learning products benefit from diagnosing the learner's actual modality gap rather than assuming a single linear level.

### What is specifically Japanese here?

For alphabetic L2s, a learner may recognize a sound but still struggle with spelling or production. Japanese adds a much larger orthographic bridge:

- kana vs kanji
- multiple readings
- homophones
- inflection/conjugation
- script choice
- artistic readings in lyrics

This makes `sound → exact written form` a stronger standalone learning problem in Japanese than in many alphabetic languages.

---

## 5. Synthesis — core insights

### Insight 1. The problem is a modality gap, not simply lack of Japanese knowledge.

The primary user may already have substantial auditory familiarity. Their problem is that listening familiarity and script literacy developed unevenly.

### Insight 2. “Hangul pronunciation search” is a commodity feature.

NAVER already supports it, and 난데스까? is built directly around it. Search cannot be the core value proposition.

### Insight 3. The opportunity is the transition from lookup to learning.

The strongest product loop is potentially:

`heard/remembered sound → contextual identification → script mapping → explanation → discrimination/recall → personal review`

The value is the conversion of existing auditory knowledge into durable readable/retrievable knowledge.

### Insight 4. Phrase-level context matters more than isolated-word lookup.

The target pain often appears in conjugated phrases and homophones. A single sound such as `いった` cannot reliably map to one kanji form without context. The product should therefore work at phrase/sentence level and allow context input.

### Insight 5. Personal content is motivating but not differentiating by itself.

LingQ, Migaku, Memrise, jpdb and others already connect study to authentic/personal content. Our wedge needs to remain the **sound-first entry point + Japanese script bridge**.

### Insight 6. J-POP is a powerful acquisition surface, but needs language-register guidance.

Music can drive repeated exposure and emotional memory, but learners should be told when an expression is lyrical, literary, stylized or uncommon in conversation.

### Insight 7. Explanation alone is insufficient.

Receptive knowledge and productive/retrieval knowledge are different. A lookup should end with a small active task and reappear later in review.

### Insight 8. The first segment should be narrow.

Provisional primary segment:

> Korean-speaking, media-first Japanese learners who have accumulated meaningful listening familiarity through J-POP/anime/drama/travel and can often recognize or imitate phrases by sound, but whose reading/writing—especially kanji/katakana and exact phrase forms—lags behind.

Out of scope initially:

- true zero-base beginners
- users whose primary problem is listening despite strong reading
- pure JLPT/exam-first learners
- advanced readers looking only for dictionary depth

---

## 6. Provisional problem definition

### Problem Statement

Korean media-first Japanese learners can accumulate many phrases whose sounds and rough meanings are familiar through repeated exposure, while still failing to connect those phrases reliably to kana/kanji forms. Existing products reviewed provide Hangul phonetic lookup, structured kanji/grammar study, media immersion, dictionaries and SRS, but the learner's workflow from a **remembered sound** to contextual identification, script understanding and later recall is often divided across separate tools or separate learning modes.

As a result, learners must repeatedly guess spellings, search, compare candidates, inspect grammar/kanji, and manually decide whether/how to save the expression. The auditory knowledge they already possess does not automatically become readable or retrievable Japanese.

### Jobs To Be Done

**Primary job**

> When I hear or remember a Japanese phrase from music, anime, video or real life but only know how it sounds, help me identify the likely original expression and connect it to the written Japanese while the context is still fresh.

**Learning job**

> Once I find an expression I already know by sound, help the written form stick so I can recognize and retrieve it later instead of looking it up again.

**Motivation job**

> Let the Japanese I genuinely care about become my learning material instead of forcing me to wait until a fixed curriculum reaches it.

### How Might We

> How might we help Korean media-first Japanese learners convert phrases they already know by sound into readable and retrievable Japanese, at the moment they encounter them, with minimal tool switching?

Secondary HMW:

> How might we preserve the motivation of learning from J-POP/anime while clearly distinguishing lyrical/stylized Japanese from everyday usage?

---

## 7. Implication for the current concept

The initial concept should **not** be discarded, but its center shifts.

Old framing:

`한글 발음 입력 → 일본어 찾기`

Stronger framing after research:

`내가 이미 귀로 알고 있는 일본어 → 문맥으로 원문 식별 → 문자와 의미 연결 → 바로 확인/회상 → 내 표현으로 축적`

This suggests that HEARD and LISTEN belong to the same core problem. WRITE may still be valuable later, but it solves a broader production/translation problem and should not automatically be part of the first MVP before primary validation.

---

## 8. What secondary research cannot validate

Before Product Planning is finalized, primary research with Korean learners should test:

- frequency of the sound-to-script problem
- severity/frustration of the problem
- contexts where it happens most (J-POP, anime, drama, travel, conversation, shorts, etc.)
- current workaround and number of tools used
- awareness/use of NAVER phonetic search or 난데스까?
- where current phonetic lookup fails (phrase length, slurred/sung sound, ambiguity, grammar, context, review)
- whether users actually want to save/review after lookup
- whether HEARD is frequent enough to create repeat usage
- which part users would pay for, if any
- strongest proficiency/age/motivation segment

Until these are tested, the target segment and problem statement above remain **research-backed hypotheses**, not final validated conclusions.

---

## Key sources

- Japan Foundation, Survey on Japanese-Language Education Abroad 2024  
  https://www.jpf.go.jp/e/project/japanese/survey/result/information.html
- Duolingo, 2025 Language Report  
  https://blog.duolingo.com/2025-duolingo-language-report/
- NAVER Japanese Dictionary Help — search methods  
  https://help.naver.com/service/5609/contents/1528?lang=ko&osType=PC
- 난데스까? — App Store  
  https://apps.apple.com/kr/app/id6790024881
- WaniKani  
  https://www.wanikani.com/
- Bunpro pricing/features  
  https://bunpro.jp/pricing
- Migaku Japanese  
  https://migaku.com/learn-japanese
- jpdb  
  https://jpdb.io/
- LingQ  
  https://www.lingq.com/en/
- Speak  
  https://www.speak.com/
- Memrise  
  https://www.memrise.com/
- Lee, S. (2025), receptive vs productive L2 English collocation knowledge  
  https://onlinelibrary.wiley.com/doi/full/10.1111/ijal.12605
- Ehri, L. C. (2014), Orthographic Mapping  
  https://doi.org/10.1080/10888438.2013.819356

Public community discussions were used only as qualitative secondary-research signals and are not treated as representative population statistics.
