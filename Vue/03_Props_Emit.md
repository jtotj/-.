# Setting


>* node와 npm 이 필수 조건이다.
>* node  관리는 nvm을 이용해서 작업한다.
    * 반드시 cmd `관리자 권한` 으로 실행하자
    * <a href="https://github.com/coreybutler/nvm-windows/releases" target="_black">NVM 다운로드</a>
    

```powershell
#node js 버전 설치
$ nvm install 0.10
$ nvm install v0.1.2
$ nvm install v8

# node 최신 버전 설치 (설치 당시 기준)
$ nvm install node

# node LTS 최신버전 설치
$ nvm install --lts

```

```powershell
# 설치된 node.js 목록 확인하기
$ nvm ls

# 설치할 수 있는 모든 Node 버전 조회 (재미삼아 해보지마세요 겁나많음... 황급히 control C 두드리기)
$ nvm ls-remote

# 특정 버전의 node 사용하기
$ nvm use <version>

# 현재 사용중인 버전 확인하기
$ nvm current

# node.js 설치 경로 확인하기
$ which node

# 필요없는 node 버전 삭제하기
$ nvm uninstall <version>
```