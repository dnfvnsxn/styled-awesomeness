# Styled Components
- SASS코드를 SASS 설치 없이 사용
- CSS파일 없이 CSS 코드를 작성
- 코드를 리액트 네이트브 앱으로 공유
- 코드의 재활용
- CSS파일 생성, 클래스명 생성등의 번거로움이 없음
- 웹팩을 사용하지 않음
- SASS의 variable, mixins등을 사용가능
- 미디어 쿼리를 리액트 네이티브에서 사용가능

## 과거의 방식
- App.css
```css
.button{
    border-radius: 50px;
    padding: 5px;
    min-width: 120px;
    color: white;
    font-weight: 600;
    -webkit-appearance: none;
    cursor: pointer;
}

.button:active,
.button:focus{
    outline: none;
}

.button--success{
    background-color: #2ecc71;
}

.button--danger{
    background-color: #e74c3c;
}
```
- 방법1
- App.js
```js
import React, { Component, Fragment } from 'react';
import "./App.css"

class App extends Component {
    render() {
        return (
        <Fragment>
            <button className="button button--success">hello</button>
            <button className="button button--danger">hello</button>
        </Fragment>
        );
    }
}

export default App;

```
- 방법2
- App.js
```js
import React, { Component, Fragment } from 'react';
import "./App.css"

class App extends Component {
    render() {
        return (
        <Fragment>
            <Button danger />
            <Button />
        </Fragment>
        );
    }
}

const Button = ({danger}) => (
    <button className={ danger ? "button button--danger" : "button button--success"}>hello</button>
)

export default App;
```

## styled component 생성
- 컴포넌트가 이미 스타일을 가지고 있는 것
- js안에 css가 위치
- 버튼 생성 예시
- 스타일링을 하려는 HTML 요소를 사용
```js
import React, { Component } from 'react';
import styled from "styled-components"

class App extends Component {
    render() {
        return (
        <Container>
            <Button success/>
            <Button danger />
        </Container>
        );
    }
}

const Container = styled.div`
    height: 100vh;
    width: 100%;
    background-color: pink;
`;

const Button = styled.button`
    border-radius: 50px;
    padding: 5px;
    min-width: 120px;
    color: white;
    font-weight: 600;
    -webkit-appearance: none;
    cursor: pointer;

    &:active,
    &:focus{
        outline: none;
    }
    background-color: ${props => props.danger? "#e74c3c" : "#2ecc71"}
`;
export default App;
```
- 이전이라면 두개의 컴포넌트, 하나이상의 파일과 다른 클래스명이 필요 했지만 모두 사라졌음

