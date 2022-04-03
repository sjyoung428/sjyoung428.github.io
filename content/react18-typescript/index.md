---
emoji: 🧢
title: React18을 typescript로 시작하기
date: '2022-04-03 20:00:00'
author: 성준영
tags: tutorial
categories: 리액트
---

## 1. 이 글을 쓰게 된 이유

ReactDOM.render는 React 18에서 지원되지 않습니다. 대신 createRoot를 사용합니다.
새로운 API로 전환할 때까지 앱이 React 17을 실행하는 것처럼 동작합니다.

Learn more: <https://reactjs.org/link/switch-to-createroot>

<br>

며칠전에 리액트18 이 정식으로 릴리즈 되었는데 추가로 설정해줘야 할 것들이 있어서
이 글을 쓰게 되었습니다.

## 2. index.tsx 설정하기

ReactDOM.render가 더 이상 사용되지 않기 때문에 createRoot를 사용해야 합니다.

```javascript
import { createRoot } from 'react-dom/client';
const rootElement = document.getElementById('root');
if (!rootElement) throw new Error('Failed to find the root element');
const root = createRoot(rootElement);
```

typescript를 사용 하지 않는 경우

```javascript
if (!rootElement) throw new Error('Failed to find the root element');
```

이 부분을 작성하지 않아도 되는것 같습니다.

## 3. tsconfig.json 설정

tsconfing.json 파일안에 아래 옵션을 추가하면 됩니다.

```json
"compilerOptions": {
      "types": ["react/next", "react-dom/next"]
}
```

이제 리액트18 버전을 사용할 수 있습니다.
