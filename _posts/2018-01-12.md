# var, let, const 차이점
### var - function-scoped
var는 함수가 범위이므로 for 문에서 초기값으로 선언하였더라도 밖에 서 사용할 수 있다. 이건 var가 hoisting 되었기 때문이다.

```
예)
for(var i=0;i<10;i+){}
console.log(i)
```

### let, const - block-scoped
var와의 차이점은 모두 변수를 재선언이 불가능하다. 여기서 차이점은 let는 재할당이 가능하지만 const는 재할당이 불가능하다.

```
let a = '123'
a = '234' (가능)

const b = '123'
b = '23' (X) 

```

또, const는 선언과 동시에 값을 할당해야 한다.



