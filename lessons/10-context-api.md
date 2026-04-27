# 10. Context API dùng được tới đâu

Context dùng để share state cho nhiều component mà không phải prop drilling quá sâu.

## Ví dụ cơ bản

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

Dùng:

```jsx
function Profile() {
  const { user } = useAuth();
  return <div>{user?.name}</div>;
}
```

## Context hợp với gì
- auth state đơn giản
- theme
- config
- state dùng rộng nhưng không update quá dày

## Context không hợp với gì
- state update liên tục
- app lớn nhiều nghiệp vụ
- thay store thực thụ một cách mù quáng

## Kết luận
Context không phải Redux killer.
Nó chỉ là công cụ share state mức vừa phải.