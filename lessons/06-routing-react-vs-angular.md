# 06. Routing trong React vs Angular Router

## Angular
- router là first-class citizen
- nested route, guard, lazy loading khá rõ

## React
React không có router built-in.
Thường dùng `react-router-dom`.

## Ví dụ cơ bản

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

## Guard kiểu React
Không có guard built-in đẹp như Angular.
Thường làm kiểu wrapper component.

```jsx
function ProtectedRoute({ children }) {
  const isLoggedIn = true;
  return isLoggedIn ? children : <Navigate to="/login" />;
}
```

## Chốt
Routing ở React dùng được, nhưng Angular router vẫn đầy đủ và đồng bộ hơn.