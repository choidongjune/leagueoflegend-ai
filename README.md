# leagueoflegend-ai

리그오브레전드(이하 롤)게임에서 수집된 데이터로 여러 서비스를 개발중에 있습니다.

## development environment

## git branch strategy and reason why we use

전반적으로 github-flow를 채택하여 따릅니다. 아래에 좀 더 자세하게 어떤 전략을 쓸지 설명합니다.
| 부모 브랜치 | 브랜치 명 | 역할 | 병합 브랜치 |
| ----------- | ----------- | ---------------------------------------- | ---------------- |
| | `main` | 배포 및 버전 관리 | |
| `main` | `develop` | 각각의 기능 개발이 끝난 후 취합 | |
| `develop` | `feature/*` | 기능 개발 | `develop` |
| `develop` | `release` | 배포 테스트 및 QA 진행 | `develop`,`main` |
| `main` | `hotfix` | product 서버에서 문제가 생겼을 시에 처리 | --- |

1. `main`브랜치는 언제나 배포가능한 형태여야 합니다.
2. 수시로 자신의 작업 내용을 원격 브랜치에 push합니다.
3. 피드백이나 도움, 혹은 merge을 할 준비가 되었다면 `pull-request`를 생성합니다.
4. develop에서 main으로 머지를 한다면 항상 태그를 붙여서 버전을 관리할 수 있도록 합니다.
5. main으로 머지를 하면 자동으로 배포가 될 수 있도록 합니다.(CI / CD)

## commit message conventions

[Conventional Commits](https://www.conventionalcommits.org/)을 기반으로 합니다.

```text

<type>[optional scope]: <description>

[optional body]

[optional footer(s)]

```

### type

| 타입       | 의미                                    |
| ---------- | --------------------------------------- |
| `build`    | 빌드 관련 작업 수행 (배포 파일 생성 등) |
| `chore`    | 프로젝트 설정 관련 작업 수행            |
| `ci`       | CI/CD 파이프라인 관련 작업 수행         |
| `docs`     | 문서 작성 또는 수정                     |
| `feat`     | 새로운 기능 추가                        |
| `fix`      | 버그 수정                               |
| `perf`     | 성능 개선                               |
| `refactor` | 코드 리팩토링                           |
| `style`    | 스타일 변경                             |
| `test`     | 테스트                                  |
| `comment`  | 주석 수정 또는 추가                     |
| `rename`   | 파일 및 폴더 이름 재설정 및 이동        |
| `remove`   | 파일 및 폴더 삭제                       |
| `!HOTFIX`  | 릴리즈 버전 치명적인 버그 수정          |

### extra

header-max-length: 100

body-max-length: 100

## directory structure
