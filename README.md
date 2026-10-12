# 자원순환 지도 (recycle-map)

지역별 재활용 거점(무인 회수기, 제로웨이스트 샵 등)을 찾아주는 웹 서비스.

## 스택

Next.js (App Router) · TypeScript (strict) · Tailwind CSS · Kakao Maps · Vercel

## 품질 기준

- `eslint-plugin-jsx-a11y` strict 프리셋을 error 레벨로 적용
- GitHub Actions에서 lint → 타입 체크 → 빌드 → Lighthouse CI 실행 (접근성 0.95 미만이면 실패)

## Lighthouse 기록

| 날짜 | 페이지 | Performance | Accessibility | Best Practices | SEO | 비고 |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-10-12 | `/` | 99 | 100 | 100 | 100 | 초기 세팅 (Hello World) |

## 개발

```bash
npm install
npm run dev
```
