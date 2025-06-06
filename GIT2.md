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

