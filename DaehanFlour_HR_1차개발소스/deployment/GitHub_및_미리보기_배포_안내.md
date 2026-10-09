# GitHub 업로드 및 미리보기 배포 안내

## GitHub에 올릴 때
- ZIP 자체가 아니라 압축을 푼 폴더 안의 파일을 저장소 최상위에 업로드합니다.
- `frontend`, `docs`, `deployment`, `.github` 폴더가 저장소 최상위에 있어야 합니다.
- 회사 소스/자료이므로 저장소는 비공개로 유지합니다.
- 원본 `saas-ustra-hr-master.zip`은 이 패키지에 포함하지 말고, 공개 저장소에도 올리지 않습니다.

## GitHub Pages
- Settings → Pages → Source에서 GitHub Actions 선택
- Actions 탭에서 `Build and deploy prototype to GitHub Pages` 실행 상태 확인
- 성공하면 Settings → Pages의 URL로 접속
- 빌드가 실패하면 Actions 로그를 서버/프런트엔드 담당자가 확인해야 합니다.

## 테스트 서버 개발자 전달 범위
이 ZIP은 화면/메뉴 협의용 React/Vite 프런트엔드 overlay입니다. 기존 U.STRA 애플리케이션과 통합된 완성 소스가 아닙니다. 기존 소스 원본은 read-only로 보존하고, 별도 브랜치/작업 사본에서 빌드와 배포를 검증해 주세요. 정책 미확정 메뉴의 HOLD/UNKNOWN 상태를 임의로 확정하지 말아 주세요.
