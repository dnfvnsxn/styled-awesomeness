# createGlobalStyle
- createGlobalStyle 활용
```js
import { createGlobalStyle } from "styled-components"

const GlobalStyle = createGlobalStyle `
    body{
        padding:0;
        margin:0;
    }

`;
class App extends Component {
    render() {
        return (
            <>
                <GlobalStyle/>
                <Container>
                <Button success>Hello</Button>
                <Button danger >Hello</Button>
                </Container>
            </>
        );
    }
}
```
## 컴포넌트 스타일 재활용
- Button의 tag를 변경하고 스타일링을 추가
```js
const Anchor = styled(Button.withComponent("a"))`
    text-decoration:none;
`;
```