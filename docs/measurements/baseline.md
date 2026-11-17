# 기준선 (legacy-2023)

## 기준 코드
- 저장소: https://github.com/yunsaeng/khu-graduate-project
- 태그: `legacy-2023`
- 커밋: `13d2e856c79aebf59438cfc148f497850def8f0e` (2023-12-08)
- 커밋 수: 24 (최초 2023-11-21)

## 현재 구조 (확인됨)
- 루트: client/ (React), server/ (Express), package.json (npm-run-all)
- 서버 엔드포인트: GET /authcheck, GET /logout, POST /login, POST /signin, POST /refresh
- 토큰 저장: 클라이언트 localStorage (id, accessToken, refreshToken)
- 환경변수: 서버 비밀값은 process.env로 읽음. 저장소에 .env 파일은 커밋되어 있지 않음.

## 측정 항목 (측정 전, 방법 확정 필요)
| 항목 | 측정 방법 | 기준값 | 측정일 | 환경 |
|---|---|---|---|---|
| 보호 API에서 토큰 검증 여부 | 토큰 없이/위조 토큰으로 호출 | [측정 필요] | | |
| 공격 시나리오별 성공 여부 (S-01~) | threat-model.md 참고 | [측정 필요] | | |
| 의존성 수·취약점 수 | npm ls, npm audit | [측정 필요] | | |
| 테스트 수·통과율 | | [측정 필요] | | |

## 측정 방법 메모
- 이전 코드를 직접 실행할 때: `git worktree add ../Graduate-Legacy legacy-2023` (측정 후 `git worktree remove ../Graduate-Legacy`)
