# 19. Làm mini app React nếu mày từng code Angular

Cách học nhanh nhất là làm lại một app đơn giản từng làm bằng Angular.

## Đề xuất mini project
### User management app
Chức năng:
- login giả lập
- protected route
- user list
- create user form
- search/filter user
- detail page

## Tech stack đề xuất
- React
- TypeScript
- Vite
- React Router
- TanStack Query
- react-hook-form
- Zod

## Gợi ý structure

```text
src/
  features/
    auth/
    users/
  app/
  shared/
```

## Ví dụ route

```jsx
<Routes>
  <Route path="/login" element={<LoginPage />} />
  <Route path="/users" element={<UsersPage />} />
  <Route path="/users/:id" element={<UserDetailPage />} />
</Routes>
```

## Mục tiêu của bài mini project
- tập state
- tập form
- tập routing
- tập query
- tập structure

## Kết luận
Code một app nhỏ còn giúp mày hiểu React hơn đọc thêm 20 bài lý thuyết.