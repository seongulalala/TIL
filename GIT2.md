# Today I Learned
`version `
`2025.6.05`

# 1. `.gitignore`
-   제외하고 싶은 파일은 반드시 `git add` 전에 `.gitinore`에 작성한다

# 2. `Clone, pull`
- 원격저장소에서 > 내 로컬 저장소로 가져 오는 것
## 1. `git clone`
-   `git clone <원격 저장소 주소>`
    ``` 
    $git clone https:// ~ 
    ```
- git clone을 통해 생성된 로컬 저장소는 `git init`와 `git add`가 이미 수행되어 있다

## 2. `git pull`
- 원격 저장소의 변경 사항을 가져와서, 로컬 저장소를 업데이트
- ` git pull <저장소 이름><브랜치 이름> `
  ```
  git pull origin master
  ```
## 3. 비교
-   git init = git clone
-   git push = git pull  

--- 
# 3. 두 가지 협업 방식
## 1. 원격 저장소 소유권 o
### 1. 개념
-   원격 저장소가 자신 것이거나, collaborator로 등록되어 있는 경우 가능
-   master에 직접 개발 x
-   기능별 브랜치를 만들어 개발
-   `PR`로 변경 내용에 대한 소통

### 2. 작업 흐름
  ```
  $ git clone 원격저장소주소

# 자신이 작업할 브랜치명 생성
  $ git switch -c 브랜치명

# 작업 후 해당 브랜치 push
$ git push origin 브랜치명

# PR로 자신의 브랜치를   master에 반영 요청

# 반영이 돼 병합되었다면 완료된 내용 다시 다운
$ git switch master
$ git pull origin master

# 필요없는 브랜치 삭제
$ git branch -d 브랜치명
```

## 2. 원격 저장소 소유권 x
### 1. 개념
- 원격 저장소를 그대로 두고
- 내 원격 저장소에 복제
- 내 원격 저장소에서 로컬 저장소로 이동
- 원격 저장소(원본)과 내 로컬 저장소 연결

### 2. 흐름
```
# 1. Fork를 통해 내 GitHub 계정에 원본 저장소 복제

# 2. 내 GitHub 원격 저장소 → 내 로컬로 복제
$ git clone <내 원격 저장소 주소>
$ cd <저장소 폴더명>

# 3. 원본 저장소 연결 (동기화용)
$ git remote add upstream <원본 저장소 주소>

# 4. 내 로컬에 새 브랜치 생성 후 기능 구현
$ git switch -c <브랜치명>
# 👉 코드 수정 작업 후

# 5. 변경사항 커밋
$ git add .
$ git commit -m "기능 또는 수정 내용 설명"

# 6. 내 원격 저장소에 푸시
$ git push origin <브랜치명>

# 7. GitHub 웹에서 원본 저장소로 PR 요청
#    - base: 원본 저장소의 master/main
#    - compare: 내 저장소의 브랜치

# 8. PR merge 완료 후 브랜치 정리
$ git switch master
$ git pull upstream master        # 최신 원본 반영
$ git branch -d <브랜치명>        # 로컬 브랜치 삭제
$ git push origin --delete <브랜치명>  # 원격 브랜치 삭제 (선택)