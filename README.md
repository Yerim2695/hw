# 1. Promises
#### 코드의 실행 순서를 조정해 보자
~~~~objective-js
componentDidMount() {  
   console.log(fetch(url))  
   console.log('hello')  
}
~~~~
  
코드를 실행할 때에 위에서부터 아래로 읽어내리게 되는데, 이것을 동기(Synchronous)라고 한다.  
실행이 순서대로 되므로, line1의 실행이 완료되지 않으면 line2의 실행은 불가능하다.  
이런 것의 불편함을 해결하기 위헤 Promises를 사용한다. 그렇게 되면 line1이 실행되든말든 line2를 실행할 수 있다.  
Promises를 잘 사용하면 작업의 스케줄을 지정해놓을 수 있다.  
<br>
<br>
* * *
# 2. Const / Let
#### 변동 가능성의 유무를 보자
변동 가능한 변수는 Let, 변동 불가능한 변수는 Const로 지정한다.  
값을 복사하는 경우 변하면 안되는 변수들에 대해서는 Const를 사용해서 코드의 혼란을 줄이는 것이 바람직하다.  
<br>
<br>
* * *
# 3. Arrow Functions
#### 함수의 표현을 간단히 하자
Function의 다른 표현이다.  
+ Function 키워드 대신 =>를 사용한다.  
+ 인자 값이 하나인 경우는 ()를 생략할 수 있다.  
+ 코드도 하나인 경우는 return도 생략할 수 있다.  
+ this를 사용할 경우는 {} 안에서만 사용할 수 있다.  
<br>
<br>
* * *
# 4. Array Methods (map, reduce, filter, slice, splice)
#### 내장 Method로 기능을 사용하자
** 참고 : https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array **
##### 1) Map - array의 각 요소에 반복적인 


