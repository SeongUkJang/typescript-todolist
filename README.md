# 초기세팅

### TypeScript와 React를 이용한 Todo-List 프로젝트 초기 세팅 정리

---

## 1. **React 프로젝트 생성**

```bash
npx create-react-app .

```

---

## 2. **불필요한 파일 삭제**

![image.png](attachment:393d1cba-87b9-4a22-897e-937e442b3db7:image.png)

![image.png](attachment:f209890b-59e0-4eea-8baa-48309f2dc904:image.png)

다음 파일들을 삭제하여 프로젝트를 간소화합니다.

- `App.test.js`
- `logo.svg`
- `reportWebVitals.js`
- `setupTest.js`

---

## 3. **React 초기 세팅**

**main.js:**

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```

**App.js:**

```jsx
import './App.css';

function App() {
  return (
    <div className="App">
      {/* 내용 작성 예정 */}
    </div>
  );
}

export default App;

```

---

## 4. **TypeScript 설정**

TypeScript 관련 의존성을 설치합니다.

```bash
npm i @types/node @types/react @types/react-dom @types/jest

```

```json
{
  "name": "section7",
  "version": "0.1.0",
  "private": true,
  "main": "src/index.tsx",
  "type": "module",
  "dependencies": {
    "@testing-library/dom": "^10.4.0",
    "@testing-library/jest-dom": "^6.6.3",
    "@testing-library/react": "^16.3.0",
    "@testing-library/user-event": "^13.5.0",
    "@types/jest": "^29.5.14",
    "@types/node": "^22.14.1",
    "@types/react": "^19.1.2",
    "@types/react-dom": "^19.1.2",
    "react": "^19.1.0",
    "react-dom": "^19.1.0",
    "react-scripts": "5.0.1",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}

```

---

## 5. **`tsconfig.json` 파일 설정**

**초기 설정:**

```json
{
  "compilerOptions": {
    "target": "ES5",
    "module": "CommonJS",
    "strict": true,
    "allowJs": true,
    "esModuleInterop": true,
    "jsx": "react-jsx"
  },
  "include": ["src"]
}

```

**추가 설정**: JSX 및 모듈 호환성을 위해 아래 내용을 추가합니다.

---

## 6. **JS 파일을 TS로 변경**

1. 파일 확장자를 `.js`에서 `.tsx`로 변경:
    - `App.jsx` → `App.tsx`
    - `index.jsx` → `index.tsx`
2. TypeScript 타입 지정:
**index.tsx:**

```tsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root') as HTMLElement);
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```

---

## 7. **오류 해결**

- JSX 사용 오류 시:
    
    ![image.png](attachment:326cd49c-462a-47cc-938c-1f554faa6526:image.png)
    
    ```json
    "jsx": "react-jsx"
    
    ```
    
- `HTMLElement | null` 오류 시:
    
    ```tsx
    const root = ReactDOM.createRoot(document.getElementById('root') as HTMLElement);
    
    ```
    

---

프로젝트가 성공적으로 TypeScript 기반으로 초기화되었습니다. 이제 Todo-List 개발을 시작할 준비가 되었습니다! 🎉

[App.tsx](https://www.notion.so/App-tsx-1dd7268828ce804cb12cdc3d2654303b?pvs=21)

[Header.tsx](https://www.notion.so/Header-tsx-1dd7268828ce801ba8bbcb45fe000457?pvs=21)

[TodoEditor.tsx](https://www.notion.so/TodoEditor-tsx-1dd7268828ce802fa62af17f0209e5d0?pvs=21)

[TodoList.tsx](https://www.notion.so/TodoList-tsx-1de7268828ce80f5b948ea3fcf901cde?pvs=21)

[TodoItem.tsx](https://www.notion.so/TodoItem-tsx-1de7268828ce8034be96e3b3ce61a669?pvs=21)

[Build](https://www.notion.so/Build-1de7268828ce80d7b6efd3c4b04f97dc?pvs=21)
