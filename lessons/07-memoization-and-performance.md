# 07. useMemo, useCallback, memo và tối ưu re-render

React không tự tối ưu hết cho mày.
Nếu component tree lớn, mày phải biết khi nào nên memo.

## React.memo

```jsx
const UserRow = React.memo(function UserRow({ user }) {
  console.log('render user row', user.name);
  return <div>{user.name}</div>;
});
```

## Vấn đề reference mới mỗi render

```jsx
function Parent() {
  const user = { name: 'Viet' };
  return <UserRow user={user} />;
}
```

`user` là object mới mỗi lần render, nên memo không giúp gì nhiều.

## useMemo

```jsx
function Parent() {
  const user = useMemo(() => ({ name: 'Viet' }), []);
  return <UserRow user={user} />;
}
```

## useCallback

```jsx
function Parent() {
  const handleClick = useCallback(() => {
    console.log('clicked');
  }, []);

  return <Child onClick={handleClick} />;
}
```

## Khi nào nên dùng
- prop truyền xuống child là object/function
- child được memo
- render tree lớn
- có issue performance thật

## Khi nào không nên lạm dụng
- component nhỏ, app nhỏ
- chỉ vì nghe nói React phải memo mọi thứ

## Kết luận
Tối ưu React phải dựa trên hiểu re-render, không phải mê tín hook.