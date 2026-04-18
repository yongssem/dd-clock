## 디자인 톤 (픽셀 아트 스타일 통일)

### 폰트
- Galmuri11 (픽셀 한글 폰트) CDN 사용
- Pretendard 사용 금지
```html
<link href="https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2107@1.1/Galmuri11.woff2" rel="stylesheet">
<style>
  @font-face {
    font-family: 'Galmuri11';
    src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2107@1.1/Galmuri11.woff2') format('woff2');
  }
  * { font-family: 'Galmuri11', monospace !important; }
</style>
```

### 3가지 테마
```css
/* 밝은 모드 (기본) */
.theme-light {
  --bg: #FFF8F0;
  --text: #1A2A4A;
  --accent: #FF9500;
}
/* 어두운 모드 */
.theme-dark {
  --bg: #0A0E27;
  --text: #FFFFFF;
  --accent: #FFD95E;
}
/* 파스텔 모드 */
.theme-pastel {
  --bg: #FFE5EC;
  --text: #7C3AED;
  --accent: #FF6B9D;
}
```

### 픽셀 스타일 CSS (필수 적용)
```css
:root {
  --pixel-dark: #1A2A4A;
  --pixel-shadow: #000000;
}
* {
  font-family: 'Galmuri11', monospace !important;
  image-rendering: pixelated;
}
.pixel-btn {
  border: 3px solid var(--text);
  box-shadow: 4px 4px 0 var(--pixel-shadow);
  border-radius: 0 !important;
  transition: all 0.1s steps(2);
  cursor: pointer;
  padding: 12px 24px;
  background: var(--accent);
  color: var(--text);
  font-weight: bold;
}
.pixel-btn:hover {
  transform: translate(-2px, -2px);
  box-shadow: 6px 6px 0 var(--pixel-shadow);
}
.pixel-btn:active {
  transform: translate(2px, 2px);
  box-shadow: 2px 2px 0 var(--pixel-shadow);
}
.pixel-box {
  border: 3px solid var(--text);
  box-shadow: 4px 4px 0 var(--pixel-shadow);
  border-radius: 0 !important;
}
```

### 시계 디스플레이
- 시각 숫자: 18rem (초대형)
- 날짜·요일: 3rem
- 교시 정보: 2rem
- 모든 텍스트에 픽셀 폰트 적용

### 금지 사항
❌ border-radius 사용 금지
❌ smooth 애니메이션 X
❌ Pretendard 폰트 X
❌ 그라디언트 X
❌ rounded 클래스 X