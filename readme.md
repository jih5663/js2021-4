#장인혁[201840131]


## [05월25일]
<br>

>오늘배운내용 요약
 <br>

 ※. express 모듈
 <br>-expreess모듈을 사용하는 방법을 이해합니다.
 <br>-요청과 응답
 <br>-express모듈을 사용한 서버생성과 실행
<br>-페이지라우팅
<br>-요청과 응답
<br>-미들웨어

<br>
<h3>＃express모듈 설치<h3>
//$npm install express@4<br>
<br>
요청하는 대상은 클라이언트<br>
응답하는 대상은 서버<br>
<br>
<br>
#response 객체
<br>
send()데이터 본문제공<br>
status()상태 코드를 제공
set()헤더를 설정합니다.
<br>
<br>
<h3>#상태코드<h3><br>
//모듈 추출합니다.
const express = require('express');
<br>
//서버생성<br>
const app = express();<br><br>
//request 이벤트 리스너를 설정<br><br>
//request 이벤트 리스너를 설정<br><br>
app.get('*',(request,response)=> {<br>response.status(404);<br>
response.send('해당경로에는 아무것도 없습니다.');});
<br><br>
//서버실행<br>
app.listen(522273, () => {<br>
    console.log('server running at http://127.0.0.1:52273');});<br><br>
#어려웠던 부분 : 미들웨어의 속성,<br>클라이언트-> 서버데이터 전송법
<br>
<br>

## [05월18일]
<br>

>오늘배운내용 요약
 <br>

 

 ※. Node.js
 <br>Node.js의 전역 변수
 <br>Node.js 문서를 보는 방법
 <br>Node.js 모듈의 동기 메소드를 이해하기
 <br>Node.js외부모듈
<br>템플릿엔진


<br>
<h3>전역 변수,전역함수,전역객체 : 모든 곳에서 사용할 수 있는 것들<h3><br>
//문자열 자료형의 전역 변수
<br>
__filename -> 현재 실행중인 코드의 파일 경로를 나타냅니다.<br>
__dimname -> 현재 실행중인 코드의 폴더 경로를 나타냅니다.<br>
//예제<br>
console.log(__filename);<br>
comsole.log(__dirname);<br>
<br>
Node.js는 process 전역 객체를 제공<br>
process 객체는 프로세스 정보를 제공하며, 제어할 수 있게 하는 객체
<br>
<br>
<h3>process 객체와 이벤트 개요<h3><br>
#Node.js의 이벤트 연결 메소드<br>
on(<이벤트 이름>, <이벤트 핸들러><br>
<br>
<h3>파일처리와 예외처리<h3>
<br>
@동기 코드 예외처리 : try catch구문
<br>
@비동기 코디 예외처리 : 콜백함수의 첫 번째 매개 변수 error를 활용
<br>

<br>
#어려웠던 부분 : File System 모듈여러 파일을 <br>
비동기적으로 읽기<br>
<br>
//모듈을 추출합니다.<br>
const fs = require('fs');
const async = require('async');
<br>
//병렬적으로 파일을 읽어 들입니다.
<br>
async.parallel([<br>
    (callback) => { fs.readFile('a.txt, callback);},<br>
    (callback) => { fs.readFile('a.txt, callback);},<br>
    (callback) => { fs.readFile('a.txt, callback);},<br>
    ], (error, results) => {<br>
    //출력합니다.<br>
    console.log(results);}
<br>
<br>
## [05월4일]
<br>

>오늘배운내용 요약
 <br>

 

 ※. 표준내용객체
 <br>기본자료형과 객체자료형의 차이점
 <br>Number 객체
 <br>String 객체
 <br>Date 객체
<br>Array 객체


<br>
<h3>＃Number 생성자함수의 속성<h3><br>
//변수를 선언합니다.
<br>
let numberA = Number.MAX_VALUE;<br>
let numberB = Number.MAX_VALUE + 1;<br>
//출력합니다<br>
console.log(numberA);<br>
comsole.log(numberB);<br>
<br>
1을 추가해도 결국 출력되는 값이 같다는 점<br>
<br>
<br>
<h3>＃String 객체 생성<h3><br>
let stringFromLiteral = '안녕하세요';<br>
let stringFromConstructor = new String('안녕하세요');<br>
<br>
<h3>※String 객체의 메소드는 변경된 값을 리턴한다.<h3>
<br>
#어려웠던 부분 : Date객체에서의 시간간격 구하기
<br>
<br>

## [04월26일]
<br>

>오늘배운내용 요약
 <br>

 

 ※. 객체
 <br>객체와 반복문
 <br>속성과 메소드
 <br>객체기본
 <br>생성자 함수와 프로토타입
<br>기억에 남는 부분 
<br> =  생성자함수

#생성자 함수
<br>
 function Product(name, price) <br>{
     this.name = name;<br>
     this.price = price;
 }

<br>
#프로토타입에 메소드 선언
Product.prototype.print = function() {<br>
    console.log('${product.name}의 가격은 ${product.price}원입니다.');<br>

};
<br>
<br>
#메소드 호출<br>
product.print();
<br>
<br>
#어려웠던 부분 : null을 활용해서 '아예값이 없는 상태'를 구분하는 것
<br>
<br>

## [04월13일]
<br>

>오늘배운내용 요약
 <br>

 

 ※. 함수
 <br>함수의 기본형태 이해
 <br>함수 생성 방법
 <br>함수의 기본활용 형태
 <br>함수 매게 변수 초기화
 <br>콜백 함수
<br>기억에 남는 부분 
<br> = 함수의 기본형태 
Fuction <함수이름> (<매게 변수>){<함수코드>return<리턴 값>}

<br>
#어려웠던 부분 : 콜백 함수
<br>
<br>




## [04월06일]
<br>

>오늘배운내용 요약
 <br>

 

 ※. 반복문
 <br>while반복문과 for반복문
 <br>for반복문 + 역for반복문
 <br>중첩 반복문
 <br>break 키워드
 <br>continue 키워드
    <br>기억에 남는 부분 
<br> = 반복문으로 별피라미드 만들기

<br>
#어려웠던 부분 : switch조건문
<br>
<br>



## [03월30일]
<br>

>오늘배운내용 요약
 <br>

 

 ※. 조건문
 <br>조건문과 조건문+논리연산자
 <br>if 조건문
 <br>중첩 조건문
 <br>switch 조건문
 <br>삼항 연산자
    <br>기억에 남는 부분 
<br> = switch조건문의 기본형태


<br>
#어려웠던 부분 : switch조건문


## [03월23일]
<br>

>오늘배운내용 요약
 <br>
 

 ※. 자바스크립트의 기초
 <br>출력메소드, 연산자, 논리연산자들의 기초
 <br>＃식별자사용규칙
 <br>1.키워드를 사용하면 안 된다.
 <br>2.특수문자는 _그리고$만 된다.
 <br>3.숫자로 시작하면 안 된다.
 <br>4.공백은 입력하면 안 된다.

#어려웠던 부분 : 변수,연산


## [03월16일]
<br>

>오늘배운내용 요약
<br>

※. 자바스크립트는 웹서버개발,모바일어플리케이션 개발, 데스크톱 어플리케이션 개발,게임개발 등 많은 것이 가능하다.
<br>
＃해야할 것 ->실습환경 구축하기



