# 08. Conditional rendering, list rendering, key

## Conditional rendering

```jsx
function UserStatus({ isLoggedIn }) {
  return isLoggedIn ? <p>Welcome back</p> : <p>Please login</p>;
}
```

## List rendering

```jsx
function UserList({ users }) {
  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

## Vì sao key quan trọng
React dùng `key` để nhận diện item trong list.
Nếu dùng key ngu, UI có thể update sai.

### Sai

```jsx
{users.map((user, index) => (
  <li key={index}>{user.name}</li>
))}
```

Nếu list reorder hoặc delete, key theo index dễ gây bug.

### Đúng hơn

```jsx
{users.map(user => (
  <li key={user.id}>{user.name}</li>
))}
```

## So với cách test quen thuộc ở framework khác
Một số framework có syntax loop trong template, còn React dùng JS thuần `map`.
Đó là lý do mày phải chắc JS array methods.

## Kết luận
List rendering trong React đơn giản nhưng phải hiểu `key` cho đúng, không là bug rất ngu.