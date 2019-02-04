# theme
- CSS 테마를 만들어 모든 컴포넌트에 적용
- theme.js 생성
```js
const theme = {
    mainColor: "#3498db",
    dangerColor: "#e74c3c",
    successColor: "#2ecc71",
}

export default theme;
```
- App.js에 적용
```js
import React, { Component } from 'react';
import styled, { createGlobalStyle, ThemeProvider } from "styled-components"
import theme from "./theme"

const GlobalStyle = createGlobalStyle `
    body{
        padding:0;
        margin:0;
    }
`;

const Card = styled.div`
    background-color: red;
`;

const Container = styled.div`
    height: 100vh;
    width: 100%;
    background-color: pink;
    ${Card} {
        background-color: blue;
    }
`;

const Button = styled.button`
    border-radius: 30px;
    padding: 25px 15px;
    background-color: ${props => props.theme.successColor}
`;

class App extends Component {
    render() {
        return (
        
        <ThemeProvider theme={theme}>
            <>
                <GlobalStyle/>
                <Container>
                    <Form />
                </Container>
            </>
        </ThemeProvider>
        
        );
    }
}

const Form = () => (<Card><Button>Hello</Button></Card>);

export default App;

```