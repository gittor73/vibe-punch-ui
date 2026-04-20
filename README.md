# Vibe Punch v1.8 — UI Redesign

> VR 리듬게임 **Vibe Punch** (Meta Quest, $19.99) 의 v1.8 UI 리디자인 프로토타입. HTML 와이어프레임 기반 상호작용 시안.

**🔗 Live Preview:** https://gittor73.github.io/vibe-punch-ui/

---

## 📌 목적

v1.8은 **Weekly Streak 시스템 + FIST Journey + Badge 40개 + Rank 22단계**를 통합하는 대규모 UI 업데이트입니다. 이 리포는:

- 기획 확정된 UI 구조를 **상호작용 가능한 HTML 와이어프레임**으로 시각화
- 개발팀 · 아트팀 · 기획팀이 **같은 링크로 동일한 시안** 확인
- 변경 요청과 반영을 **커밋 히스토리로 추적**
- 최종 비주얼 합성(나노바나나) 전 **레이아웃/밀도/상호작용 검증**

---

## 🗂 파일 구조

| 파일 | 역할 | 링크 |
|------|------|------|
| **`index.html`** | 메인 진입점 — 리스트 형태로 모든 화면 링크 + 변경사항 요약 | [열기](https://gittor73.github.io/vibe-punch-ui/) |
| **`left.html`** | 왼쪽 패널 단독 (280px) — Streak Fire + SETTING 토글 | [열기](https://gittor73.github.io/vibe-punch-ui/left.html) |
| **`right.html`** | 오른쪽 패널 단독 — HOME / STATS / BADGES / LEADERBOARD 4탭 | [열기](https://gittor73.github.io/vibe-punch-ui/right.html) |
| **`space.html`** | 공간 홀로그램 구성요소 설계도 — S1 / S2 / T1 | [열기](https://gittor73.github.io/vibe-punch-ui/space.html) |
| **`popups.html`** | 팝업 5종 — 다이아몬드 스타일 (UNLOCKED 참고) | [열기](https://gittor73.github.io/vibe-punch-ui/popups.html) |
| **`common.css`** | 공통 스타일 토큰 — 컬러 / 폰트 / 레이아웃 / 애니메이션 | 스타일 참조 |

---

## 🎨 디자인 원칙

### 기존 HTML (v3.36) 계승
- 전체 레이아웃: `280px + 1fr`, gap 14px, max-width 1200px
- 컬러 토큰: `--p` (#b44aff), `--pk`, `--cy`, `--gd`, `--fi`, `--tl`, `--gn`
- 폰트: **Orbitron** (제목/숫자), **Rajdhani** (본문), **Share Tech Mono** (값)
- 카드: `.mc` 패턴 (label 11px + value 20px + sub 10px)
- 탭 / 그리드 / 애니메이션 전부 재활용

### v1.8 신규/변경
- **심플화 우선** — 텍스트 10~13px, 섹션당 카드 최대 4개, 설명 최소화
- **팝업 재설계** — 다이아몬드 프레임 + 내부 아트 + 2줄 제목 + OK 하나
- **좌우 분리** — 왼쪽 280px / 오른쪽 ~880px, 패널 독립적으로 수정 가능
- **공간 홀로그램 분리** — VR 3D 요소는 평면 UI와 다른 설계 문서

---

## 🔄 v1.8 변경사항 (vs v3.36)

### 삭제
- ❌ **GRACE 배지** — FIST 보관/장착 UI가 별도로 존재
- ❌ **HOME 탭 WEEKLY STREAK 섹션** — S1 공간 홀로그램으로 통합
- ❌ **HOME 탭 FIST STATUS 섹션** — 별도 UI 존재
- ❌ **STATS HISTORY 서브탭** — OVERVIEW에 RECENT 5 통합 (4 → 3 서브탭)
- ❌ **팝업 P4 FIST SWAP** — FIST 보관/장착 UI가 별도 존재

### 변경
- 🔄 **BADGES 105 → 40개** — 4카테고리 (Rhythm 12 / Combo 10 / Explore 4 / Streak 14)
- 🔄 **MODIFIER 토글 v1.9 비활성** — 슬롯 예약, v1.8은 SETTING만 활성
- 🔄 **팝업 전체 재설계** — 첨부 UNLOCKED 이미지의 다이아몬드 스타일

### 확정
- ✅ **Streak 마일스톤 14단계** — FIST 10개 + 칭호/이펙트 4개
- ✅ **FIST 10단계 불꽃 네이밍** — SPARK / FLAME / BLAZE / INFERNO / FIRESTORM / SOLAR FLARE / PHOENIX / SUPERNOVA / STARBURST / ETERNAL FLAME

---

## 📅 Version Log

| Version | Date | Summary |
|---------|------|---------|
| **v0.4** | 2026.04.20 | 초기 릴리즈 — 5개 화면 분리 + 공통 CSS + GitHub Pages 배포 |

향후 변경은 이 표에 누적 기록합니다.

---

## 🔗 관련 문서

- **Project:** Vibe Punch (Meta Quest, $19.99)
- **Jira Epic:** VP-569 Vibepunch Upgrade Plan
- **Confluence Space:** Vibe Punch (VI) · VPUP 카테고리
- **Reference File:** `vibe_punch_ui_v3_36.html` (프로젝트 파일)

---

## 🛠 수정 / 피드백 방법

### 팀 피드백
- Confluence 인라인 코멘트 → VPUP 카테고리 v1.8 UI 페이지
- Jira VP-569 에픽에 이슈 등록

### 직접 수정
1. 해당 파일 열기 → 연필 아이콘 (Edit)
2. 변경 후 커밋 메시지 규칙: `v0.X: [변경 내용 요약]`
   - 예: `v0.5: Remove BEST RECORDS from STATS OVERVIEW`
3. Commit → 1~2분 후 Pages 자동 반영

### 풀 리퀘스트 (대규모 변경 시)
1. 새 브랜치 생성: `feature/v0.X-description`
2. 변경 후 PR 생성 → 리뷰 후 merge

---

## 📐 기술 스택

- **HTML5 / CSS3** — 프레임워크 없음, 순수 웹 표준
- **Google Fonts** — Orbitron / Rajdhani / Share Tech Mono
- **SVG** — 랭크 링, 불꽃, 프로그레스 바
- **GitHub Pages** — 정적 호스팅, 자동 빌드

외부 의존성 최소화 → 로딩 속도 우수, 오프라인 캐싱 가능.

---

**Lila Soft · 2026**
