# Styled Component

> ๐ Styled Components๋ฅผ ์ ์ฌ์ฉํ๋๊ฐ ?
>
> ๋ฆฌ์กํธ Web ๊ณผ ๋ฆฌ์กํธ Native๋ ๋ฏธ์ธํ๊ฒ Style ์ค์ ์ด ๋ค๋ฅด๋ค.
>
> mui ๊ฐ์ ํ๋ ์ ์ํฌ๋ฅผ ์ฌ์ฉํ๋๋ผ๋ native ์ฉ์ ์๊ธฐ์ ๊ฐ๊ฐ ๋ค์ CSS๋ฅผ ์์ฑํด์ผ ํ๋ ๊ฒฝ์ฐ๊ฐ ์๋๋ฐ,
>
> Styled-Components ์ฌ์ฉ์ CSS ์ค์ ์ ๋ค์ ๋ฒ๊ฑฐ๋กญ์ง๋ง ํ๋ฒ ์์ฑํด๋์ผ๋ฉด WEB ๊ณผ App ๊ฐ์ ์ฐ๋์ด ๊ฐ๋ฅํ๋ค.

## ๊ธฐ๋ณธ ๋ฌธ๋ฒ

```jsx
import styled from "styled-components";

// ๊ธฐ๋ณธ ๋ธ๋์ ์คํ์ผ ์ฌ์ฉ
const StyledButton = styled.button`
  width: 120px;
  color: white;
  bacground-color: tomato;
`;

// ์คํ์ผ ๋ ๋ธ๋๋ฅผ ์์ํด์ ์ฌ์ฉ
const StyledSuccessButton = styled(StyledButton)`
  background-color: green;
`;
```

## ํ์ฅ ๊ธฐ๋ฅ

> ๋จ์ ์คํ์ผ ๋ฟ ์๋๋ผ ์ํ๋ณ ์คํ์ผ ๋ณ๊ฒฝ๋ ๊ฐ๋ฅํ๋ค

### props ์ฌ์ฉ

```jsx
import styled from "styled-components";

const LikeButton = styled.button`
  width: 100px;
  color: white;
  bgcolor: ${(props) => (props.isLike ? "green" : "red")};
`;

function Post() {
  const [isLike, setIsLike] = useState(false);
  return (
    <React.Fragment>
      ....Post
      <LikeButton isLike={isLike} onClick={() => setIsLike(!isLike)} />
    </React.Fragment>
  );
}
```

### ํ๊ทธ ๋ณ๊ฒฝ

> ์ปดํฌ๋ํธ์ ์คํ์ผ์ ๊ธฐ์กด ๊ทธ๋๋ก ์ ์งํ๋ ํ๊ทธ ์ด๋ฆ๋ง ๋ณ๊ฒฝํ๊ณ  ์ถ์ ๊ฒฝ์ฐ

```jsx
import styled from "styled-components";

const styledBtn = styled(Input).attr({
  as: "button",
})`
  margin-left: 10px;
`;
```
