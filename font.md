# 1. 폰트 파일 준비
먼저, 사용할 폰트 파일을 다운로드하여 로컬 서버에 저장해야 합니다. <br>
폰트 파일의 형식으로는 일반적으로 .ttf, .otf, .woff, .woff2 등이 있습니다.<br>

# 2. 폰트 파일 로컬 서버에 업로드
로컬 서버에 접근하여 원하는 폰트 파일을 웹사이트의 폴더 구조에 맞게 업로드합니다. <br>
예를 들어, 프로젝트 폴더 내에 fonts 폴더를 만들어 그 안에 폰트 파일을 저장할 수 있습니다.<br>

  ```
  /your-project-directory
      /fonts
          /Roboto
              Roboto-Thin.ttf
              Roboto-Regular.ttf
              Roboto-Bold.ttf
              Roboto-Italic.ttf
              Roboto-BoldItalic.ttf
  ```
# 3. CSS 파일 수정
CSS 파일에서 @font-face 규칙을 사용하여 업로드한 폰트를 정의합니다. 아래는 예시입니다. <br>
불러올 폰트가 많다면 하나하나 다 불러와야 한다. <br>
  ```css
    @font-face {
        font-family: "Roboto";
        src: url('/fonts/Roboto/Roboto-Thin.ttf') format('truetype');
        font-weight: 100;  //- 100 thin 
        font-style: normal;
    }
    
    @font-face {
        font-family: "Roboto";
        src: url('/fonts/Roboto/Roboto-Regular.ttf') format('truetype');
        font-weight: 400;  // - 400 regular
        font-style: normal;
    }
    
    @font-face {
        font-family: "Roboto";
        src: url('/fonts/Roboto/Roboto-Bold.ttf') format('truetype');
        font-weight: 700; // - 700 bold
        font-style: normal;
    }
    
    @font-face {
        font-family: "Roboto";
        src: url('/fonts/Roboto/Roboto-Italic.ttf') format('truetype');
        font-weight: 400;
        font-style: italic; // - 이태릭
    }
    
    @font-face {
        font-family: "Roboto";
        src: url('/fonts/Roboto/Roboto-BoldItalic.ttf') format('truetype');
        font-weight: 700;
        font-style: italic; // - 이태릭
    }
    
h1 {
  font-weight: 700; /* 강조 폰트 굵기 설정 */
}
p {
  font-weight: 400; /* 일반 폰트 굵기 설정 */
}
em {
  font-style: italic; /* 이탤릭체 설정 */
}
body {
    font-family: "Roboto", sans-serif;
}

h1 {
    font-weight: 700;
}

p {
    font-weight: 400;
}

em {
    font-style: italic;
}
html {
  --color-black: #0e111b;
  --color-white: #fff;
  --color-white-50: rgba(255, 255, 255, 0.5);
  --color-white-30: rgba(255, 255, 255, 0.3);
  --color-white-20: rgba(255, 255, 255, 0.2);
  --color-white-10: rgba(255, 255, 255, 0.1);
  --color-white-5: rgba(255, 255, 255, 0.05);
  --color-primary: #fdc000;  
  --color-hover: #f86a05;
  --color-area: #1c212e;

}
body {
  background-color: var(--color-black);
  font-family: "Roboto", sans-serif;  
  line-height: 1.4;
  color: var(--color-white);
}

  ```
# 4. HTML 파일에서 폰트 사용
CSS 파일을 HTML 파일에 링크하고, 필요한 곳에서 정의한 폰트를 사용합니다.<br>
```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Custom Font Example</title>
      <link rel="stylesheet" href="styles.css">
  </head>
  <body>
      <h1>이것은 커스텀 폰트를 사용하는 예제입니다</h1>
      <p>여기에 본문 텍스트가 들어갑니다.</p>
  </body>
  </html>
````
추가 팁
폰트 파일을 여러 형식으로 제공하는 것이 좋습니다. 이는 브라우저 호환성을 높이기 위함입니다. <br>
font-display 속성을 사용하여 폰트 로딩 중에 대체 텍스트가 표시되는 방법을 제어할 수 있습니다. <br>
예를 들어, font-display: swap;을 사용하면 폰트가 로드될 때까지 시스템 폰트를 사용하고, 로드되면 교체됩니다.<br>

이런 식으로 하면 로컬 서버에서 폰트를 다운로드하여 웹사이트에서 사용할 수 있습니다.

# 5.폰트 숫자의 의미
100: Thin <br>
200: Extra Light (Ultra Light) <br>
300: Light <br>
400: Normal (Regular) <br>
500: Medium <br>
600: Semi Bold (Demi Bold) <br>
700: Bold <br>
800: Extra Bold (Ultra Bold) <br>
900: Black (Heavy) <br>


 
