---
emoji: ๐งข
title: React18์ typescript๋ก ์์ํ๊ธฐ
date: '2022-04-03 20:00:00'
author: ์ฑ์ค์
tags: tutorial
categories: ๋ฆฌ์กํธ
---

## 1. ์ด ๊ธ์ ์ฐ๊ฒ ๋ ์ด์ 

ReactDOM.render๋ React 18์์ ์ง์๋์ง ์์ต๋๋ค. ๋์  createRoot๋ฅผ ์ฌ์ฉํฉ๋๋ค.
์๋ก์ด API๋ก ์ ํํ  ๋๊น์ง ์ฑ์ด React 17์ ์คํํ๋ ๊ฒ์ฒ๋ผ ๋์ํฉ๋๋ค.

Learn more: <https://reactjs.org/link/switch-to-createroot>

<br>

๋ฉฐ์น ์ ์ ๋ฆฌ์กํธ18 ์ด ์ ์์ผ๋ก ๋ฆด๋ฆฌ์ฆ ๋์๋๋ฐ ์ถ๊ฐ๋ก ์ค์ ํด์ค์ผ ํ  ๊ฒ๋ค์ด ์์ด์
์ด ๊ธ์ ์ฐ๊ฒ ๋์์ต๋๋ค.

## 2. index.tsx ์ค์ ํ๊ธฐ

ReactDOM.render๊ฐ ๋ ์ด์ ์ฌ์ฉ๋์ง ์๊ธฐ ๋๋ฌธ์ createRoot๋ฅผ ์ฌ์ฉํด์ผ ํฉ๋๋ค.

```javascript
import { createRoot } from 'react-dom/client';
const rootElement = document.getElementById('root');
if (!rootElement) throw new Error('Failed to find the root element');
const root = createRoot(rootElement);
```

typescript๋ฅผ ์ฌ์ฉ ํ์ง ์๋ ๊ฒฝ์ฐ

```javascript
if (!rootElement) throw new Error('Failed to find the root element');
```

์ด ๋ถ๋ถ์ ์์ฑํ์ง ์์๋ ๋๋๊ฒ ๊ฐ์ต๋๋ค.

## 3. tsconfig.json ์ค์ 

tsconfing.json ํ์ผ์์ ์๋ ์ต์์ ์ถ๊ฐํ๋ฉด ๋ฉ๋๋ค.

```json
"compilerOptions": {
      "types": ["react/next", "react-dom/next"]
}
```

์ด์  ๋ฆฌ์กํธ18 ๋ฒ์ ์ ์ฌ์ฉํ  ์ ์์ต๋๋ค.
