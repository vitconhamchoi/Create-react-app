# 02. Component, JSX, props, state

## So sánh nhanh

### Angular
- component = class + template + decorator
- binding rõ ràng hơn

### React
- component thường là function
- UI được mô tả bằng JSX
- props là input
- state là dữ liệu nội bộ

## Ví dụ React cơ bản

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

## State trong React

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

## Điều Angular dev hay bị lệch
- tưởng `setState` đổi xong là có ngay giá trị mới như imperative code
- không để ý component render lại khi state đổi
- không để ý object reference làm re-render khó đoán

## Chốt
Trong React, component là hàm render theo state hiện tại.
Đừng nghĩ theo kiểu class lifecycle cũ trước đã.