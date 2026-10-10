# Project Changelog

## 2026-10-10 — Common polite expression retrieval fix

- Reported regression: Hangul sound query `와카리마스카` unexpectedly showed "no candidates" despite corresponding to `分かりますか（わかりますか）`.
- Confirmed the existing `api/search.js` local exact phrase inventory had `wakarimasen` but lacked `wakarimasuka`, so this basic question was not guaranteed to survive external candidate retrieval and sound-quality filtering.
- Added trusted local search entries for `分かります`, `分かりますか`, `分かりました`, and `分かりませんか`; the question includes a `分かります + か` segment explanation.
- Remaining limitation: this patches missing core expressions, not a general conjugation/grammar search engine. Additional natural polite forms and neighboring inputs still need regression coverage.
- Production source commit: `e1057fff137201461ab39d9574de0f88214f911e`
- Production Vercel: `READY` and GitHub Vercel commit status `success`.


## 2026-10-04 — Sound-search full pronunciation gate

- `사이고노`처럼 짧은 입력에 `最後の愛を`처럼 **입력 뒤에 다른 단어가 붙은 IME prediction 후보가 노출될 수 있던 문제** 수정
- 원인:
  - IME가 반환한 표면형에 실제 읽기를 다시 확인하지 않고 입력 발음을 후보 reading으로 재사용하는 경로가 있었음
  - Google 자동완성 후보에서 prefix match를 과도하게 점수 보정하는 로직이 있었음
  - 사전 검증에서 표면형 존재만으로 reading 불일치 후보가 통과할 수 있었음
- 수정:
  - IME·Google suggestion·licensed lyric search에 공통 `resolveImeSurfaceReading` gate 적용
  - mixed kanji/kana는 전체 입력 발음이 표면형 전체와 정렬될 때만 허용
  - pure kanji는 exact dictionary reading이 전체 발음과 일치할 때만 허용
  - prefix-only score boost 제거
  - dictionary evidence는 surface + reading을 함께 확인
- regression:
  - `最後の` ↔ `さいごの` 허용
  - `最後の愛を` ↔ `さいごの` 차단
  - `さいごのあいを` ↔ `さいごの` 차단
  - 조사 표기/발음 차이 `今日は / こんにちわ`는 정상 허용
- feature branch에서 첫 regression build 실패를 확인하고 조사 발음 정렬 조건을 수정한 뒤 재검증
- Vercel preview build `READY` 및 전체 npm regression suite 통과 후 PR #1 squash merge
- production commit: `cfcb62b3`
- production deployment: `READY`


## 2026-10-01 — Production repository rename

- production repository를 `readdy-1ff67b`에서 **`japanese-sound-to-script-web`**으로 변경
- 프로젝트 저장소와 production 저장소가 같은 naming family를 사용하도록 정리
- 역할은 그대로 유지
  - `japanese-sound-to-script` → 정돈된 제품/기획/결정/히스토리
  - `japanese-sound-to-script-web` → 실제 웹앱 코드/API/Vercel 배포
- rename 후 GitHub push 권한과 Vercel deployment status `success` 확인

> Production code는 `bini-s2/japanese-sound-to-script-web`에 있으며, 이 문서는 기능 단위의 **프로젝트 기록**이다.

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

- production code commit → `japanese-sound-to-script-web`
- project meaning / decisions / implementation state → **this repository**
- meaningful session changes are grouped into `CURRENT-IMPLEMENTATION.md` and this changelog
- explicit public `/log` → `Design-log`
