# 프로젝트 시작

### 1. 프로젝트 시작
npm init -y 

파슬 번들러 설치
npm i -D parcel 

### 2.  package.json 파일 변경
  ```js
    "scripts": {
      "dev": "parcel ./index.html",
      "build": "parcel build  ./index.html"    
    },
  ```

### 3. reset.css cdn 설치
구글에서 reset.css cdn 검색해서 jsdelivr 사이트 들어가서 가져오기. 

**중국에서 jsdelivr 사이트 들어가는지 체크 필요 안되면 직접 로컬 서버에 설치해서 사용**

``` html
https://cdn.jsdelivr.net/npm/reset-css@5.0.2/reset.min.css
```

### 4. 중국 html 기본 세팅
``` html
  <!DOCTYPE html>
  <html lang="zh-Hans">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Movie App</title>
    <!-- <link rel="icon" href=""> -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.2/reset.min.css"> 
    <link rel="stylesheet" href="./src/main.css">
    <script type="module" defer src="./src/main.js"></script>
  </head>
  <body>
    <div id="root"></div>
  </body>
  </html>
```

### 5. 개발 중 체크
npm run dev 
에러 뜨면 하나씩 수정하고
ctrl + c 로 npm 종료

### 6. git hub 최초 배포
git hub > Repositories > New 를 눌러 저장소 생성 

Repository name : 적기 > 공개 혹은 비공개 선택 하고 생성 > Quick setup 주소 복사하기

비주얼 스튜디오로 돌아오기

## 6-1.gitignore 파일 만들기
.parcel-cache, dist 폴더, node-modules 들은 업로드 할 필요가 없다.

gitignore 파일에 업로드가 필요 없는 파일 적기
```
parcel-cache
dist/
node_modules
.DS_Store
.vscode
.env
*.log

```

### 6-2 git 에 배포 ###

``` turminal
git init   // 초기화
git add .  // 현재 위치 추가

// 추가를 잘못 했을 경우 리셋후 다시 추가 하면 된다
git reset

    //파일을 잘못 올렸을 경우 로컬에서 삭제후 다시 push 하면 된다.
    rm -r 잘못올린 파일, 폴더
    git add . // 모두 올리기 스테이징에.
    git add path/to/파일.xx // 파일 하나만 올리기

git status  // 올릴 파일 한번 체크해 보기
git commit -m "메시지 적기" 생략해도 된다.

git remote add origin "github에서 복사한 주소 붙여 넣기:"
git remote add origin https://~~~
git push origin main  // main 브랜치로 업로드,
    // git branch -m master main (마스터 브랜치를 main으로 이름 변경하는 방법. 이름 안 바꿔도 된다.)
    // 이름 바꿀거면 바꾼 후에 push 하면 된다.

```

## 7 vercel 이용하기

npm i -D vercel // 패키지 설치

package.json 열고 

"vercel": "vercel dev" 라고 스크립트에 적어 준다.

  ```js

    "scripts": {
      "dev": "parcel ./index.html",
      "build": "parcel build ./index.html",
      "vercel": "vercel dev"  
    },

  ```

./ package.json 자리에 vercel.json 파일도 만들어 준다.

``` vercel
{
  "devCommand": "npm run dev",
  "buildCommand": "npm run build"
}
```
서버리스 함수를 이용해서 api 카를 감출 수 있다.

npm run vercel 로 테스트 해 본다.






















