# Lesson #2

## 함수(Function)와 React Native의 컴포넌트(Component)

### 함수에 대해

함수(Function)는 어떤 입력값을 계산하고 처리하는 한 단위의 코드 덩어리야.

함수는 보통 이렇게 생겼어. arg1이라는 숫자 입력값을 받아서 2를 곱한 뒤에 반환하는 함수를 표현해볼께.

- 일반 함수

```javascript
function twoTimes(arg1: number) {
  const result = arg1 * 2;

  return result;
}
```

- Arrow(화살표) 함수

```javascript
const twoTimes = (arg1: number) => {
  const result = arg1 * 2;

  return result;
};
```

두 함수 모두 실행을 해보면 결과는 똑같아. 함수를 선언하는 표현 방식만 다를 뿐이야. 사실 둘의 차이는 있는데, 나중에 좀 더 뒤에 알려줄께.

함수를 저렇게 만들면 함수가 선언(Declaration)됐다고 말해. 그런데 선언되었다고 해서 실행이 되는 건 아냐. 실행은 어떻게 하냐면,

- 함수의 호출(= 실행)

```javascript
twoTimes(1);
```

arg1의 자리에 1이라는 숫자를 입력해서 `twoTimes`라는 함수를 호출(=실행)하는 표현이야.

이 둘을 합해 보면,

```javascript
const twoTimes = (arg1: number) => {
  const result = arg1 * 2;

  return result;
};

const value = twoTimes(1);

console.log(value);
```

### **연습하기**

1. ~/projects 디렉토리에 `twoTimes`라는 디렉토리를 만들고, 그 디렉토리로 이동

2. VSC(= Visual Studio Code)를 실행해서 `twoTimes.ts`라는 파일을 만들고, `twoTimes`함수를 선언하고 호출하는 코드를 작성한다.

3. 터미널에서 아래와 같이 실행해본다.

```shell
$ node twoTimes.ts
```

4. 결과는?

## 함수와 React Native 컴포넌트의 관계는?

React Native의 컴포넌트들은 모두 함수야. View, Text, Button같은 컴포넌트들이 앱의 화면에서 공간을 만들고(View), 글자를 표시해주고(Text), 버튼을 생성해주는(Button) 함수들이야.

그래서, App.tsx를 보면 함수처럼 생긴 걸 알 수 있을 거야.

```js
const App = () => {
  // 코드들...

  return <View>...</View>;
};
```

결국 React Native는 App이라는 함수를 실행해서 화면을 구성하고 작동하게 하는 것이지.

그리고 View도 결국 함수고, View 안에 있는 Text나 Button들도 함수인거야.

그럼, Text컴포넌트의 onChangeText 같은 건 뭘까?

onChangeText는 Text라는 컴포넌트 함수의 입력값이야. `twoTimes`함수의 예에서 arg1같은 녀석이지.

이걸 대충 표현해본다면 이렇게 될거야.

```js
const Text = (onChangeText) => {
    ...

    return ...
}
```

실제로는 저것 보단 훨씬 복잡하지만, 함수와 컨포넌트를 이해해기 위해 간단히 표현해본거야.

자 그렇다면, View, Text, Button처럼 `react-native`에서 제공하는 이미 만들어진 컴포넌트 말고 우리가 직접 함수를 이용해서 만들 수 있지 않을까?

### **연습하기**

1. MyName이라는 컴포넌트를 함수를 이용해서 만들어보자.

```js
const MyName = () => {
  return <Text>성호</Text>;
};
```

2. 이 컴포넌트를 앱 안에서 사용해보자.

```js
const App = () => {
    ...

    return (<>
        <ScrollView>
            ...
            <MyName />
            ...
        </ScrollView>
    </>)
}

const MyName = () => {
    return <Text>성호</Text>
}
```

3. 컴포넌트에 입력값을 받는 함수로 만들어보자.

```js
const App = () => {
    ...

    return (<>
        <ScrollView>
            ...
            <MyName name="성호" />
            ...
        </ScrollView>
    </>)
}

const MyName = ({ name } : { name: string }) => {
    return <Text>{name}</Text>
}
```

다음엔 변수와 state에 대해서 알아보자. 함수(= 컴포넌트), 변수(= state)를 기본적으로 잘 이해하면 나머진 금방 할 수 있을거야. 조금 어려워도 연습해보고 이해하려고 하면 나중에 쉬워질거야. 모르는 것 있으면 언제든 물어봐.
