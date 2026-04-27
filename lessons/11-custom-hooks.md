# 11. Custom hooks để tái sử dụng logic

Đây là thứ React rất mạnh.

## Vì sao custom hook đáng học
Trong nhiều codebase lớn, mày hay reuse logic qua:
- service
- shared helper
- directive

Trong React, mày có thêm custom hook để tách logic khỏi UI.

## Ví dụ

```jsx
import { useEffect, useState } from 'react';

export function useWindowWidth() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    const onResize = () => setWidth(window.innerWidth);
    window.addEventListener('resize', onResize);
    return () => window.removeEventListener('resize', onResize);
  }, []);

  return width;
}
```

Dùng:

```jsx
function Layout() {
  const width = useWindowWidth();
  return <div>Width: {width}</div>;
}
```

## Ví dụ hook fetch đơn giản

```jsx
import { useEffect, useState } from 'react';

export function useUsers() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch('/api/users')
      .then(res => res.json())
      .then(setUsers);
  }, []);

  return users;
}
```

## Kết luận
Nếu có service mindset, thì khi học React nên có thêm hook mindset.