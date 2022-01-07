# NPM Registry 생성부터 배포까지 연습해보기

## Prerequisite

1. npm 가입 

## 순서 

1. npm 초기화 
```bash
  $ npm init -y
```

2. dependency 설치 
```bash
  $ npm i commander 
```

3. cli 구현 
```bash
  $ mkdir bin 
  $ touch cli.js
```

```javascript
const { program } = require('commander');

//action
program.action(cmd => console.log('Running!'));
program.parse(process.argv);
```

4. package.json 수정 
```json 
  {
    ...
    "bin": {
      "log-run": "bin/cli.js"
    },
    "files": [
      "cli"
    ],
    ...
  }
```

5. local 테스트 
```bash
  npm link 
  log-run
```

6. .npmignore 작성 
```
node_modules
```

7. 배포 
```bash
  npm login
  npm publish
```