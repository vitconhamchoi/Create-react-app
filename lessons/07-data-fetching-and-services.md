# 07. Data fetching, service layer, API calling

## Angular quen gì
- HttpClient chuẩn
- interceptor chuẩn
- service layer rất tự nhiên

## React thì sao
React không ép mày cách fetch data.
Có mấy hướng phổ biến:
- fetch/axios + `useEffect`
- custom service layer
- TanStack Query để lo cache, loading, retry

## Ví dụ service layer

```js
export async function getUsers() {
  const res = await fetch('/api/users');
  if (!res.ok) throw new Error('Failed');
  return res.json();
}
```

```jsx
import { useEffect, useState } from 'react';
import { getUsers } from './userService';

function UsersPage() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    getUsers().then(setUsers);
  }, []);

  return <div>{users.length}</div>;
}
```

## Nếu app nghiêm túc
Tốt hơn nên dùng TanStack Query vì nó xử lý:
- loading
- cache
- refetch
- error
- stale data

## Chốt
Angular cho sẵn HttpClient ngon.
React muốn code sạch thì mày nên tự tạo service layer và query strategy rõ ràng.