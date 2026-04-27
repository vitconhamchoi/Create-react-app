# 06. useEffect, lifecycle và side effects

## useEffect để làm gì
Nó dùng để đồng bộ component với thế giới bên ngoài:
- gọi API
- subscribe event
- setInterval
- thao tác DOM ngoài React

## Ví dụ fetch data

```jsx
import { useEffect, useState } from 'react';

function UsersPage() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch('/api/users')
      .then(res => res.json())
      .then(setUsers);
  }, []);

  return <div>{users.length}</div>;
}
```

## Ví dụ cleanup

```jsx
useEffect(() => {
  const id = setInterval(() => console.log('tick'), 1000);
  return () => clearInterval(id);
}, []);
```

## So với cách test quen thuộc ở framework khác
- `useEffect(..., [])` gần giống `ngOnInit`
- cleanup gần giống `ngOnDestroy`
- nhưng React vẫn nghĩ theo render/dependency, không phải method lifecycle cũ

## Ví dụ bug phổ biến: dependency sai

```jsx
useEffect(() => {
  fetch(`/api/users?keyword=${keyword}`)
    .then(res => res.json())
    .then(setUsers);
}, []); // sai vì keyword đổi nhưng effect không chạy lại
```

Đúng:

```jsx
useEffect(() => {
  fetch(`/api/users?keyword=${keyword}`)
    .then(res => res.json())
    .then(setUsers);
}, [keyword]);
```

## Kết luận
Nếu coi `useEffect` như chỗ nhét mọi logic thì rất dễ toang.
Nó chỉ nên dùng cho side effects.