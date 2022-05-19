# 02.TypeScript-Setup
박성범 02. 개발환경 설정방법

# TypeScript 설치방법

<aside> 💡 TypeScript를 설치하기 위해서 먼저 Node.js를 설치해 주어야 합니다. Node.js의 기능인 npm이라는 라이브러리를 통하여 TypeScript를 설치해 줄 수 있습니다.

</aside>

## 1. Node.JS 설치하기



아래 Node.js 홈페이지에 들어가신 후, 다운로드를 받습니다.

[Node.js](https://nodejs.org/en/)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6617a5d0-f32a-4b9a-9231-91033650933c/Untitled.png)

우측 초록색 버튼(Latest Features)을 클릭하여 가장 최신 버전을 다운로드 받으시면 됩니다.

설치창에서 나오는 모든 항목은 그대로 두시고 다음을 눌러 다운로드를 완료하시면 Node.js 설치가 완료됩니다.

## 2. npm으로 TypeScript 설치하기

----------

### 2.1 npm이란?

----------

<aside> 💡 여기서는 npm을 **TypeScript를 사용하는데 필요한 도구**정도로 기억하시면 됩니다.

</aside>

npm은 세계에서 가장 규모가 큰 라이브러리 / 패키지 관리자 / 설치 프로그램 입니다.

npm은 무료이며 많은 오픈소스들이 npm을 통하여 공유되고 있습니다. 따라서 Node.js만 설치하시면 따로 다운로드 받거나, 로그인 할 필요없이 바로 사용하실 수 있습니다.

![ ](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d0a9e2dc-2906-4909-aefc-2276e33c5c35/Untitled.png)

### 2.2 설치방법

----------

Visual Studio Code의 터미널 창에 아래 문구를 작성 후 엔터를 누르시면, TypeScript가 설치됩니다.

`npm install -g typescript`



# TypeScript 파일 생성하기

<aside> 💁 처음 TypeScript 파일이 생성되는지 테스트를 하며 다양한 문제에 부딪힐 수 있습니다. 아래의 내용을 통해 문제를 하나하나 해결해 나가 봅시다!

</aside>

## 1. TypeScript파일 생성하기


1.  TypeScript **파일생성**

Visual Studio Code에서 새 파일을 열어 app.ts 명으로 TypeScript 파일 만들기

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5822944c-aad7-40f8-977c-d5f91b77bf46/Untitled.png)

1.  **TypeScript 파일을 JavaScript 파일로 컴파일하기**

터미널을 열어준 후, `tsc app.ts` 명령어를 입력하시면 컴파일이 됩니다.

<aside> ❓ Q. tsc란 어떤 명령어 인가요? A. tsc는 typescript compiler라는 의미입니다. 즉 타입스크립트(.ts) 파일을 자바스크립트(.js) 파일로 변환(컴파일) 해 줍니다.

</aside>

<aside> ❓ Q. tsc란 어떤 명령어 인가요? A. tsc는 typescript compiler라는 의미입니다. 즉 타입스크립트(.ts) 파일을 자바스크립트(.js) 파일로 변환(컴파일) 해 줍니다.

</aside>

<aside> ❓ Q. 왜 TypeScript 파일을 JavaScript 파일로 컴파일 해줘야 하나요? A. 브라우저는 TypeScript 파일을 읽을 수 없습니다. 따라서 반드시 브라우저가 읽을 수 있는 JavaScript 파일로 컴파일 해주어야 합니다. Sass파일을 CSS파일로 컴파일하는것과 비슷한 개념이라고 생각하시면 됩니다.

</aside>

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/97e85664-6442-4ce9-b41f-d9ad34dc57e1/Untitled.png)

`tsc app.ts` 을 입력하면 app.js 파일이 생성됩니다.

만약 에러가 발생한 다면 아래를 참고하세요.

[에러1. about_Execution_Policies](https://www.notion.so/1-about_Execution_Policies-256c105500294b449ca019757021ceb1)

[에러1. about_Execution_Policies (1)](https://www.notion.so/1-about_Execution_Policies-1-ea81fb081ac54fe19456db2b82feca70)

[에러2. File 'app.ts' not found.](https://www.notion.so/2-File-app-ts-not-found-435f63e8ad4a4453806006a11db9bd46)

[에러3. Error: 중복된 함수 구현](https://www.notion.so/3-Error-82898b3ffd964b38a8f7e62ad87fc9ec)

1.  **컴파일 된 JavaScript 파일의 실행결과 확인하기**

터미널 창에 `node app.js` 를 입력하시면 스크립트의 실행된 결과가 터미널창 좌측 하단에 나타납니다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bdae86ba-6f1a-44eb-9b4e-b1ef96c305cf/Untitled.png)

만약 에러가 발생한 다면 아래를 참고하세요.

[에러4. cannot find module](https://www.notion.so/4-cannot-find-module-5c508f7501c34579859fc831bed865c6)

1.  **자동 컴파일 설정하기**

앞에서 `tsc` 명령어를 이용하여 TypeScript 파일을 JavaScript파일로 변환하는 방법을 배웠습니다. 하지만 매번 명령어를 입력하는 것은 매우 귀찮은 일입니다. 그래서 이 과정을 자동화 시켜주는 방법이 있습니다. 바로 `tsc -w` 또는 `tsc --w` 명령어 입니다. 여기서 w는 watch의 뜻으로, 계속 보고있다는 의미입니다.

`“tsc -w 파일경로”` 를 입력하시면 해당 파일을 저장할 때마다 자동으로 컴파일을 해줍니다.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d1e09181-e112-44e8-b317-52463d4f3a26/Untitled.png)
