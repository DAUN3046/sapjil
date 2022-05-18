# node.js 패키지 설치 안될 때
# 문제
`npm i ~~` 패키지 설치 시 코드 문제가 아닌 **ERR**가 잔뜩 뜸(unable to resolve dependency tree ~~ )
# 원인
npm 7버전부터는 충돌 시 설치를 못하게 바뀌었다. 뒤에 `--force`를 붙여서 다른 의존들을 추가하거나, `--legacy-peer-deps`를 붙여 이전 버전에서와 같이 충돌을 무시하는 방법이 있다. 
# 해결
1. 캐시 삭제
```
npm cache clear --force
```
2. 뒤에 --save --legacy-peer-deps를 붙여서 다시 설치
```
npm i ~~ --save --legacy-peer-deps
```
