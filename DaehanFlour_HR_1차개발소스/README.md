# 대한제분 HR 1차 검증 프로토타입 — GitHub 업로드용

이 저장소는 고객과 메뉴·정책을 협의하기 위한 **프런트엔드 시제품**입니다.
실제 인사정보, 급여 계산, 로그인/SSO, 저장 기능, U.STRA API/DB 연동은 포함하지 않습니다.

## 1. GitHub에 올리기

1. GitHub에서 새 저장소(Repository)를 만듭니다.
2. 회사 업무용 자료이므로 기본은 **Private(비공개)** 로 설정합니다.
3. ZIP 압축을 푼 뒤, 이 폴더 안의 파일과 폴더를 저장소 최상위에 업로드합니다.
   - `frontend/`, `docs/`, `deployment/`, `.github/`가 저장소 최상위에 보여야 합니다.
   - ZIP 파일 자체만 저장소에 올리면 웹 화면은 실행되지 않습니다.
4. 기본 브랜치 이름은 `main`을 사용합니다.

## 2. GitHub Pages로 미리보기 배포

이 저장소에는 GitHub Actions 빌드/배포 설정이 포함되어 있습니다.

1. GitHub 저장소의 **Settings → Pages**로 이동합니다.
2. Build and deployment에서 **Source: GitHub Actions**를 선택합니다.
3. **Actions** 탭에서 `Build and deploy prototype to GitHub Pages` 작업이 실행되는지 확인합니다.
4. 작업이 성공하면 저장소의 **Settings → Pages**에 표시되는 사이트 주소로 접속합니다.

주의: 첫 배포는 패키지 설치와 빌드가 성공해야 진행됩니다. 이전 작업 환경에서는 패키지 설치가 시간 초과되어 빌드가 검증되지 않았습니다. Actions에서 실패하면 로그를 확인하고 오류를 수정해야 합니다.

## 3. Vercel로 미리보기 배포하는 경우

1. Vercel에서 GitHub 계정을 연결하고 이 저장소를 Import합니다.
2. **Root Directory**를 `frontend`로 지정합니다.
3. Framework는 Vite, Build Command는 `npm run build`, Output Directory는 `dist`로 설정합니다.
4. 배포 전에 접근 권한 설정을 확인합니다. 회사 내부 검토용이면 공개 URL로 민감한 자료가 노출되지 않도록 주의합니다.

## 4. 테스트 서버 개발자에게 전달할 파일

이 GitHub 업로드용 ZIP을 전달하셔도 됩니다. 함께 전달할 `deployment/서버담당자_전달문.txt`와 `deployment/테스트서버_배포및통합_안내.md`에 범위와 주의사항이 정리되어 있습니다.

다만 이 패키지는 **독립 프런트엔드 overlay**입니다. 기존 U.STRA Java/Gradle 애플리케이션 전체 소스나 통합 완료본이 아니므로, 테스트 서버 개발자는 기존 소스 작업 사본과 분리해 먼저 빌드·화면 검증을 해야 합니다. 원본 U.STRA 전체 소스를 공개 GitHub 저장소에 올리지 마세요.

## 5. 정책 미확정 항목

정책이 확인되지 않은 메뉴는 `HOLD` 또는 `UNKNOWN` 상태로 표시하고, 정책 확인 필요 안내를 제공합니다. 이를 승인된 정책이나 실제 업무 처리 기능으로 간주하면 안 됩니다.

## 6. 현재 검증 상태

- ZIP 내부 파일 구조 확인: 완료
- npm 의존성 설치 및 production build: **미검증** (이전 실행 환경에서 npm install 시간 초과)
- 브라우저/실제 서버 검증: **미실시**
- U.STRA API/DB 통합: **미실시**
