# `lerna-monorepo-example`

1. root 경로에 모든 패키지가 공통적으로 사용할 종속성을 설치하기 위해서는 `yarn add`, `npm install`을 사용한다. `lerna.json`의 설정으로 설치가 불가능할 경우에는 `--ignore-workspace-root-check` 옵션을 사용해서 설치할 수 있다.

2. lerna create <package_name>
```
lerna create first-package
lerna create second-package
```

3. `lerna add`를 사용해서 각 패키지에 모듈 설치를 할 수 있는데 `--scope=package_name`을 사용해야 한다. `--scope` 옵션을 사용하지 않으면 모든 패키지에 설치한다. 각 패키지에 node_modules 폴더가 생성되지 않았지만, root 경로의 node_modules 폴더에 추가된 것이다.
```
lerna add jest --scope=first-package
```

4. 이 예제 프로젝트에서는 `lerna run --scope second-package run`으로 실행할 수 있다. 이 명령어는 `--scope` 옵션으로 패키지를 선택할 수 있고 해당 패키지의 `package.json`에 정의된 `run` 스크립트를 실행한다. 
```
❯ lerna run --scope second-package run
lerna notice cli v4.0.0
lerna notice filter including "second-package"
lerna info Executing command in 1 package: "yarn run run"
yarn run v1.22.0
$ node lib/second-package.js
Hello, firstPackage!
Done in 0.23s.
lerna success run Ran npm script 'run' in 1 package in 0.5s:
lerna success - second-package
```

---
#### 참고

https://pks2974.medium.com/mono-repo-%EB%A5%BC-%EC%9C%84%ED%95%9C-lerna-%EA%B0%84%EB%8B%A8-%EC%A0%95%EB%A6%AC%ED%95%98%EA%B8%B0-65c22029988

https://kdydesign.github.io/2020/08/25/mono-repo-lerna/

https://kdydesign.github.io/2020/08/27/mono-repo-lerna-example/