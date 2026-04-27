# 04. useEffect và tư duy lifecycle

## Đây là chỗ Angular dev hay ngu nhất khi sang React
Vì React không bảo mày nghĩ theo lifecycle method cũ.
Nó bắt mày nghĩ theo:
- render
- dependency
- synchronization with external world

## useEffect cơ bản

```jsx
import { useEffect, useState } from 'react';

function UserPage() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch('/api/users')
      .then((res) => res.json())
      .then(setUsers);
  }, []);

  return <div>{users.length}</div>;
}
```

## So với Angular
- `useEffect(..., [])` gần giống `ngOnInit`, nhưng không hoàn toàn giống
- cleanup function gần giống `ngOnDestroy`

```jsx
useEffect(() => {
  const id = setInterval(() => console.log('tick'), 1000);
  return () => clearInterval(id);
}, []);
```

## Sai lầm phổ biến
- nhét mọi thứ vào `useEffect`
- không hiểu dependency array
- bị stale closure
- fetch loop vô hạn

## Chốt
`useEffect` không phải chỗ để nhét business logic bừa.
Nó chủ yếu để đồng bộ component với thế giới bên ngoài.