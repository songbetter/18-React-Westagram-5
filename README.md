## 인스타그램 Clone 프로젝트 "Westagram"
* 프로젝트 기간: 2021.03.02~2021.03.12
* 기술스택: HTML, CSS, JavaScript(ES6+), React, SCSS
#### 구현사항
1. 인스타그램 로그인, 메인 페이지 레이아웃
2. 로그인 버튼 클릭 시 메인 페이지로 이동
3. 로그인 시 사용자 입력 데이터 저장
4. 로그인 ID/PW Validation
5. 로그인 인증 (API 통신)
6. 메인페이지 내 피드에서 댓글 입력 후 엔터 or 게시 클릭 시 댓글 추가
7. 메인페이지 내 피드 & 댓글 & 추천영역 데이터 렌더링

> 따라치는 코딩이 아닌, 개념 공부 후 이해한 내용을 바탕으로 기능을 구현했습니다.


![](https://images.velog.io/images/songbetter/post/f8012d06-d3ac-40a9-a86a-b469596085d3/ezgif.com-gif-maker%20(1).gif)![](https://images.velog.io/images/songbetter/post/ac614d5a-8f7e-4b17-954d-5fbaffced799/mockdata.gif)
## Login page
![](https://images.velog.io/images/songbetter/post/28514b7d-9d35-4330-9675-a1f8318e9354/image.png)
> #### 구현사항 1 로그인 버튼 클릭 시 메인 페이지로 이동
로그인 버튼에 `onClick` event 발생 시 goToMain 함수 실행.
1. Form태그의 Submit 기능을 제어하기 위해 `e.preventDefault()`를 먼저 실행.
2. 입력한 ID와 Password를 body에 담아 string으로 변환 후 API에 인증 요청.
3. 요청에 대한 응답을 받아 JSON형식으로 변환.
4. 인증이 되면 메인으로 이동하고 서버로부터 전달받은 token을 localStorage에 저장.
5. 인증에 실패하면 "아이디와 비밀번호를 확인해주세요" 팝업 생성.

> #### 구현사항 2 사용자 입력 데이터 저장
ID/PW Input 창에 `onChange` event 발생 시 handleInput 함수 실행.
1. event.target.value(Input창에 입력된 ID와 PW)를 state에 저장.

> #### 구현사항 3 Validation
ID에 @가 포함되고, PW가 5자 이상일 때 버튼 활성화.
1. ID/PW Input에 따라 변화하는 state값을 이용하여 유효성 검사 실행.
2. 조건에 부합할 경우 className 변경. 
3. .activeBtn과 .inactiveBtn의 css 효과를 다르게 주어 버튼 활성화 기능 구현.
ex) `.activeBtn{opacity: 1.0}; .inactiveBtn{opacity: 0,5}`

## Main Page 
### - Comment
![](https://images.velog.io/images/songbetter/post/e5045873-5aec-48e8-935a-82448ba86961/image.png)
> #### 구현사항 1 댓글 입력 후 엔터 or 게시 클릭 시 댓글 추가
1. Textarea에 `onChange` event 발생 시 handleCommentInput 함수 실행
: event.target.value(=comment)를 state에 저장.
2. 게시 버튼 `onClick` event 발생 혹은, textarea에 `onKeyPress` event 발생 시 addComment 함수 실행
: event.target.comment(Textarea에 입력된 Comment)를 state에 저장.
-> commentList에 comment추가 
-> comment state를 초기화.
3. map 함수를 이용하여 commentList에 저장된 데이터를 원하는 형태로 렌더링 (JSX활용)

### - Feed
![](https://images.velog.io/images/songbetter/post/fe80a99c-e41f-476f-bb39-082ae5f90c10/image.png)
> #### 구현사항 2 중복되는 UI 단순화 (데이터 렌더링)
Mock data를 만들어 데이터 통신을 하지 않아도 기능이 구현되는 것을 확인할 수 있음.
-> map 함수를 이용하여 저장된 데이터를 원하는 형태로 렌더링 (JSX활용)

> 블로그 바로가기
https://velog.io/@songbetter/Project-02-Westagram-by.React
