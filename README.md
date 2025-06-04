# Today I Learned
`version `
`2025.6.04`

* 하루동안 학습한 내용을 기록으로 남기면 확실히 복습도 되고 좋을 것 같다
  
# 1. CLI
-   CLI(command Line Interface)란 터미널을 통해 사용자와 컴퓨터가 상호작용하는 것, 쉽게 말해 `컴퓨터랑 직접 소통하는 것`이다
-   Poweshell과 명령 프롬프트도 CLI이지만 우리는 오늘 `Git Bash`란 CLI을 배웠다
  
## 터미널 명령어
### 1. touch
-   파일을 생성하는 명령어
``` bash
$ touch text.txt
```

### 2. mkdir
- 폴더를 생성하는 명령어

```bash
$ mkdir TIL
```
### 3. ls
-   현재 작업중인 디렉토리의 폴더/파일 목록을 보여주는 명령어

```bash
$ls
# all : 숨긴 파일까지 모두 보여줌
$ls -a
# long : 자세히 보여줌
$ls -a -l
```
### 4. mv
-   폴터/파일을 이동하거나 , 이름을 변경하는 명령어
-   이동할 때는 작성한 폴더명이 있어야 함, 없으면 이름이 수정

```bash
# 이동
$ mv text.txt folder
# 변경
$ mv text1.txt text2.txt
```

### 5. cd
-   현재 작업중인 디렉토리를 변경하는 명령어
```bash
# 현재 작업 중인 디렉토리에 있는 folder 폴더로 이동
$ cd folder
# 절대 경로를 통한 디렉토리 변경
$ cd C:/Users/이성우/Desktop
```
`cd~` : 홈 디렉토리로 이동  
`cd ..` : 부모 디렉토리로 이동  
`cd -` : 바로 전 디렉토리로 이동  

### 6. rm
- 폴더/파일을 지우는 명령어
- `-r` : 폴더를 지울 때 사용
```bash
$ rm test.text
$ rm -r folder
```

### 7. start
- 폴더/파일을 여는 명령어
```bash
$ start folder
```
# 2. VScode
-   Vscode란 MS에서 개발한 코드 에디터

# 3. 마크 다운
- 간단한 문서 작성 언어

## 주요문법
### 1. 제목
    # 제목1
    ## 제목2
    ###### 제목6
### 2. 목록
    * 
### 3. 강조
    1. 기울임 *글자*
    2. 강조 **글자**
    3. 취소 ~~글자~~
### 4. 코드
    1. 인라인 : ` 코드 `
    2. 블록 :

         ```언어이름
         코드
         ```
### 5. 링크
    [표시할 글자](이동할 주소)
### 6. 이미지
    ![대체 텍스트](이미지 주소)
### 7. 인용
    > 인용문을 작성합니다
### 8. 표
    | 동물 | 종류 | 다리 개수|
    | ---- | ---- | ------- |
    | 사자 | 포유류 | 4개 |

* 헤더 셀을 구문할 때는 3개 이상의 하이픈(-)이 필요
  
### 9. 수평선
    -를 3번 이상 연속 입력
    ex) ---


# 4. Git 기초
## 1. Git 기본 명령어
### 1. git init
- 현재 작업 중인 디렉토리를 Git으로 관리한다는 명령어
- 터미널에 `(master)`라고 표기됨

- Git 저장소인 폴더 내 init를 사용하지 않는다!!!
- = **터미널에 이미 `master`가 있다면 절대 git init를 입력하면 안 됨**

### 2. git status
-   파일의 현재 상태를 알려주는 명령어
-   
### 3. git add
-   파일을 2번째 공간(Staging Area)로 올리는 명령어
  
  ```bash
  $ git add a.txt
  $ git add folder
  ```

### 4. git commit
-  Staging Area에 올라온 파일을 하나의 버전(커밋)으로 저장하는 명령어
```bash
$ git commit -m "first commit"
```

### 5. git log
```
$ git log --online
```
# 5. Gitbub
- 코드를 저장하는 클라우드라고 생각하면 됨
= **원격저장소**

## 1. git remote
### 1. 등록
` git remote add <이름> <주소>`
```
$ git remote add origin https:...

[풀이]
remote(원격 저장소)에 add(추가) 한다.  
origin이라는 이름으로 <주소>의 내용을 불러온다
```

### 2. 조회
`git remote -v`
```
$ git remote -v
origin  https://github.com/edukyle/TIL.git (fetch)
origin  https://github.com/edukyle/TIL.git (push)

add를 이용해 추가했던 원격 저장소의 이름과 주소가 출력된다
```

### 3. 삭제
`git remote rm origin`
```
원격 저장소와의 연결 끊기
```

## 2. 원격 저장소에 업로드
### 1. 로컬 저장소에서 커밋 생성
```
# 현재 상태 확인
$ git status
```

### 2. 원격 저장소에 업로드
`git push <저장소 이름><브랜치 이름>`
```
$ git push origin master
```