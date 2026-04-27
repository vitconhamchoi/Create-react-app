# 02. JavaScript và TypeScript nào cần chắc trước khi học React

Nếu JS gốc không chắc thì học React chỉ là học mẹo.

## Những thứ phải chắc
- destructuring
- spread operator
- array methods như `map`, `filter`, `find`
- function là first-class value
- closure
- async/await
- object reference
- optional chaining
- TypeScript generic cơ bản

## Ví dụ 1. map và filter

```js
const users = [
  { id: 1, name: 'A', active: true },
  { id: 2, name: 'B', active: false }
];

const activeNames = users
  .filter(user => user.active)
  .map(user => user.name);

console.log(activeNames);
```

React code rất hay kiểu này.

## Ví dụ 2. spread operator để update state

```js
const user = { name: 'Viet', age: 28 };
const updatedUser = { ...user, age: 29 };
```

Khi update state trong React, mày làm kiểu này liên tục.

## Ví dụ 3. closure

```js
function createCounter() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}

const counter = createCounter();
console.log(counter());
console.log(counter());
```

Closure là nền tảng để hiểu hook và callback.

## Ví dụ 4. object reference

```js
const a = { name: 'Viet' };
const b = { name: 'Viet' };

console.log(a === b); // false
```

React rất nhạy với reference identity.

## TypeScript tối thiểu cần dùng trong React

```ts
type User = {
  id: number;
  name: string;
};

function UserCard({ user }: { user: User }) {
  return <div>{user.name}</div>;
}
```

## Kết luận
Muốn học React đỡ lú thì đừng nhảy vào hook trước.
Phải chắc JS/TS gốc trước đã.