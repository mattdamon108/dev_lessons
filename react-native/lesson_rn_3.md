# Lesson #3

## 변수와 state

### 변수(variable)와 상수(constant)

변수란 말그대로 변할 수 있는 값이라는 의미야. 그에 반해 상수는 늘 같은 값을 가지는 녀석이지.

변수는 이렇게 선언해서 사용할 수 있어.

```js
const myName = "성호";

let weight = 30;
```

`const`는 한 번 선언하면 나중에 바꿀 수 없는 값을 선언할 때 붙이는 type이고, `let`은 한 번 선언하고나서도 나중에 값을 변경할 수 있는 변수를 선언할 때 사용해.

즉, myName은 한 번 선언하면 늘 `"성호"`라는 문자열(string)을 갖는 상수이고, weight는 `30`이라는 숫자(number)로 선언된 변수야.

나중에 weight값을 바꿀 수 있어.

```js
const myName = "성호";

let weight = 30;

weight = 35;
```

`const`나 `let`으로 한 번 선언한 상수와 변수의 이름은 바꿀 수 없어. 다른 이름으로 새로 선언하고 사용해야하거나, weight처럼 let으로 변수로 선언한 변수는 나중에 35를 대입하듯이 값을 변경할 수 있어.

그렇다면, state는 뭘까?

state는 영어 단어 의미 그대로 상태를 말해. state는 React Native에서만 사용할 수 있는 약속된 값이야. state는 React Native에서 사용하는 상태를 나타내는 상수인데, 이 상수인 state의 값을 변경할 수 있는 짝꿍 함수가 늘 존재해.

만약, 아래와 같이 선언하면,

```js
const [height, setHeight] = useState(110);
```

저기 선언한 height는 110이라는 값으로 선언한 state이고, 상수의 성격을 가져. 프로그램의 다른 곳에서 사용할 수 있고, 만약 그 값을 바꾸고 싶으면,

```js
const [ height, setHeight ] = useState(110)

...

setHeight(120)

// 이제 height는 120이 되었어.
```

state와 const/let으로 선언한 값들과는 어떤 차이가 있을까?

```js
const App = () => {
  const [height, setHeight] = useState(110);

  const changeHeight = () => {
    setHeight(120);
  };

  return (
    <View>
      <Text>내 키는 {height}</Text>
      <Button title="커져라 키" onPress={changeHeight} />
    </View>
  );
};
```

이렇게 만들어서 앱을 실행하고 나면, `내 키는 110`이라고 표시되고, 아래 `커져라 키`라는 버튼이 하나 있을거야. 이 버튼을 누르면 `내 키는 120`이라고 변하는 걸 볼 수 있을거야.

이렇게 App같은 컴포넌트 함수안에서 성호가 버튼 같은 컴포넌트로 어떤 액션을 만들어서 변화를 주고 그 변화를 앱에 표시해주고 싶을 때는 state를 사용해야해.

만약 그냥 `let`을 사용해서 한다면, 그 변화가 앱에 표시되지 않을거야.

```js
const App = () => {
  let height = 110;

  const changeHeight = () => {
    height = 120;
  };

  return (
    <View>
      <Text>내 키는 {height}</Text>
      <Button title="커져라 키" onPress={changeHeight} />
    </View>
  );
};
```

> 값이 변하지 않음

사실 이건, React Native를 만든 개발자들이 그렇게 사용해달라고 약속하고 만들어준 것이라서, 어쩔 수 없이 그것에 따라 사용을 해야해. 마치 우리가 전제제품을 샀을 때 제품에 붙어있는 버튼들을 사용해야 하는 것과 비슷해.

## 연습하기

1. `내 이름은 성호`라는 글을 화면 중앙에 표시하고, `내 별명은`이라는 버튼을 누르면 `내 별명은 천재`라는 화면을 만들어보기
