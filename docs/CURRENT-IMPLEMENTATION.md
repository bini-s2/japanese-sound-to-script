# Current Implementation

> Last synced: 2026-09-30  
> Production source: `bini-s2/japanese-sound-to-script-web`  
> Live: https://sound-to-script.vercel.app/

이 문서는 **지금 실제로 배포되어 있는 제품 상태**를 설명하는 기준 문서다.
초기 기획 문서와 충돌할 경우 현재 구현은 이 문서를 우선한다.

## 1. Repository rule

- Project memory / planning / decisions / history: **`bini-s2/japanese-sound-to-script`**
- Production code / deployment: **`bini-s2/japanese-sound-to-script-web`**
- Public career work log: `bini-s2/Design-log` — explicit `/log` only

production에서 기능을 수정해도 그 기능의 의미와 결정은 이 planning repository에 다시 기록한다.

## 2. Current global navigation

Desktop:

`소리 검색 · 랜덤 퀴즈 · JLPT 학습 · 복습하기 · 북마크 · 문자 학습`

- 복습하기 / 북마크는 보조 카테고리로 시각적 weight를 낮춘다.
- 문자 학습은 주요 CTA 성격을 가진다.
- Mobile은 bottom navigation으로 같은 핵심 목적지를 제공한다.

## 3. Sound Search

Core:

`Sound → Script → Meaning`

지원 방향:

- 한글로 들린 발음 입력
- exact + fuzzy 후보
- 장음 / 촉음 / 탁음·유사 자음 흔들림
- 붙여 쓴 문장과 구문
- 띄어쓰기는 hard separator가 아니라 soft boundary hint
- multi-term boundary inference
- 구어체 / 문어체 / slang / J-POP lyrical expression
- Google autocomplete / web search signal 보조
- J-POP title popularity signal
- 필요 시 licensed lyric provider 연결 가능

검색 품질 원칙:

- 후보 수보다 **가장 자연스러운 결과가 위에 오는 것**
- 긴 고유명사·작품명이 짧은 일상 표현을 밀어내지 않음
- 사전 headword가 아니어도 문법·가사체 근거가 강하면 문장 후보 허용
- 이상한 기계 번역이나 transliteration-like 한국어 뜻을 차단

### Result hierarchy

현재 결과 위계:

`일본어 원문 → 히라가나 읽기 → 한국어 발음 → 뜻 → 태그/근거 → 학습하기/북마크 → Deep Dive`

예:

```
おはよう
おはよう
발음 · 오하요
좋은 아침
```

## 4. Character Learning

Route: 문자 학습

### Hiragana / Katakana

- 기본 46자 표
- 탁음·반탁음
- 요음
- 일반 모드에서 hover 시 대응 문자 비교
  - 히라가나 → 가타카나
  - 가타카나 → 히라가나
- **혼합 보기**에서 각 행을 히라가나 → 가타카나 순서로 붙여 학습
- 혼합 보기에서는 hover swap을 비활성화하여 글자가 사라지는 문제 방지

### Kanji

- 자주 쓰는 한자 / 표현 중심
- 위계:
  `한자 → 히라가나 읽기 → 한국어 발음 → 실제 예문`
- 처음 20개 + 더 보기로 40개
- 단독 음독/훈독 암기보다 실제 표현 안에서 읽기를 연결

## 5. Random Quiz

Entry:

`랜덤 퀴즈 → 무작위 / 상황별 → 글자 / 단어 / 문장`

상황 카테고리는 일상·취미·여행·J-POP·비즈니스 등의 맥락을 사용한다.

### Character

`Script → Sound`

- 표기를 보고 발음을 고름
- 5지선다
- 한자는 읽기가 정해지는 예시 문맥을 함께 제공

### Word

`Sound → Script → Meaning`

1. 한국어로 들리는 발음
2. 일본어 표기 5지선다
3. 한국어 뜻 5지선다

### Sentence

`Sound → Script → Meaning`

1. 발음으로 문장을 제시
2. 일본어 표기 선택
3. 뜻 선택

### Learning behavior

- 각 step에 `모르겠어요`
- 모르겠어요 → 약점 유형과 함께 복습하기에 저장
- Step 1에서 모르겠어요를 눌러도 **뜻을 미리 공개하지 않음**
- 첫 오답에는 정답 미공개
- 두 번 틀리면 해당 step의 정답 학습 카드 공개
- 다시하기는 정답 여부와 무관하게 항상 가능
- 다시하기/리셋 시 보기 순서를 다시 섞음

## 6. Bookmark / Review

### Bookmark

검색·학습에서 나중에 다시 볼 표현을 저장한다.

### Review

복습의 핵심은 스트릭이나 점수가 아니라 **왜 다시 봐야 하는지**다.

현재 약점 이유 예:

- 연결이 약함
- 여러 번 검색함
- 오래 안 봄
- 단어 표기 연결이 약함
- 단어 뜻 연결이 약함
- 표기 연결이 약함
- 뜻 연결이 약함

랜덤 퀴즈의 `모르겠어요`가 review queue로 연결된다.

## 7. JLPT N5 Beta

현재 실제 학습 가능:

- 문법
- 문맥형 어휘
- 짧은 독해
- 청해
- 10문항 미니 테스트

목표 레벨 UI:

`입문 / N5 / N4 / N3 / N2 / N1`

- 입문: 기존 문자 학습 / 랜덤 퀴즈로 연결
- N5: 실제 사용 가능
- N4~N1: 문제은행 검수 전 잠금

Mini test:

- 문법 3
- 어휘 3
- 독해 2
- 청해 2
- 총 10문항
- 문제 순서와 선택지 순서를 매번 shuffle
- 같은 영역 내 한 세션 문제 중복 방지

### Listening

청해는 브라우저 speechSynthesis만 의존하지 않는다.

1. same-origin `/api/tts` 오디오 endpoint 우선
2. 실패할 경우 browser TTS fallback

브라우저에 일본어 voice가 없는 환경에서도 재생 가능성을 높인다.

## 8. Current UI system decisions

### Major hierarchy

- White / very light gray-blue base
- Cobalt / royal blue primary
- Large typography
- Japanese original text is the visual anchor

### Semantic information tags

정보성 태그는 공통 system을 사용한다.

- Fill: light gray `var(--fill)`
- Text: primary blue
- Size: 12px
- Weight: Medium 500
- Radius: pill
- Padding: 9px 12px

적용 대상:

- 추천 검색어
- result badges
- bookmark meta
- review reasons
- random quiz context tags
- JLPT tags
- pronunciation suggestion tags

Tabs / filters / action buttons are not forced into this style.

### Home spacing

Home major sections use one shared vertical spacing token.

- Desktop: 112px
- Mobile: 78px

## 9. Important production commits

### 2026-09-25

- `93a4f47e` — kana and kanji learning page
- `71f7ec8f` — kana counterpart hover
- `074bc7ff` — mixed kana learning mode
- `17a0032d` — disable hover swap in mixed mode
- `b73222cf` — infer multi-word boundaries from spaces
- `af4855a1` — J-POP lyrical expression search
- `f817e008` — optional licensed J-POP lyric provider

### 2026-09-26

- `638ef2ea` — random quiz question banks
- `3baec5c5` — random quiz learning flow
- `eb586a60` — align quiz learning directions
- `0656c39c` — keep meanings hidden in step one

### 2026-09-29

- `0011d6f4` — JLPT N5 study beta
- `a5d06c20` — browser listening reliability
- `b3c11bab` — server audio fallback
- `58a004b8` — subpage spacing and quiz reshuffling

### 2026-09-30

- `02382086` — home review / CTA copy
- `fff437b0` — review grid / CTA hierarchy
- `4cba51a8` — remove redundant home demo buttons
- `fa6276db` — shared home section spacing
- `90449473` — simplify search example copy
- `917dd5f9` — recommended search chips
- `849ad198` — unified semantic tag system
- `75f7dd0e` — Korean pronunciation on expression results

## 10. Next priorities

- 일본어 문제 문장 / 오답 선택지 QA
- 랜덤 퀴즈 문제은행 확대
- N5 콘텐츠 밀도 개선
- N4 이상 JLPT 설계
- review 약점 데이터와 학습 모듈 연결 강화
- 실제 사용자 테스트
- 저장 데이터의 계정/동기화 필요성 검증
