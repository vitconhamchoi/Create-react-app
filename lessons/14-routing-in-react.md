# 14. Routing trong React

## Router trong nhiều framework full
- router là first-class citizen
- guard, lazy loading, nested route khá rõ

## React
React không có router built-in.
Thường dùng `react-router-dom`.

## Ví dụ

```jsx
import { BrowserRouter, Routes, Route } from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="/users" element={<UsersPage />} />
      </Routes>
    </BrowserRouter>
  );
}
```

## Protected route

```jsx
import { Navigate } from 'react-router-dom';

function ProtectedRoute({ children }) {
  const isLoggedIn = true;
  return isLoggedIn ? children : <Navigate to="/login" />;
}
```

Dùng:

```jsx
<Route
  path="/dashboard"
  element={
    <ProtectedRoute>
      <DashboardPage />
    </ProtectedRoute>
  }
/>
```

## Kết luận
Routing trong React đủ mạnh để làm app thật, nhưng mày phải tự chọn và tổ chức rõ.