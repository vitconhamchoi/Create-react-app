# 16. React thiếu gì so với Angular và phải tự bù gì

## Angular mạnh ở chỗ gì
- framework full
- convention rõ
- forms mạnh
- DI mạnh
- router mạnh
- HttpClient chuẩn

## React không cho sẵn
- DI chuẩn
- form solution chuẩn
- state solution chuẩn
- data fetching solution chuẩn
- project structure chuẩn

## React app nghiêm túc thường phải tự ghép stack
Ví dụ:
- React
- React Router
- TanStack Query
- react-hook-form
- Zod
- Zustand/Redux nếu cần

## Ví dụ một App provider root

```jsx
<QueryClientProvider client={queryClient}>
  <BrowserRouter>
    <App />
  </BrowserRouter>
</QueryClientProvider>
```

Tức là nhiều thứ Angular làm hộ, React bắt mày tự gắn.

## Kết luận
React mạnh vì linh hoạt.
Nhưng linh hoạt luôn đi kèm rủi ro loạn kiến trúc nếu team yếu.