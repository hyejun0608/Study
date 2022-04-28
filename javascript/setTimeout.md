# setTimeout & setInterval
> 호출 스케줄링 scheduling a call  
> 일정 시간이 지난 후에 원하는 함수를 예약 실행(호출) 할 수 있게 하는 것

## setTimeout
> 일정시간이 지난 후에 함수를 실행하는 방법
```
let timerId = setTimeout(function/code, [delay], [arg1], [arg2], ...);
```
## 예시
```
function sayHello() {
    console.log('Hello!);
}

setTimeout(sayHello, 1000); //Hello!
```
## 주의
```
// 잘못된 코드
setTimeout(sayHello(), 1000); //undefined
```
## setInterval
> 일정 시간 간격을 두고 함수를 실행하는 방법  
> `setTimeout`은 함수를 단 한번만 실행하지만 `setInterval`는 함수를 주기적으로 실행하게 한다
```
let timerId = setInterval(function/code, [delay], [arg1], [arg2], ...);
```
## 예시
```
let timerId = setInterval(()=> console.log('tiktok'), 2000);
console.log(timerId);
// 6초 후에 정지
setTimeout(()=> { clearInterval(timerId); console.log('tik);}, 6000);
console.log(timerId);
```