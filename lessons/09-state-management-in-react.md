# 09. State management cho người quen RxJS

## Những gì nhiều người từng quen
- service singleton
- BehaviorSubject
- Observable
- async pipe
- NgRx nếu app lớn

## React không có một đường duy nhất
Mày có thể dùng:
- `useState`
- `useReducer`
- `Context`
- Zustand
- Redux Toolkit
- TanStack Query cho server state

## Ví dụ local state

```jsx
function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

## Ví dụ dùng useReducer

```jsx
import { useReducer } from 'react';

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    default:
      return state;
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });
  return <button onClick={() => dispatch({ type: 'increment' })}>{state.count}</button>;
}
```

## Mapping tư duy từ framework có stream mạnh
- service + BehaviorSubject gần giống global store nhỏ
- React không bắt mày dùng stream cho mọi thứ
- nhiều khi state thường + query lib là đủ

## Kết luận
Đừng bê RxJS vào React chỉ vì quen tay.
React mạnh ở composition hơn là built-in reactive stream.