# 03. Component, JSX, props, state

## Cách nhìn React cho người đã quen framework full

### Cách nghĩ kiểu framework full
- component = class + template + decorator
- input/output rõ bằng decorator

### React
- component thường là function
- JSX là cách mô tả UI
- props là input
- state là dữ liệu nội bộ

## Ví dụ component cơ bản

```jsx
function UserCard({ name, age }) {
  return (
    <div>
      <h3>{name}</h3>
      <p>{age}</p>
    </div>
  );
}
```

Dùng:

```jsx
<UserCard name="Viet" age={28} />
```

## State cơ bản

```jsx
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
}
```

## So sánh input kiểu decorator với React props

### Cách nghĩ kiểu framework full

```ts
@Input() title!: string;
```

### React

```jsx
function Header({ title }) {
  return <h1>{title}</h1>;
}
```

## Sai lầm phổ biến
### 1. Sửa state trực tiếp

```jsx
// sai
user.name = 'New Name';
setUser(user);
```

### 2. Đúng

```jsx
setUser({ ...user, name: 'New Name' });
```

## Kết luận
Trong React:
- props là dữ liệu đi vào
- state là dữ liệu component tự giữ
- UI luôn là kết quả render từ state hiện tại