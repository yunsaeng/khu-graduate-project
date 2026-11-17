# khu-graduate-project

경희대학교 졸업 프로젝트(2023): JWT 인증 구현과 XSS 공격 시뮬레이션. 현재 리팩토링·고도화 진행 중이다.

## 브랜치와 태그
- `legacy-2023` (태그): 2023-12 최종 상태. 고도화 전 기준선.
- `main`: 기존 코드
- `refactor`: 고도화 작업 브랜치

## 실행
```bash
npm install
cd server && npm install && cd ../client && npm install && cd ..
cp .env.example server/.env   # 값 채우기
npm start
```

## 문서
`docs/` 참고: prd, design, decisions, tasks, measurements, issues, reviews

## 보안 시연 범위
XSS·토큰 탈취 시연은 localhost 환경에서만 실행한다. 외부 서비스를 대상으로 하지 않는다.
