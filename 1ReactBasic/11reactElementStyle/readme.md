리액트 Element에 스타일 입히기

- className : 문자열
- style : 객체, 카멜케이스, className보다 먼저

커스텀함수!
예를들어 Button 이라는 함수를 만든다

function Button({ className, color, ...rest }) {
return <button className={`button ${color}`} {...rest} />;
}

() 안에 받을 값 다 적어줘야 적용됨

const element = (
<>
<Button color="green">Green</Button>
<Button color="blue">Blue</Button>
<Button color="red">Red</Button>
<Button color="gray">Gray</Button>
<Button color="black">Black</Button>
</>
);

모든 <Button/>에 "button"이라는 className 부여할거니까 className 써주고,
각 Button에 입력한 'color'값을 받아서 클래스네임으로 적용시킬 것이기 때문에 color 도 받아야함

{...rest} 는 내가 입력하지 않은 이외의 것들 ex 칠드런 (버튼안에들어갈 text 값, 이라던지 개별적으로 입력된 style 값이 포함됨 그이외에 어떤 값들이 적용되는지는 검색해서 꼭 알아 볼 것.)

ㄴ style 적용하고싶으면
style={{ fontSize: "80px" }}
이런 양식으로.....
무조건 카멜케이스로 입력되어야하고, className보다 먼저 적용됨 (밑에 쓰였기때문인듯)
