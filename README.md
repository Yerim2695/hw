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
~~~~objective-js
Function Jungmin(name) {
   console.log(name)
}

Jungmin=(name) => {
   console.log(name)
}
~~~~
* * *

# 4. Array Methods (map, reduce, filter, slice, splice)
#### 내장 Method로 기능을 사용하자
** 참고 : https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array **
##### 1) Map - array의 각 요소에 반복적인 수행을 반복한다.
~~~~objective-js
const num =[1,2,3,4];
const number =num.map(x=>x/2);
~~~~

##### 2) Filter - array의 각 요소를 조건에 맞춰 필터링하여 새로운 array를 만든다. 
~~~~objective-js
const num =[1,2,3,4];
const number =num.filter(x=>x>2);
~~~~

##### 3) Reduce - array의 원소에 순서대로 동일한 연산을 취하여 하나의 축적된 결과를 얻어낼 수 있다.
Reduce의 Syntax는 arr.reduce(callback[, initialValue])이다.
+ callback은 accumulator, currentValue, currentIndex, array 순으로 4개의 매개변수로 구성이 된다.
+ accumulator: 축적자란 뜻으로 전 callback 함수의 return값을 가지고 있다. 즉 축적된 연산결과가 넘어온다는 말이다. 
만약 initialValue 인자를 넘겼다면 최초의 callback에서의 값은 initialValue가 될 것이고, 그렇지 않다면 arr의 첫 번째 원소가 될 것이다.
+ currentValue: 이번 callback에서 연산을 할 배열의 원소가 된다. 
만약 intialValue를 입력했다면  최초의 callback에서는 배열의 첫 번째 원소가 될 것이고, 아니라면 두 번재 원소가 넘어올 것이다.
+ currentIndex: currentValue의 index이다.
+ array: 이 메서드를 돌리는 배열 자체이다.

##### 4) Slice - array이나 문자열이나 index의 범위 안에서 잘라 반환한다.
~~~~objective-js
.slice('구분자') //구분자를 기준으로 나눈다.
.slice(앞인덱스, 뒤인덱스) //배열이나 문자열이나 index의 범위 안에서 잘라 반환해 줍니다.
~~~~

##### 5) splice - 원하는 위치의 요소를 추가하거나 잘라내는 것이 가능하다.
~~~~objective-js
.splice(시작점, 길이, 추가요소 n) 
const num=[1,2,3,4]
const number=num.splice(1,2,5)

number=[2,3,5]
~~~~
<br>
<br>

# 5. Export / Import
#### 모듈을 불러오고 내보내보자
##### 1) Named Export - 여러개를 동시에 내보낼 수 있다.
+ 내보내고나면 다른 곳에서 여러번 사용할 수 있다.
+ 변수 / 함수 / 객체 등 내보내려는 것의 정의 앞에 **export** 키워드를 붙여주면 된다.
+ export {대상}을 붙여줘야 한다.

##### 2) Default Export - 한 파일당 하나를 내보낼 수 있다.
+ 함수와 클래스만 내보낼 수 있다. 객체 불가능
+ Named와 달리 {}를 붙여줄 수 필요가 없다.

##### 3) Named Import - 여러개를 불러올 수 있다.
+ import {대상명 as 별칭} from 상대경로
+ as를 사용하여 별칭으로 불러올 수도 있다.

##### 5) Default Import - 하나를 불러온다.
+ 하나만 불러오기 때문에 아무 이름이나 적어줘도 된다.
<br>
<br>

# 6. Spread Operator (Array/Object Spread)


