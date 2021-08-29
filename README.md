# `lerna-monorepo-example`

1. root 경로에 모든 패키지가 공통적으로 사용할 종속성을 설치하기 위해서는 `yarn add`, `npm install`을 사용한다. `lerna.json`의 설정으로 설치가 불가능할 경우에는 `--ignore-workspace-root-check` 옵션을 사용해서 설치할 수 있다.

2. lerna create <package_name>
```
lerna create first-package
lerna create second-package
```