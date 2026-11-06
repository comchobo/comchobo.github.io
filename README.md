# comchobo.github.io

Astro + TypeScript + pnpm 기반 개인 사이트의 초기 개발·배포 환경입니다.
현재 `/`는 콘텐츠 없는 빈 페이지이며, 소개·작업·메뉴·테마는 아직 구현하지 않았습니다.

## 개발 환경

- Node.js 24 (`.node-version`, CI에서도 같은 버전 사용)
- pnpm 12.16.1 (`package.json`의 `packageManager`에 명시)

Node.js 환경을 준비한 뒤 pnpm을 설치하고 실행합니다.

```sh
npm install --global pnpm@12.16.1
pnpm install --frozen-lockfile
pnpm dev
```

개발 서버 기본 주소는 `http://localhost:4321`입니다.

## 명령

| 명령 | 용도 |
| --- | --- |
| `pnpm dev` | 로컬 개발 서버 |
| `pnpm check` | Astro 및 TypeScript 검사 |
| `pnpm build` | 정적 사이트를 `dist/`에 빌드 |
| `pnpm preview` | 빌드 결과 로컬 미리보기 |

```sh
pnpm check
pnpm build
pnpm preview
```

미리보기에서 `/`가 정상 응답하고 화면이 비어 있으면 현재 단계의 의도된 동작입니다.

## 구성

- `src/pages/index.astro`: 빈 진입 페이지
- `astro.config.mjs`: 사이트 주소 및 Astro 설정
- `tsconfig.json`: Astro의 strict TypeScript 설정
- `pnpm-workspace.yaml`: pnpm이 생성한 최신 의존성의 배포 대기 기간 예외 목록
- `.github/workflows/pages.yml`: PR 검사 및 GitHub Pages 배포

## 배포

공개 주소: <https://comchobo.github.io/>

GitHub 저장소의 **Settings → Pages → Build and deployment → Source**는
**GitHub Actions**로 설정해야 합니다. 기존 `main` 브랜치 루트 게시 방식에서는
Astro 소스가 아닌 빌드 결과를 게시하도록 전환이 필요합니다.

- `main` 대상 PR: 의존성 설치, 검사, 빌드만 실행합니다.
- `main`에 push 또는 PR 병합: 검사·빌드 성공 후 `dist/`를 Pages에 배포합니다.
- 수동 실행: Actions의 **Check and deploy → Run workflow**에서 `main`을 선택합니다.

PR 생성만으로는 사이트가 배포되지 않습니다. 최초 배포는 PR 병합 후 실행 결과로 확인합니다.
