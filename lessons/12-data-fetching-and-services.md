# 12. Service layer, data fetching và gọi API

## Những gì nhiều người thường quen ở framework full
- HttpClient chuẩn
- interceptor chuẩn
- service layer rất tự nhiên

## React thì không ép
Mày phải tự chọn cách fetch.

## Ví dụ service layer

```js
export async function getUsers() {
  const res = await fetch('/api/users');
  if (!res.ok) throw new Error('Failed to fetch users');
  return res.json();
}
```

## Dùng trong component

```jsx
import { useEffect, useState } from 'react';
import { getUsers } from './userService';

function UsersPage() {
  const [users, setUsers] = useState([]);
  const [error, setError] = useState(null);

  useEffect(() => {
    getUsers()
      .then(setUsers)
      .catch(setError);
  }, []);

  if (error) return <p>Error</p>;

  return <div>{users.length}</div>;
}
```

## Cách nghĩ đúng
- component không nên ôm mọi fetch logic
- nên có service layer hoặc query layer
- app lớn thì đừng fetch tay quá nhiều

## Kết luận
React không cho sẵn HttpClient hay data layer chuẩn, nên mày phải tự chọn cách fetch rõ ràng.
Muốn code sạch, mày phải tự tạo data access layer.