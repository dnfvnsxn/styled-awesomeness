# Extra Attributes and Mixins
## tag의 attributes를 사용하는 방법

```js
const Input = styled.input.attrs({
    required: true
})`
    border-radius: 5px;
`;
```

## mixin
- CSS그룹을 만들어 여러곳에서 사용
- 2가지 방법이 존재
    - 다른 컴포넌트를 쓰고 확장
    - mixin을 사용
    ```js
    import styled, { css } from "styled-components"

    const awesomeCard = css`
    box-shadow: 0 4px 6px rgba(50, 50, 93, 0.11), 0 1px 3px rgba(0, 0, 0, 0.08);
    background-color: white;
    border-radius: 10px;
    padding: 20px;
    `;
    ``
- awesomeCard는 단지 CSS block
- Input에 활용
```js
const Input = styled.input.attrs({
    required: true
})`
    border: none;
    ${awesomeCard};
`;
```