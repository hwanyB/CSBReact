Ref로 Dom 다루기(useRef)
Ref 는 Reference 의 준말

돔을 다루는 Hook

document.getElementById("input").focus();
위 코드 대신

const inputRef = React.useRef();
React.useEffect(() => {
inputRef.current.focus();
}, []);

return (
<>
<input ref={inputRef} />
</>
);
이렇게 사용 가능

왜 리액트는 document.getElementById 등의 류를 사용하지 않고 useRef라는 별도의 방법(훅)을 사용할까??
: 리액트가 제공하는 일련의 룰같은 개념.
