# 문제발생

Could not attach to pid : ~~~~

Error 1

# 발생원인

간헐적으로 발생하는 오류여서 코드에 문제가 있는 것은 아니고, 정확한 원인은 모르겠다. Xcode 시뮬레이터 자체의 문제로 보인다.

# 문제해결

- simulator 종료 후 재실행하였다.(실패)

- Clean Build Folder 후 재실행하였다. (실패)

- simulator 옵션에서 reset 시켰다. (실패)

- 이후 다시 Clean Build Folder (실패)

- simulator의 Developer - Reindex All items with Identifiers  simulator 재실행 (성공)
