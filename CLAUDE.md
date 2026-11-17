# CLAUDE.md (Claude Code 작업 규칙)

## 프로젝트
- 졸업 프로젝트(JWT 인증 + XSS 시뮬레이션, 2023)의 리팩토링·고도화.
- 기준 코드: 태그 `legacy-2023`. 작업 브랜치: `refactor`. `main`은 건드리지 않는다.
- 현재 스택(고도화 중 변경될 수 있음, 변경은 docs/decisions의 ADR로 먼저 기록): React, Express, MySQL, JWT, bcrypt, express-session.
- 실행: 루트 `npm start` (client + server 동시 실행). 서버 환경변수는 `.env.example` 참고.

## 문서 위치 (작업 전에 읽는다)
- 요구사항 `docs/prd.md`, 진행 상태 `docs/roadmap.md`
- 설계 `docs/design/`, 기술 결정 `docs/decisions/`
- 작업 스펙 `docs/tasks/T-NNN-*.md` (사용자가 "T-004 진행"이라고 하면 해당 파일을 읽고 시작)

## 작업 규칙
1. 작업 스펙의 범위와 완료 기준을 먼저 확인한다. 범위 밖 파일은 고치지 않는다. 필요하면 이유를 말하고 허락을 받는다.
2. 새 라이브러리·스택 변경은 구현 전에 이유와 대안을 설명하고, 승인되면 `docs/decisions/`에 ADR을 만든다.
3. 설계가 바뀌면 코드보다 `docs/design/`을 먼저 고친다.
4. 작업 단위로 커밋한다. 커밋 메시지는 `type: 내용`(feat, fix, refactor, test, docs, chore). 한 커밋에 여러 작업을 섞지 않는다.
5. 완료 기준은 테스트나 실행 결과로 확인한다. 확인하지 못한 것은 완료로 쓰지 않고 `[확인 필요]`로 남긴다.
6. 수치를 기록할 때는 `docs/measurements/`에 측정 방법, 환경, 커밋 해시, 측정 횟수를 함께 적는다. 측정하지 않은 수치는 쓰지 않는다.
7. 막힌 문제와 해결 과정은 `docs/issues/ISSUE-NNN-*.md`에 남긴다.
8. 작업이 끝나면 `docs/ai-workflow/log.md`에 항목을 추가한다. 내가 맡은 일, 결과, 사용자가 직접 검증한 부분, 잘못되거나 범위를 넘은 부분을 적는다.
9. 작업 스펙의 `결과` 섹션과 `docs/roadmap.md` 상태를 갱신한다.

## 하지 않는 것
- `.env`, 키, 토큰을 읽어서 출력하거나 커밋하는 것
- 보안 시연 코드를 로컬 밖의 대상에 쓰는 것
- `docs/exp-draft.md` 외의 위치에서 이력서·포트폴리오용 문장을 만드는 것 (그 일은 Claude 프로젝트에서 한다)
- 확인 없이 파일 삭제, `git push --force`, `main` 브랜치 수정

## 보안 시연 범위
- XSS·토큰 탈취 재현은 `localhost` 환경에서만 실행한다.
- 공격 코드는 취약 버전 시연용이며 외부 서비스를 대상으로 하지 않는다.
