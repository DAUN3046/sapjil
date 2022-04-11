# 문제상황
**fatal: Could not read from remote repository.** 메시지가 뜨며 레포를 인식하지 못하고 깃허브 레포에 푸시가 안됨.

# 문제원인
처음부터 VSCode로 만들었던 저장소가 아니어서 브랜치 이름이 달랐다.

# 문제해결
origin이 아니라 main으로 연결했다. 결과적으로 파일을 직접 첨부했던 브랜치는 main, 이후 VSCode에 연동해서 추가한 브랜치가 master이다.
이제 수동으로 첨부하는 방식을 쓰지 않고 VSCode상에서 바로 푸시할 것이므로 master를 기본 브랜치로 변경했다. 기존 브랜치는 남겨둘 겸 삭제하지 않았다.
conflict 난 곳들은 따로 수정해줘야된다. git graph로 보면 이러하다. 연결했었네? 미리 확인하는 자세를 기르자.</br>
![image](https://user-images.githubusercontent.com/49031232/162668052-a3dee289-4f28-4210-b6fb-ced1d956be44.png)


## 전체 코드
```
PS C:\Users\linds\Desktop\htdoc> git init
Initialized empty Git repository in C:/Users/linds/Desktop/htdoc/.git/
PS C:\Users\linds\Desktop\htdoc> git add .
PS C:\Users\linds\Desktop\htdoc> git commit -m 20220411
[master (root-commit) 1137642] 20220411
 13 files changed, 323 insertions(+)
 create mode 100644 .vscode/asdf.html
 create mode 100644 .vscode/settings.json
 create mode 100644 1.html
 create mode 100644 2.html
 create mode 100644 3.html
 create mode 100644 css/box.html
 create mode 100644 css/grid.html
 create mode 100644 css/syntax.html
 create mode 100644 index.html
 create mode 100644 javascript/datatype.html
 create mode 100644 javascript/run.html
 create mode 100644 review.html
 create mode 100644 review2.html
PS C:\Users\linds\Desktop\htdoc> git remote add origin git@github.com:DAUN3046/elice-sw-2-2.git
PS C:\Users\linds\Desktop\htdoc> git push -u origin master
Warning: Permanently added the ECDSA host key for IP address '00.00.000.000' to the list of known hosts.
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
PS C:\Users\linds\Desktop\htdoc> git pull origin master --allow-unrelated-histories
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
PS C:\Users\linds\Desktop\htdoc> git pull origin main
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

PS C:\Users\linds\Desktop\htdoc> git remote update
Fetching origin
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
error: Could not fetch origin

Please make sure you have the correct access rights
and the repository exists.
PS C:\Users\linds\Desktop\htdoc> git remote -v                       origin  git@github.com:DAUN3046/elice-sw-2-2.git (fetch)
origin  git@github.com:DAUN3046/elice-sw-2-2.git (push)
PS C:\Users\linds\Desktop\htdoc> git pull origin main --allow-unrelated-histories
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
PS C:\Users\linds\Desktop\htdoc> git remote remove main
fatal: No such remote: 'main'
PS C:\Users\linds\Desktop\htdoc> git remote -v
PS C:\Users\linds\Desktop\htdoc> git remote add main https://github.com/DAUN3046/elice-sw-2-2.git  
PS C:\Users\linds\Desktop\htdoc> git remote -v
main    https://github.com/DAUN3046/elice-sw-2-2.git (fetch)
main    https://github.com/DAUN3046/elice-sw-2-2.git (push)
PS C:\Users\linds\Desktop\htdoc> git pull main main --allow-unrelated-histories
warning: no common commits
remote: Enumerating objects: 13, done.
remote: Counting objects: 100% (13/13), done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 13 (delta 7), reused 0 (delta 0), pack-reused 0        
Unpacking objects: 100% (13/13), 10.48 KiB | 170.00 KiB/s, done.
From https://github.com/DAUN3046/elice-sw-2-2
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> main/main
CONFLICT (add/add): Merge conflict in review.html
Auto-merging review.html
CONFLICT (add/add): Merge conflict in index.html
Auto-merging index.html
CONFLICT (add/add): Merge conflict in 3.html
Auto-merging 3.html
CONFLICT (add/add): Merge conflict in 2.html
Auto-merging 2.html
CONFLICT (add/add): Merge conflict in 1.html
Auto-merging 1.html
Automatic merge failed; fix conflicts and then commit the result.
PS C:\Users\linds\Desktop\htdoc> git branch
* master
```
