#### Memoization
> 이미 계산해 본 연산 결과를 기억해두었다가 동일한 연산을 해야할 때 다시 연산하지 않고 기억해두었던 데이터를 반환시키는 방법.

#### useMemo
> 어떤 값을 리턴하는 어떤 함수에게 특정 값이 변화할 때만 리턴 연산을 수행할 것임을 명시해주고 싶을 때 사용 하는 것이 useMemo


- **얕은 비교 (Shallow Comparison)**
    - 객체나 배열을 비교할 때, 내부의 값 하나하나를 비교하는 것이 아니라 **메모리 주소(참조)가 같은지만 확인**
    - 원시 타입(string, number, boolean 등)은 값을 직접 비교
    - 리액트의 `React.memo`, `useMemo`, `useEffect`의 의존성 배열 등이 이 방식을 사용
        
- **깊은 비교 (Deep Comparison)**
    - 객체나 배열의 **내부 요소까지 재귀적으로 모두 순회하며 값이 같은지 확인**
    - 계산 비용이 매우 비싸기 때문에 리액트에서는 기본적으로 사용하지 않음

But 리액트는 컴포넌트가 언제 다시 렌더링될지 결정할 때 **얕은 비교**를 사용함

해결책: 불변성(Immutability) 유지

이 문제에 대한 리액트의 공식적인 해결책은 **'불변성'을 지키는 것** 
즉, 원본 데이터를 직접 수정하지 않고, **항상 새로운 객체나 배열을 생성**하여 상태를 업데이트 해아함

https://velog.io/@sujinjwa/useMemo%EC%99%80-React.memo%EA%B0%80-%EB%AC%B4%EC%97%87%EC%9D%B4%EA%B3%A0-%EC%9D%B4%EB%93%A4%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90%EC%9D%84-%EC%9D%B4%ED%95%B4%ED%95%B4%EB%B3%B4%EC%9E%90

https://ui.toast.com/weekly-pick/ko_20190731
