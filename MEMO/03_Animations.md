
# Animation
- keyframes 활용
```js
import React, { Component } from 'react';
import styled, {css, keyframes } from "styled-components"

class App extends Component {
    render() {
        return (
        <Container>
            <Button success>Hello</Button>
            <Button danger rotationtime = {5}>Hello</Button>           
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

    ${props => {
        if(props.danger){
            return css`animation: ${rotation} ${props.rotationtime}s linear infinite`;
        }
    }}
`;

const rotation = keyframes`
    from{
        transform: rotate(0deg);
    }
    to{
        transform: rotate(360deg);
    }
`;
export default App;
```