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



##### commit

- 커밋 파일 (버젼기록 2단계)
- SHA-1 알고리즘에 40자 길이의 체크섬을 생성하고, 이를 통해 고유한 커밋으로 표시

```bash
$git commit -m '커밋메시지'
$git commit # 메시지 편집 창(기본 vim)              
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

##### 

##### branch -M 브랜치이름

- 로컬 브랜치 이름 변경

```bash
$git branch -M main # 로컬의 현재 branch를 main 브랜치로 이름 변경
```

