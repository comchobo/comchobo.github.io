---
version: alpha
name: Monochrome Portfolio
description: 프로젝트를 명료하게 소개하기 위한 한국어 중심의 흑백 포트폴리오 디자인 시스템.
colors:
  primary: "#171717"
  on-primary: "#FFFFFF"
  surface: "#FAFAFA"
  surface-container: "#FFFFFF"
  on-surface: "#171717"
  on-surface-variant: "#626262"
  outline: "#737373"
  outline-variant: "#D9D9D9"
  surface-variant: "#EFEFEF"
  primary-dark: "#F2F2F2"
  on-primary-dark: "#171717"
  surface-dark: "#111111"
  surface-container-dark: "#181818"
  on-surface-dark: "#F2F2F2"
  on-surface-variant-dark: "#AAAAAA"
  outline-dark: "#8A8A8A"
  outline-variant-dark: "#393939"
  surface-variant-dark: "#252525"
typography:
  headline-lg:
    fontFamily: "Arial, 'Apple SD Gothic Neo', 'Noto Sans KR', sans-serif"
    fontSize: 3.375rem
    fontWeight: 600
    lineHeight: 1.25
    letterSpacing: -0.05em
  title-md:
    fontFamily: "Arial, 'Apple SD Gothic Neo', 'Noto Sans KR', sans-serif"
    fontSize: 1.5rem
    fontWeight: 600
    lineHeight: 1.25
    letterSpacing: -0.035em
  body-md:
    fontFamily: "Arial, 'Apple SD Gothic Neo', 'Noto Sans KR', sans-serif"
    fontSize: 1rem
    fontWeight: 400
    lineHeight: 1.75
    letterSpacing: 0em
  label-md:
    fontFamily: "Arial, 'Apple SD Gothic Neo', 'Noto Sans KR', sans-serif"
    fontSize: 0.875rem
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0em
  label-sm:
    fontFamily: "Arial, 'Apple SD Gothic Neo', 'Noto Sans KR', sans-serif"
    fontSize: 0.75rem
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0em
  meta:
    fontFamily: "ui-monospace, SFMono-Regular, monospace"
    fontSize: 0.75rem
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0.06em
rounded:
  none: 0px
spacing:
  xs: 0.25rem
  sm: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  2xl: 2rem
  3xl: 3rem
  4xl: 4rem
components:
  project-heading:
    textColor: "{colors.on-surface}"
    typography: "{typography.title-md}"
    rounded: "{rounded.none}"
  project-description:
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
  project-meta:
    textColor: "{colors.on-surface-variant}"
    typography: "{typography.meta}"
  project-tag:
    textColor: "{colors.on-surface}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.none}"
  link:
    textColor: "{colors.on-surface}"
    typography: "{typography.label-md}"
---

# Monochrome Portfolio

## Overview

경력 섹션 없이 프로젝트를 중심으로 소개하는 개인 포트폴리오다. 무엇을 만들고 어떤 문제를 다루었는지 쉽게 이해하도록, 장식보다 콘텐츠와 탐색에 우선순위를 둔다.

시각적 방향은 **흑백·무채색, 선명한 타이포그래피, 충분한 여백, 절제된 인터랙션**이다. 차이는 새로운 색이나 효과를 더하기보다 크기·간격·굵기·구분선으로 표현한다.

이 문서는 [Google Labs DESIGN.md Format](https://github.com/google-labs-code/design.md/blob/main/docs/spec.md)의 YAML 토큰 구조와 섹션 순서를 따른다. 해당 형식은 alpha 단계이며, 토큰의 정확한 값은 위 YAML에 정의하고 본문은 의미와 적용 방법을 설명한다.

구체적인 화면과 동작의 참조는 [`src/pages/index.astro`](src/pages/index.astro)다. `pnpm dev`로 실행해 홈(`/`)에서 확인한다. 화면별 배치·열 너비·아코디언 상태 전이는 페이지 구현이 담당하며 이 문서에 중복 명세하지 않는다. 현재 프로젝트·기술 분류·UI는 디자인 검토용 가상 예시다.

레퍼런스는 외형 전체를 복제하는 대신 다음 원칙을 참고한다.

- [Brittany Chiang](https://brittanychiang.com/): 프로젝트 제목·설명·링크의 정보 위계. 경력 섹션이나 색상은 차용하지 않는다.
- [AstroPaper](https://github.com/satnaing/astro-paper): 간결한 탐색과 읽기 편한 타이포그래피, 테마별 일관성.
- [Maggie Appleton](https://maggieappleton.com/): 짧은 소개에서 작업물로 자연스럽게 이어지는 흐름.

## Colors

모든 색은 무채색이다. 색 이름보다 **역할**을 기준으로 선택한다.

| 토큰 | 역할 |
| --- | --- |
| `primary` / `on-primary` | 주요 강조·포커스, 강조된 표면 위의 텍스트 |
| `surface` / `on-surface` | 페이지 바탕, 제목과 주요 본문 |
| `surface-container` | 예시 UI처럼 별도 표면이 필요한 영역 |
| `on-surface-variant` | 보조 설명·분류·메타 정보 |
| `outline` | 식별에 필요한 조작 요소 경계 |
| `outline-variant` | 장식적 구분선과 비조작 요소의 경계 |
| `surface-variant` | 미리보기 배경처럼 표면을 구분하는 영역 |

테마는 시스템의 `prefers-color-scheme` 설정을 따른다. Google Labs 형식에는 전용 테마 스키마가 없으므로 `-dark` 접미사의 평면 토큰을 사용한다. 이 접미사는 이 프로젝트의 명명 규칙이다. 다크 모드에서는 같은 역할의 `-dark` 값으로 교체한다.

CSS에서는 `colors.surface`를 `--color-surface`처럼 대응시킨다. 테마 전환 시 소비하는 CSS 변수 이름은 유지하고 값만 교체한다. `primary`는 포커스 외곽선에도 사용한다. 선택 상태는 밑줄과 의미 정보로 함께 전달한다.

`outline-variant`는 옅은 장식용 선이다. 필수 조작 요소나 포커스를 식별하는 유일한 수단으로 사용하지 않는다. 본문은 최소 4.5:1, 큰 텍스트와 필요한 UI 식별은 최소 3:1 대비를 목표로 실제 배경·상태 조합을 확인한다.

## Typography

외부 웹폰트 없이 설치된 서체를 사용하는 스택이다. 한글 fallback까지 확인하고, 특정 서체가 없다고 줄이 넘치거나 의미가 잘리지 않도록 한다.

- `headline-lg`: 페이지의 핵심 문장. 토큰 값은 최대 크기이며 화면 폭에 따라 축소한다.
- `title-md`: 프로젝트 제목. 긴 제목은 줄바꿈을 허용한다.
- `body-md`: 프로젝트의 주요 설명. 긴 문장은 적절한 읽기 폭과 넉넉한 행간을 확보한다.
- `label-md`: 보조 설명과 링크. 실제 링크는 밑줄로 식별한다.
- `label-sm`: 기술 태그와 보조 라벨.
- `meta`: 번호·분류 같은 짧은 메타 정보. 고정폭 서체와 절제된 자간을 사용한다.

CSS의 `--text-headline`, `--text-title`, `--text-body`, `--text-label`, `--text-meta`는 해당 크기 토큰에 대응한다. 서체·굵기·행간·자간도 함께 적용한다. 제목은 `word-break: keep-all`을 우선하고, 긴 URL·영문 문자열에는 넘침 방지 처리를 적용한다. 읽어야 하는 실제 콘텐츠를 말줄임으로 숨기지 않는다.

썸네일 안의 가상 UI는 프로젝트 결과물을 표현하는 삽화다. 축소된 삽화 내부 글자 크기를 실제 탐색이나 본문의 텍스트 크기 기준으로 사용하지 않는다.

## Layout

공통 간격은 `spacing` 척도를 사용한다. 작은 단계는 요소 내부와 밀접한 관계에, 큰 단계는 그룹과 주요 구역을 구분하는 데 사용한다. 의미가 같은 관계에는 같은 간격 단계를 적용한다.

`spacing.xl`은 `--space-xl`처럼 CSS에 대응한다. 정확한 폭·배치 순서·반응형 분기점은 참조 페이지에 둔다. 모든 화면에 동일한 고정 배치를 강제하지 않는다.

좁은 화면에서는 정보 순서를 유지하며 재배치한다. 320px 폭에서도 본문과 필수 조작에 가로 스크롤이 생기지 않아야 한다. 긴 제목, 한글·영문 혼용, 확대된 텍스트에서도 내용을 읽을 수 있어야 한다.

## Elevation & Depth

기본 그림자는 사용하지 않는다. 깊이는 `surface`, `surface-container`, `surface-variant`의 명도 차이와 필요한 구분선으로 표현한다. 의미 없이 카드를 여러 겹 쌓거나 입체 효과를 더하지 않는다.

## Shapes

기본 형태는 `rounded.none`의 직각이다. 구분선은 1px 실선으로 통일한다. 키보드 포커스는 `primary` 색의 2px 외곽선과 4px 간격을 사용한다. 이러한 규칙을 적용한 CSS 변수는 각각 `--border-width`, `--focus-width`, `--focus-offset`이다.

태그는 비조작 라벨이다. 조작 가능한 버튼처럼 보이는 과도한 모서리·그림자·호버 효과를 주지 않는다.

## Components

`components` 토큰은 공통 요소가 참조할 색상·타이포그래피·형태를 연결한다. 토큰 참조는 `"{colors.on-surface}"`, `"{typography.title-md}"` 문법을 사용한다. 실제 사용하지 않는 폼이나 버튼 변형까지 미리 정의하지 않는다.

- **프로젝트 항목:** 제목·요약·설명·분류의 위계를 일정하게 유지한다. 호버·선택 상태는 제목의 밑줄로 식별하며, 터치와 키보드에도 동등한 접근 경로를 제공한다.
- **프로젝트 제목 행:** 별도 펼침 아이콘은 두지 않는다. 조작 행은 네이티브 버튼으로 구현하고 `aria-expanded`, `aria-controls`로 상태와 콘텐츠 관계를 전달한다. 시각적인 일반 제목과 의미적인 조작 기능을 구분한다.
- **프로젝트 설명:** 제공된 사실을 우선하며, 해결한 문제·기여·결과는 실제 정보가 있을 때만 작성한다. 가상의 성과나 수치를 만들지 않는다.
- **링크:** 밑줄로 식별하고 목적을 알 수 있는 이름을 사용한다. 외부 링크 표시가 있다면 아이콘만으로 의미를 전달하지 않는다. 더미 링크는 예시 안내로 연결하며 실제 결과물인 것처럼 보이게 하지 않는다.
- **태그:** 짧은 분류 라벨에 한정한다. 본문 설명을 기술 태그의 나열로 대체하지 않는다.

키보드 포커스는 항상 보이게 한다. 숨겨진 패널의 링크는 탭 순서에서 제외하며, 사용 중인 패널을 마우스 움직임으로 갑자기 숨기지 않는다. 주요 조작은 24×24 CSS px 이상의 영역을 확보하고 좁은 화면에서도 인접 조작을 구분한다.

모션은 `--motion-duration: 160ms`, `--motion-easing: ease-out`을 사용한 짧은 불투명도 전환으로 제한한다. 이동·확대·높이 보간을 기본으로 추가하지 않는다. `prefers-reduced-motion: reduce`에서는 불필요한 애니메이션을 실행하지 않는다. 이는 별도 최상위 토큰 그룹이 아니라 이 형식의 컴포넌트 적용 규칙이다.

## Do's and Don'ts

**Do**

- 작업 시작 시 이 문서와 현재 홈을 함께 확인한다. 방향이 바뀌는 디자인은 시안을 보여주고 피드백을 받은 뒤 확정한다.
- 공통 토큰을 우선 재사용한다. 토큰을 바꾸면 YAML과 페이지 CSS의 대응 값을 같은 변경에서 갱신한다.
- 실제 프로젝트 자료와 검토용 가상 콘텐츠를 명확히 구분한다.
- `pnpm check`와 `pnpm build`를 실행한다. `pnpm dev`로 실제 화면과 상호작용도 확인한다.
- 화면 변경은 모바일·데스크톱, 라이트·다크에서 확인하고 긴 콘텐츠·가로 넘침·포커스·터치·모션 감소를 점검한다.
- PR에는 변경 이유, 검사 결과, 관련 스크린샷, 미검증 항목을 기록한다. 검사를 실행하지 않았다면 통과로 보고하지 않는다.

**Don't**

- 비슷한 회색·간격·글자 크기를 이유 없이 추가하지 않는다.
- 그라데이션·유색 강조·강한 그림자·장식적 모션을 기본 스타일로 도입하지 않는다.
- 호버만으로 필수 콘텐츠를 제공하거나, 키보드 사용자의 포커스를 숨기지 않는다.
- 접근성을 고려한 일부 검사만으로 전체 WCAG 적합성을 주장하지 않는다.
- 개별 화면의 배치와 상태 전이 구현을 이 문서에 중복 명세하거나, 실제 사용하지 않는 디자인 시스템을 미리 확장하지 않는다.

검증 기준의 참고 문서는 [WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/)와 [Playwright 브라우저 검증 문서](https://playwright.dev/docs/intro)다.
