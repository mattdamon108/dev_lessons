# Lesson #1
> React Native 시작하기 위한 사전작업

## Terminal CLI(Command Line Interface)에 익숙해지기

### Terminal 주요 명령어

1. mkdir : 디렉토리 생성 (MaKe DIRectory)

> projects 디렉토리 만들기
```shell
$ mkdir projects
```

2. cd : 디렉토리 이동 (Change Directory)

> `projects` 디렉토리로 이동
```shell
$ cd projects
```

3. pwd : 현재 내 위치 확인하기

```shell
$ pwd
```

4. rm -rf : 디렉토리 지우기 (ReMove)

> `myapp` 디렉토리 지우기
```shell
$ rm -rf myapp
```

5. mv : 파일 이동하기, 파일 이름 바꾸기

> `a.ts` 파일을 `/home/sungho` 디렉토리로 이동시키기
```shell
$ mv a.ts /usr/sungho
```

> `a.ts` 파일을 `b.ts`로 이름 바꾸기
```shell
$ mv a.ts b.ts
```

## Linux 파일 구조 이해하기

> 참고

* https://webdir.tistory.com/101


1. `~` : 유저의 홈 디렉토리
   * 성호의 홈 디렉토리는 `/home/sungho` 이고 줄여서 `~` 표현할 수 있음
   * `~/projects` 디렉토리처럼 홈 디렉토리에서 작업하는 것이 좋음

2. `/` : 루트(root) 디렉토리
   * 시스템 최상위 디렉토리

## React Native 앱 시작하기

1. 앱 개발을 시작하려고 하는 디렉토리로 이동

```shell
$ cd ~/projects
```

2. 앱 구성하기

> myapp 이라는 이름으로 구성하기
```shell
$ npx react-native init myapp --template react-native-template-typescript
```

3. 앱 실행하기

    * 앱 디렉토리로 이동하기
    
    ```shell
    $ cd myapp
    ```

    * 터미널을 하나 추가로 열고,

    ```shell
    $ npm run start
    ```

    * 원래 터미널에서,

    ```shell
    $ npm run android
    ```
    > 만약 에러가 나면, android 에뮬레이터(가상 기기)가 완전히 부팅되고 나서 다시 명령어 실행
