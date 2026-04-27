# 05. State management trong React cho người quen RxJS

## Angular dev quen gì
- service singleton
- BehaviorSubject
- Observable stream
- async pipe
- NgRx nếu app lớn

## React có gì tương đương
Không có một đáp án duy nhất.
Tùy độ lớn app mà chọn:
- local state với `useState`
- shared state với `Context`
- app lớn thì dùng `Zustand`, `Redux Toolkit`, `Jotai`, v.v.
- data fetching thì thường dùng `TanStack Query`

## Cách map tư duy

### Angular service + BehaviorSubject
Có thể gần giống với:
- custom hook + context
- hoặc Zustand store

## Ví dụ Context đơn giản

```jsx
import { createContext, useContext, useState } from 'react';

const AuthContext = createContext(null);

export function AuthProvider({ children }) {
  const [user, setUser] = useState(null);
  return (
    <AuthContext.Provider value={{ user, setUser }}>
      {children}
    </AuthContext.Provider>
  );
}

export function useAuth() {
  return useContext(AuthContext);
}
```

## Điều cần nhớ
React không ép mày dùng stream cho mọi thứ.
Nhiều lúc state thường + query lib là đủ.

## Chốt
Đừng bê nguyên tư duy RxJS vào React nếu không cần.
React mạnh ở composition, không mạnh ở built-in reactive stream.