# 자원순환 지도 (recycle-map)

지역별 재활용 거점(무인 회수기, 제로웨이스트 샵 등)을 찾아주는 웹 서비스.

## 스택

Next.js (App Router) · TypeScript (strict) · Tailwind CSS · Kakao Maps · Vercel

## 품질 기준

- `eslint-plugin-jsx-a11y` strict 프리셋을 error 레벨로 적용
- GitHub Actions에서 lint → 타입 체크 → 빌드 → Lighthouse CI 실행 (접근성 0.95 미만이면 실패)
- Gitleaks로 커밋 이력의 시크릿 유출 검사

## Lighthouse 기록

| 날짜 | 페이지 | Performance | Accessibility | Best Practices | SEO | 비고 |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-10-12 | `/` | 99 | 100 | 100 | 100 | 초기 세팅 (Hello World) |

## 개발

```bash
npm install
cp .env.example .env.local   # 키 값 채우기
npm run dev
```

## 환경 변수와 키 관리

- 실제 키는 `.env.local`(git 제외)과 Vercel 환경 변수에만 둔다. 저장소에는 키 이름만 적은 `.env.example`만 커밋한다.
- 서버 전용 키(`DATA_GO_KR_KEY`)에는 `NEXT_PUBLIC_`을 붙이지 않는다. 붙이면 브라우저 번들에 포함된다.
- 카카오맵 JS 키는 브라우저 노출이 전제이므로 카카오 콘솔에서 허용 도메인을 제한한다.
- CI의 `secret-scan` 잡(Gitleaks)이 커밋 이력 전체에서 키로 보이는 문자열을 찾으면 실패한다. 실수로 커밋했다면 이력 삭제가 아니라 **키 재발급**으로 대응한다.
