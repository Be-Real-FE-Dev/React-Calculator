# CalCulator
<br>
<div align="middle">
  <image src="./src/assets/calculator.svg"/>
</div>
<br>
<p align="middle">
  <img src="https://img.shields.io/badge/Version-1.0.0-red?style=flat-square" alt="template version"/>
  <img src="https://img.shields.io/badge/Library-React-blue.svg?style=flat-square"/>
  <img src="https://img.shields.io/badge/Style-StyledComponent-hotpink.svg?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-brightgreen.svg?style=flat-square"/>
</p>

<br>

## ๐ฏ ๊ธฐ๋ฅ ์๊ตฌ์ฌํญ

- 2๊ฐ์ ์ซ์์ ๋ํด ๋ง์์ด ๊ฐ๋ฅํ๋ค.
- 2๊ฐ์ ์ซ์์ ๋ํด ๋บ์์ด ๊ฐ๋ฅํ๋ค.
- 2๊ฐ์ ์ซ์์ ๋ํด ๊ณฑ์์ด ๊ฐ๋ฅํ๋ค.
- 2๊ฐ์ ์ซ์์ ๋ํด ๋๋์์ด ๊ฐ๋ฅํ๋ค.
- AC(All Clear)๋ฒํผ์ ๋๋ฅด๋ฉด 0์ผ๋ก ์ด๊ธฐํ ํ๋ค.
- ๊ณ์ฐ ๊ฒฐ๊ณผ๋ฅผ ํํํ  ๋ ์์์  ์ดํ๋ ๋ฒ๋ฆผํ๋ค.

<br>

## ๐ folder Architecture

- vite๋ฅผ ์ฌ์ฉํ์ฌ build
- UI : atomic components
- Calculator : ๊ณ์ฐ๊ธฐ UI๋ฅผ ๊ตฌ์ฑํ๋ components

```
  react-calculator
  โโโ public/
  โโโ src/
  โ   โโโ assets/
  โ   โโโ components/
  โ       โโโ Calculator/
  โ       โโโ UI/
  โโโ index.html
  โโโ package.json
  โโโ webpack.config.js
```

<br>

## ๐ ์๋ก ์๊ฒ๋ ๊ฒ

### 1. Styled Component

- view๋ง ๊ทธ๋ฆฌ๋ ์ปดํฌ๋ํธ๋ styledComponent ๋ฌธ๋ฒ์ผ๋ก๋ง ์ฌ์ฉํด๋ ๋ฌด๋ฐฉํ๋ค.
- component extending styles ํ๊ธฐ

  1. tagged template literals๋ฅผ ์ฌ์ฉํ์ฌ Button ์ปดํฌ๋ํธ ์์ฑ.
  2. ๊ธฐ์กด์ Button ์ปดํฌ๋ํธ์ ์คํ์ผ์ ์ถ๊ฐํ์ฌ ์ปดํฌ๋ํธ๋ฅผ ํ์ฅ ๊ฐ๋ฅ.

  ```js
  import styled from 'styled-components';

  const Button = styled.button`
    color: #131313;
    background-color: #151515;
  `;

  const ComposedButton = styled(Button)`
    color: #999999;
    ...
  `;
  ```

- component์ props ์ ์ฉํ๊ธฐ

  1. styled-component๋ ๊ธฐ๋ณธ์ ์ผ๋ก arguments๋ก props์ ๋ํ ์ ๋ณด๋ฅผ ๋ฐ๋๋ค.

  ```js
  // Button.js
  const Button = styled.button`
    /* Adapt the colors based on primary prop */
    background: ${(props) => (props.primary ? 'palevioletred' : 'white')};
  `;

  // App.js
  const App = () => {
    return <Button primary={true}>์ถ๊ฐ</Button>;
  };
  ```

  ๋จ์ : props๋ฅผ ๋ฐ์์ ์ฌ์ฉํ๋ฏ๋ก ์์ ์ปดํฌ๋ํธ๊ฐ ๋ถ๋ชจ ์ปดํฌ๋ํธ์ ์์กด์ ์ด๋ค. atomic ํ์ง ์๋ค.
<br>

## ๐ค ๊ณ ๋ฏผํ ๊ฒ

### state๋ฅผ ์ด๋ป๊ฒ ๋๋ ๊ฒ์ธ๊ฐ?
<br>
