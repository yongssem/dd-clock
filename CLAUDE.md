## 디자인 톤 (뉴모피즘 / Neomorphism)

EduTime Pro 레퍼런스 기반. 부드러운 그림자 + 둥근 모서리 + 차분한 색.

### 폰트
- **Plus Jakarta Sans** (500/600/700) — Google Fonts CDN
- Galmuri11 / Pretendard 사용 금지
```html
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@500;600;700&display=swap" rel="stylesheet">
```

### 3가지 테마 (CSS 변수)
```css
.theme-light {
  --bg: #fbf9f8; --panel: #f1efee;
  --text: #1b1c1c; --text-muted: #4a504a;
  --primary: #4a654e; --primary-soft: #cceace; --primary-ink: #07200f;
  --accent: #8e4e14; --track: #e4e2e2;
  --shadow-light: rgba(255,255,255,1);
  --shadow-dark: rgba(0,0,0,0.08);
}
.theme-dark {
  --bg: #14171f; --panel: #1c1f29;
  --text: #f1efee; --text-muted: #a8aab1;
  --primary: #b0ceb2; --primary-soft: #2a3a2e; --primary-ink: #e6f4e8;
  --accent: #ffb780; --track: #2a2e3a;
  --shadow-light: rgba(255,255,255,0.04);
  --shadow-dark: rgba(0,0,0,0.55);
}
.theme-pastel {
  --bg: #ffe5ec; --panel: #fff0f5;
  --text: #5b2a6b; --text-muted: #8a5a9a;
  --primary: #c084d6; --primary-soft: #f7d8ff; --primary-ink: #4a1f5e;
  --accent: #ff6b9d; --track: #f7c8d8;
  --shadow-light: rgba(255,255,255,0.9);
  --shadow-dark: rgba(180,70,120,0.18);
}
```

### 뉴모피즘 그림자 패턴
```css
/* 떠 있는 패널 */
.neo {
  box-shadow:
    -8px -8px 16px var(--shadow-light),
     8px  8px 16px var(--shadow-dark);
}
/* 파인 영역 (인풋, 트랙) */
.neo-inset {
  box-shadow:
    inset -4px -4px 8px var(--shadow-light),
    inset  4px  4px 8px var(--shadow-dark);
}
/* 버튼 */
.neo-btn { box-shadow: -4px -4px 8px var(--shadow-light), 4px 4px 8px var(--shadow-dark); }
.neo-btn:active { box-shadow: inset -2px -2px 4px var(--shadow-light), inset 2px 2px 4px var(--shadow-dark); }
```

### 크기 가이드
- 시각 메인: 13rem (모바일 5rem)
- 초: 4.5rem (메인의 ~35%)
- 날짜: 2rem · 상태칩: 1.4rem
- stage 패딩: 56-64px, border-radius: 40px

### 컴포넌트 규칙
- **stage**: 중앙 패널, `var(--panel)` + `.neo` + `border-radius: 40px`
- **status-chip**: `var(--primary-soft)` 배경, pill
- **progress-track**: `.neo-inset`, height 22px, pill
- **progress-fill**: `var(--primary)`, 상단 흰색 하이라이트 그라데이션 허용
- **icon-btn**: 44×44 원형, `.neo-btn`
- **text-btn**: pill, `.neo-btn`

### 금지
- ❌ Galmuri11, Pretendard, 픽셀 폰트
- ❌ 픽셀 하드 그림자 (`4px 4px 0 #000`)
- ❌ 채도 높은 원색 (차분한 톤만)
- ❌ 인라인 스타일 / console.log 잔류
- ❌ `transition: steps()` 같은 픽셀 애니메이션

### 필수
- ✅ 색은 모두 CSS 변수 (테마 자동 전환)
- ✅ 항상 `border-radius` (직각 금지)
- ✅ 그림자는 `--shadow-light` / `--shadow-dark` 변수만
- ✅ 푸터: `© 2026 무궁무진클래스 · 용쌤 → mumuclass.kr`
- ✅ 트랜지션 0.2~0.6s ease
