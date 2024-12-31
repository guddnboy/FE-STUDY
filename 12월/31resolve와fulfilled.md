# resolve와 fulfilled의 차이에 대해서 설명해주세요.

`resolve`는 `Promise`를 성공적으로 마무리 짓는 행위라고 볼 수 있고, `fulfilled`는 그 결과로 발생하는 완료된 상태를 의미합니다. 즉, `resolve`가 호출되어야 비로소 `fulfilled` 상태가 됩니다.

## Promise 객체에서 resolve란 무엇인가요?

`resolve` 함수는 `Promise`가 성공적으로 처리가 되었을 경우에 결과값을 전달하는 함수입니다. `resolve`를 통해서 "이 작업이 끝났고, 결과값은 이거다." 라고 전달합니다. 이렇게 `resolve`가 호출되면 Promise의 상태는 '이행됨'으로 변경되고 `fulfilled`라고 부릅니다.

> 예를 들어, `new Promise((resolve, reject) => { resolve('완료'); })`처럼 `resolve` 메서드를 호출하면, 이 `Promise`의 상태는 `fulfilled`로 변경됩니다. 이처럼 `resolve`는 `fulfilled` 상태로 전환시키는 역할을 합니다.

## Promise 객체에서 fulfilled는 무엇인가요?

`fulfilled`는 `Promise`가 **완료된 상태**를 의미합니다.
