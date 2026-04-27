# 08. Reuse logic với custom hooks

## Đây là chỗ React rất mạnh
Trong Angular, mày hay reuse logic bằng:
- service
- directive
- shared helper

Trong React, mày có thêm custom hook.

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

```jsx
function Page() {
  const width = useWindowWidth();
  return <div>Width: {width}</div>;
}
```

## Ý nghĩa
Custom hook giúp:
- tách logic khỏi UI
- reuse dễ
- giữ component gọn hơn

## Chốt
Nếu Angular dev có service mindset, thì React dev nên có thêm hook mindset.