# PSH AI ARENA — 검증 관제실

PSH AI ARENA V2.4 개발·검증 이력과 MSG16 교착 과제를 관리하는 웹 관제실입니다.

**웹앱:** https://bduidohd937-beep.github.io/PSH-AI-ARENA/

## 현재 배포
- 관제실: **V1.2** (2026-11-12 저장소 이전)
- GitHub Pages: `main`에 변경이 생기면 `.github/workflows/pages.yml`이 자동 배포합니다.
- 배포 실행: [GitHub Actions](https://github.com/bduidohd937-beep/PSH-AI-ARENA/actions/workflows/pages.yml)
- 앱 시작 파일: `index.html`

## 주요 기능
- 세션 목표/완료 경기 수와 승패, 로그·리플레이·내보내기 검증 상태 관리
- MSG16 이후 `OCG_DuelProcess` 미반환 교착 P0 이슈 추적
- 결함 해결 시 다음 미해결 과제로 자동 승계
- 버전별 회귀 테스트 보고와 실제 대전 검증 결과 분리
- JSON/JSONL/CSV/TXT/LOG/ZIP 및 리플레이 파일 수동 업로드·검토
- SHA-256 근거 기록, JSON 백업 및 수동 승인
- 주간 검증·승인 우선순위 상위 3개 추천

## 검증 상태 주의
- V2.4 웹 테스트 9/9, 전체 252/252, V2.4.1 전체 254/254는 **이전 보고 기록**으로 앱 자체 재실행 결과가 아닙니다.
- MSG16 교착 해결과 실제 PSH 실전 파일 연동은 **미확인 또는 미해결**입니다.
- 관제실은 EDOPro·CDB·Lua 원본을 수정하지 않습니다. 원본 무결성은 해시 비교 기록으로 별도 검증해야 합니다.
- 웹앱이 저장하는 사용자 편집 데이터는 사용 중인 **브라우저의 localStorage**에 저장됩니다. 브라우저/기기간 공유 또는 자동 백업 기능은 없습니다. JSON 백업을 정기적으로 다운로드하세요.
- GitHub Pages의 정적 호스팅만으로 PSH 경기장 로컬 서버와 자동 연결되지는 않습니다. 로컬 세션 업로드 기능을 사용합니다.

## 기존 V1.2 HTML 데이터
기존 로컬 HTML을 사용 중이었다면 **기존 파일에서 JSON 백업 → 웹 버전에서 JSON 가져오기** 순서로 이전하세요. 웹 주소의 localStorage는 로컬 파일과 공유되지 않습니다.

## 배포
`main` 업데이트 시 GitHub Actions가 정적 HTML을 GitHub Pages로 배포합니다. 배포가 시작되지 않으면 저장소 `Settings → Pages → Build and deployment → GitHub Actions` 설정과 Actions 권한을 확인하세요.

## 프로젝트 구성
- `index.html`: 독립 실행형 관제실 V1.2, 브라우저 로컬 저장 방식
- `.github/workflows/pages.yml`: GitHub Pages 배포
