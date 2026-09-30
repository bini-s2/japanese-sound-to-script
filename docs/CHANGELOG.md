# Project Changelog

> Production code는 `bini-s2/readdy-1ff67b`에 있으며, 이 문서는 기능 단위의 **프로젝트 기록**이다.

## 2026-09-30 — UI system & result hierarchy

- Home에서 불필요한 설명/데모 CTA를 제거해 정보 밀도를 낮춤
- Home major section spacing을 공통 token으로 통일
  - Desktop 112px
  - Mobile 78px
- 추천 검색어 라벨/칩을 정리
- 정보성 tag system 통일
  - light gray fill
  - primary blue text
  - 12px / medium 500
- expression result에 한국어 발음 라인을 확실히 노출
- 결과 위계를 `원문 → 읽기 → 한국어 발음 → 뜻`으로 고정

Related production commits:
`02382086`, `fff437b0`, `4cba51a8`, `fa6276db`, `90449473`, `917dd5f9`, `849ad198`, `75f7dd0e`

## 2026-09-29 — JLPT N5 beta

- JLPT 학습 페이지 추가
- 입문 / N5 / N4 / N3 / N2 / N1 목표 레벨 UI
- N5 문법·문맥형 어휘·짧은 독해·청해 구현
- 10문항 미니 테스트 구현
- 문제 및 선택지 reshuffle
- 청해 안정화
  - same-origin server audio 우선
  - browser TTS fallback

Related production commits:
`0011d6f4`, `a5d06c20`, `b3c11bab`, `58a004b8`

## 2026-09-26 — Random Quiz learning loop

- 무작위 / 상황별 랜덤 퀴즈
- 글자 / 단어 / 문장 유형
- 글자: `Script → Sound`
- 단어·문장: `Sound → Script → Meaning`
- 5지선다
- 모르겠어요 → 복습하기
- 첫 오답 정답 비공개 / 두 번 오답 후 학습 카드
- Step 1에서 뜻을 먼저 보여주지 않도록 수정

Related production commits:
`638ef2ea`, `3baec5c5`, `eb586a60`, `0656c39c`

## 2026-09-25 — Character learning & search expansion

### Character learning

- 히라가나 / 가타카나 / 한자 학습 페이지
- kana 대응 문자 hover
- 혼합 보기
- 한자 한국어 발음 추가
- 혼합 모드 hover conflict 수정

### Search

- spaced input을 soft boundary hint로 활용
- whole phrase를 먼저 보호한 뒤 multi-word boundary 추론
- J-POP 가사체 / 문학적 표현 lexicon과 ranking evidence
- optional licensed lyric provider 구조

Related production commits:
`93a4f47e`, `71f7ec8f`, `074bc7ff`, `17a0032d`, `b73222cf`, `af4855a1`, `f817e008`

## Record rule from now on

- production code commit → `readdy-1ff67b`
- project meaning / decisions / implementation state → **this repository**
- meaningful session changes are grouped into `CURRENT-IMPLEMENTATION.md` and this changelog
- explicit public `/log` → `Design-log`
