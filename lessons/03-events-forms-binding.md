# 03. Event, form, two-way binding khác gì Angular

## Angular quen gì
- `(click)`
- `[(ngModel)]`
- reactive forms khá mạnh

## React khác gì
React không có two-way binding built-in kiểu Angular.
Mày thường dùng controlled component.

```jsx
import { useState } from 'react';

function LoginForm() {
  const [email, setEmail] = useState('');

  return (
    <input
      value={email}
      onChange={(e) => setEmail(e.target.value)}
    />
  );
}
```

## Ý nghĩa
Trong React:
- UI lấy giá trị từ state
- event cập nhật lại state
- state lại render ra UI

## Angular dev hay khó chịu ở điểm này
- thấy verbose hơn Angular
- cảm giác React không hỗ trợ form tốt bằng Angular

Điều đó đúng một phần.
Form trong React muốn ngon thường phải dùng thêm lib như:
- react-hook-form
- zod/yup

## Chốt
Angular form built-in ngon hơn.
React form thường phải tự ghép tool, nhưng bù lại linh hoạt hơn.