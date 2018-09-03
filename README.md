# 1. Promises
### 코드의 순서를 조정할 수 있다!
##### 예를 들어
> componentDidMount(){

   console.log(fetch('https://yts.ag/api/v2/list_movies.json?sort_by=rating'))

   console.log('hello')

 }
