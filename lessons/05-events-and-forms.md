# 05. Event handling và form trong React

## Những gì nhiều người thường quen ở framework full
- `(click)`
- `[(ngModel)]`
- reactive forms rất mạnh

## React khác gì
React không có two-way binding built-in.
Mày thường viết controlled component.

## Ví dụ input cơ bản

```jsx
import { useState } from 'react';

function LoginForm() {
  const [email, setEmail] = useState('');

  return (
    <input
      value={email}
      onChange={(e) => setEmail(e.target.value)}
      placeholder="Enter email"
    />
  );
}
```

## Ví dụ form submit

```jsx
import { useState } from 'react';

function LoginForm() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log({ email, password });
  };

  return (
    <form onSubmit={handleSubmit}>
      <input value={email} onChange={(e) => setEmail(e.target.value)} />
      <input type="password" value={password} onChange={(e) => setPassword(e.target.value)} />
      <button type="submit">Login</button>
    </form>
  );
}
```

## So với two-way binding quen thuộc
### Cách nghĩ kiểu framework full

```html
<input [(ngModel)]="email" />
```

### React

```jsx
<input value={email} onChange={(e) => setEmail(e.target.value)} />
```

## Kết luận thật lòng
- form built-in của nhiều framework full thường mạnh hơn React
- React form dùng tay thì verbose hơn
- app nghiêm túc nên dùng `react-hook-form`

## Chốt
React không mạnh ở form built-in.
Muốn code form đỡ ngu phải chọn lib đúng.