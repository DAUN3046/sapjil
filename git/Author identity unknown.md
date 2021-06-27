# 문제발생
Author identity unknown
*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'user@DESKTOP-5V2CFN3.(none)')

# 문제원인
일시적인 오류인듯 하다.

# 문제해결
git bash 접속하여 git config --list 명령어로 user.email 과 user.name이 정상적으로 출력되는 것을 확인.
이후 다시 실행하자 무사히 커밋이 진행되었다.
