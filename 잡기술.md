1. 로딩 에니메이션
html
```html
  <div class="the-loader"></div>
```

```css
.the-loader {
  width: 30px;
  height: 30px;
  margin: 30px auto;
  border: 4px solid red;
  border-top-color: transparent;
  border-radius: 50%;
  animation: loader 1s infinite linear;
}
@keyframes loader {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
```

2. 스켈레톤 로딩 skeleton
```html
  <h1 class="skeleton"></h1>
  <h2 class="skeleton"></h2>
  <p>
    <div class="photo skeleton"></div>
    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Molestias dicta est culpa, voluptatum laudantium et temporibus, minus laborum illo natus ex, veritatis consequuntur fugiat repellat quo numquam nesciunt obcaecati nihil!
  </p>
```

```css
body {
  background-color: black;
  color:white;
}
h1.skeleton {
  width: 60%;
  height: 40px;
}
h2.skeleton {
  height: 30px;
}
.photo {
  width: 300px;
  height: 250px;
  borderL 4px solid;
  float: left;
  margin-right: 14px;
}

.skeleton {
  background-color: var(--color-area);
  position: relative;
  border-radius: 10px;
  overflow: hidden;
}
.skeleton::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: linear-gradient(270deg, 
    transparent, 
    rgba(255, 255, 255, 0.1), 
    transparent);
  animation: skeleton-loader 2s infinite;
  transform: translateX(-100%);
}
@keyframes skeleton-loader {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}
```
