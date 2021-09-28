# Git/GitHub 특강

## 목차

- 마크다운(Markdown)을 활용한 문서 작성
- Git을 활용한 버전 관리
  - 버전관리 기본

- Git branch



## 마크다운(Markdown)을 활용한 문서 작성

1. 마크다운 개요
2. 마크다운 에디터 설치 - https://typora.io/

3) 마크다운 가이드 cheat sheet - https://www.markdownguide.org/cheat-sheet/

4. 마크다운을 이용한 예제 - "MarkDownSyntax.md" 참조



## Git

### Git 관련 소프트웨어 설치

- Git Bash
- VS Code



### Git 명령어

#### GitHub를 위한 정보 등록

- username과 email 등록

  ```bash
  $git config --global user.name "XxxYyyy"
  $git config --global user.email "XXXX@gmail.com"
  ```

- username과 email 확인

  ```bash
  $git config --global user.name
  $git config --global user.email
  ```



#### 저장소 생성

- .git 저장소가 생성되고, CLI 환경에서는 (master) 브랜치가 나타난다.

  ```bash
  $git init
  Initialized empty Git repository in D:/Workspace/github-training/.git/
  ```



#### 버젼 관리

##### status

- 상태확인(Untracked, changed files on tracked)

```bash
$git status # working directory / staging area
```



##### add

- 스테이지 파일 (버젼기록 1단계)
- 스테이지 AREA를 두는 이유: 수정된 파일들 중, 사용자가 원하는 파일들만 staging한 후, commit 처리

```bash
$git add .
$git add <file명>
$git add -A
```



##### restore

- 스테이지 파일을 unstage
- 스테이지되지 않은 변경된 파일의 수정을 취소

```bash
$git restore --staged .         # 수정한 내용은 그대로 두고, unstage시킴
$git restore --staged <file명>  # 수정한 내용은 그대로 두고, unstage시킴 
$git restore . # 스테이지 되지 않은 변경된 파일의 수정을 취소
$git restore <file명> # 스테이지 되지 않은 변경된 파일의 수정을 취소
```

##### 

##### commit

- 커밋 파일 (버젼기록 2단계)
- SHA-1 알고리즘에 40자 길이의 체크섬을 생성하고, 이를 통해 고유한 커밋으로 표시

```bash
$git commit -m '커밋메시지'
$git commit # 메시지 편집 창(기본 vim)
$git config --global core.editor "code --wait" # 메시지 편집 창을 VS Code로 변경
$git config --global core.editor "vim" # 메시지 편집 창을 vim으로 변경
```



##### log

- 로그확인, 로그 상세확인 옵션

```bash
$git log
commit 65f23c187e6f5c7adbcef69bc8dd8e44e655c396 (HEAD -> master)
Author: KyuSahm <gusami32@gmail.com>
Date:   Mon Sep 27 14:39:02 2021 +0900

    a.txt is changed
$git log --oneline -2  # 마지막 두 개의 리비전에 대한 간략한 수정 확인
65f23c1 (HEAD -> master) a.txt is changed
aaa2006 b.txt added    
$git log -p -1 # 마지막 리비전에 대한 상세 수정 확인
$git log -p -2 # 마지막 두개의 리비전에 대한 상세 수정 확인
$git show 43d581ad708f2bcb57cf530a03f59092749683c5 # 특정 리비젼 확인    
```



#### 원격저장소 관리

##### New Repository on GitHub

- New Repository > Repository 이름 입력 > Create repository 클릭

  

##### 원격저장소 등록

- 로컬에 이미 저장소가 존재하는 경우에 사용
- ``origin`` 이름으로 특정 URL을 등록
  - Git에게 원격저장소를 ``origin`` 이름으로 URL을 등록요청

```bash
$git remote add origin https://github.com/KyuSahm/github-training.git # GitHub repository를 origin으로 명명
$git branch -M main # 로컬의 현재 branch를 main 브랜치로 이름 변경
```

- 오류 메시지: 특정 이름으로 이미 등록된 경우, 에러가 발생
  - URL을 변경하거나 등록된 원격저장소를 삭제하고, 다시 등록

```bash
$ git remote add origin https://github.com/KyuSahm/github-training.git
error: remote origin already exists.
$ git remote rm origin # 삭제
$ git remote add origin https://github.com/KyuSahm/github-training.git # 다시 등록
```



##### 원격저장소에 Push

- 파일/폴더가 업로드 되는 것이 아니라 버전(커밋들)을 push하는 것

```bash
$git push -u origin main # GitHub에 Push
```

 

##### 원격저장소 복제

- 로컬에 저장소가 존재하지 않는 경우에 사용
- 원격저장소 자체를 로컬로 복제해서 가져옴

```bash
$git clone https://github.com/KyuSahm/TIL.git TIL-main # 원격저장소를 복제해 와서 TIL-main 폴더 생성
Cloning into 'TIL-main'...
remote: Enumerating objects: 29, done.
remote: Counting objects: 100% (29/29), done.
remote: Compressing objects: 100% (18/18), done.
remote: Total 29 (delta 8), reused 25 (delta 6), pack-reused 0
Receiving objects: 100% (29/29), 16.62 KiB | 8.31 MiB/s, done.
Resolving deltas: 100% (8/8), done.
```

 

##### branch -M 브랜치이름

- 로컬 브랜치 이름 변경

```bash
$git branch -M main # 로컬의 현재 branch를 main 브랜치로 이름 변경
```



### Config

#### 사용자 정보

- "C:\User\사용자명\\.gitconfig"에 사용자 정보가 존재

```bash
[user]
	name = KyuSahm
	email = gusami32@gmail.com
[gui]
	recentrepo = D:/Workspace/TestGit
[core]
	autocrlf = true
	editor = vim
```

- GitHub에 Push하는 경우의 로그인 정보는 Window의 Certificate에 GitHub관련 정보가 존재

#### Editor 변경

- 기본으로 VIM Editor을 제공
- 아래의 명령어를 이용해서, VS Code로 변경 가능

```bash
$git config --global core.editor "code --wait" # to VS Code
$git config --global core.editor "vim" # to vim
```



#### .gitignore 설정

- 버젼관리가 필요없는 폴더 및 파일들을 리스트함

```tex
# 특정 파일
data.csv
# 특정 폴더
secret/
# 특정 확장자 (*)
*.csv
```

- .gitignore 파일 생성방법
  - "https://www.toptal.com/developers/gitignore"에서 "OS, IDE, Language"를 명시
  - 예를 들면, ``windows`` , ``eclipse``, ``java`` 를 입력하면 됨



#### push error

- 버젼관리가 필요없는 폴더 및 파일들을 리스트함
- GitHub에 새로운 commit을 하고난 후, 로컬에서 또다른 commit을 한 후, push하는 경우

```bash
$git push origin main
To https://github.com/KyuSahm/TIL.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/KyuSahm/TIL.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

- 해결방법

```bash
$git fetch # github 최신 정보 update
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 648 bytes | 40.00 KiB/s, done.
From https://github.com/KyuSahm/TIL
   4ea5c5d..4cdac8a  main       -> origin/main
$git pull origin main # github의 최신 리비젼 가져오기
From https://github.com/KyuSahm/TIL
 * branch            main       -> FETCH_HEAD
Merge made by the 'recursive' strategy.
 ddd.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 ddd.txt
$git push origin main
$git log --oneline # 최종적으로, 3개의 commit이 발생 (commit for GitHub, local and merge)
b5b7e93 (HEAD -> main, origin/main) Merge branch 'main' of https://github.com/KyuSahm/TIL # branch merge
9c35037 cc.txt created        # local commit
4cdac8a Create ddd.txt        # GitHub commit
b961637 VIM is best
5cd2119 Test for changing editor config
6e658f6 New file "t.txt" added commit message test
4ea5c5d add image file
4f16358 my git summary added
66fe586 markdown files added
a1f87ae readme file created
```

### Branch

#### 브랜치 생성

```bash
$git branch {branch naame}
```



#### 브랜치 이동

```bash
$git checkout {branch name}
```



#### 브랜치 생성 및 이동

```bash
$git checkout -b {branch naame}
```



#### 브랜치 목록

```bash
$git branch	   # local branch 목록
$git branch -a # remote branch 포함
```



#### 브랜치 삭제

```bash
$git branch -d {branch name}
```



#### Branch merge

- 각 branch에서 작업을 한 후, 이력을 합치기 위해 사용
- 충돌 발생 시, 직접 수정 처리
- 로컬의 두 개의 Branch를 병합하면, 병합하면서 바로 Commit 처리됨.
- 사이트에서는 GitHub의 Remote Repository Commit들을 로컬로 Pull(Fetch + Merge)을 통해서 병합. 충돌시 해결 후, Push 처리
- 대상 Branch의 특정 Commit들만을 Merge하기 위해서, git cherry-pick 명령어를 사용

```bash
$git checkout main       # Merge할 브랜치로 이동
$git merge {branch name} # Merge 대상 브랜치의 이름을 입력하여 Merge처리
$git cherry-pick 4386f7c # Merge 대상 브랜치의 commit hash number를 입력하면 됨
```



### 개발 프로젝트 (끝말잇기)

> master 브랜치만 이용할 때

#### 조장

- 원격 저장소 생성 및 로컬 저장소 연결

```bash
$git init
$touch README.md
$git add .
$git commit -m "Init"
# Github에서 원격저장소 end를 만들고
$git remote add origin {url}
$git push origin main
```

- GitHub 원격저장소 초대
  - 초대!
  - settings > manage access > invite a collaborator

#### 조원

- 이메일로 초대 수락
- git 저장소 clone

```bash
$git clone {URL}
# 주의 사항!!!
# clone은 저장소의 이름의 폴더를 만들어줌
$cd 폴더이름
```



#### 반복

1. 끝말잇기
2. add->commit
3. push
4. 다른 조원에게 pull 받으세요~~ 이야기하기

---

1. pull을 받고, 끝말잇기, add->commit->pull-> pull받으세요



### GitHub Flow Model

- Shared Repository Model
- Fork & Pull Model

Shared Repository Model의 경우, 해당 저장소에 Push 권한이 있으므로,  Fork과정이 생략된 것으로 이해하면 된다.



#### Fork

- In the top-right corner of the page, click **Fork**.
- 원본 URL의 소스를 나의 Repository로 복사해 온다



#### Pull Request(PR)

- 수정한 내용이 존재하니, 작업 브랜치를 검토후, 관리자에게 Master(Main) 브랜치에 합쳐 주세요
- [Git PR Request 사용해 보기](https://yhmane.tistory.com/108)
- [How to send PR Request](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork)
- [Git을 알면 편합니다](https://m.inven.co.kr/webzine/wznews.php?idx=219067&site=durango)
- Pull Request는 아래와 같은 흐름으로 진행 됩니다. 다음 파트에서 각 부분마다 어떤식으로 진행되는지 알아보도록 하겠습니다.
  1.  fork : 해당 Repository에 대한 권한이 있다면, 생략
  2.  clone & remote 설정
  3.  branch 생성 : 작업은 master나 main 브랜치가 아니라, 작업 브랜치를 생성해서 함.
  4.  git add, commit, push
  5.  pull request 생성 : GitHub 사이트에서 관리자에게 해당 브랜치의 작업 내용을 Merge 요청
  6.  관리자 pull merge : 관리자가 Merge처리
  7.  소스코드 동기화



#### 수강 후기

- 강사님 URL을 Fork해 온 후,  파일 생성해서 작성 후, PR을 보냄

```bash
$ git clone {Fork해온 URL}
$ cd ai-0928
$ touch 여러분이름.md
$ git add .
$ git commit -m "ㅇㅇㅇ 후기"
$ git push origin master
# 나의 GitHub 사이트에서 Pull Request(PR)을 보내면 강사님한테 전달됩니다.
```



