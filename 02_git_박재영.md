# Git
(버전을 통해) 코드를 관리하는 도구
+ 백업 도구
+ 협업 도구
+ 배포 도구

## Git
* SCM(Source Code Management): 코드 관리 도구
* VCS(Version Control System): 버전 관리 시스템(도구)
* DVCS(Distributed VCS): 분산형 버전 관리 시스템(도구)

## I. Git 명령어
`git [명령어]`
### (1) `git init` : Git 프로젝트 시작
- Git 은 폴더(디렉토리) 단위로 코드를 관리
- Git 프로젝트 시작전에는 해당 프로젝트를 관리할 폴더(디렉토리)를 생성
- 결과: 프로젝트 폴더 내에 `.git`폴더 생성

### (2) `git status` : Git 상태 출력

#### 최초 상태
-결과
```bash
On branch master -> master라는 branch에 있음

NO commits yet -> commit이 아직 없음

nothing to commit (create/copy files and use 'git add' to track) -> commit 할 것도 없음

```

#### `a.txt` 파일 생성 후

```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        a.txt
    -> commit 될 것에 포함 시키고 싶으면 git add <파일명>을 사용
nothing added to commit but untracked files present (use "git add" to track)
-> commit 할 것은 없는데, 추적되지 않은 파일은 있음( 추적하고 )
```

#### `git add a.txt` 입력 후
```
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt

```

### (3) `git add [파일/폴더]` 
  commit을 위한 stage  

### (4) `git commit -m "<메시지>"` 
  commit ==버전을 생성 == 현재의 스냅샷 촬영  

#### 최초 commit 시
```
Author identity unknown -> 작자 미상

*** Please tell me who you are. -> 너가 누군지 알려줘

Run -> 실행해봐

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity. -> 당신의 계정의 기본 신원을 설정하기 위해
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'dandy@DESKTOP-N1KGQOF.(none)')
```
### (5) `git config`: Git 관련 설정 ; 최초 1회만 실행
```
  git config --global user.email "you@example.com"  -> '당신의 이메일'
  git config --global user.name "Your Name" -> '당신의 이름'
```
- 수정도 같은 명령어를 사용
- 현재 이메일이나 이름을 확인하고 싶을 경우 "~"란을 생략
  
- cat ~/.gitconfig : 현재의 이름과 이메일 반환

### (6) `git log` : Commit 목록
  현재 까지의 commit 출력
```
commit 921cd27c621683ab1f402512d47cbf363a7230b2 (HEAD -> master)
Author: pakjy <pakjy47@gmail.com>
Date:   Tue Nov 28 16:51:39 2023 +0900

    First commit
```
`git log -oneline`: 한줄로 출력

#### 최종 commit
```
On branch master
nothing to commit, working tree(== directory) clean

```
## II. 백업 Git 명령어
### (7) `git remote` 
- 원격 저장소(Remote Repository)에 대한 정보
- `git remote add`:원격 저장소 추가
    - `git remote add [저장소] [저장소주소]`
    - `git remote add origin http://github.com/...`   

### (8) `git push` : 원격 저장소에 프로젝트 업로드
- `git push [저장소 이름] [브랜치 이름]`
- ``