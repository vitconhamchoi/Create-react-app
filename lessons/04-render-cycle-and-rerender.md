# 04. Render cycle, re-render và vì sao React hay gây lú

Đây là chỗ rất nhiều người mới học React hay bị hụt nhất.

## React hoạt động kiểu gì
React component là function.
Mỗi lần state hoặc props đổi, function đó có thể chạy lại để tạo UI mới.

## Ví dụ

```jsx
function Demo() {
  console.log('render');
  return <div>Hello</div>;
}
```

Mỗi lần component render lại, `console.log` sẽ chạy lại.

## Ví dụ với state

```jsx
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  console.log('render', count);

  return (
    <button onClick={() => setCount(count + 1)}>
      {count}
    </button>
  );
}
```

Bấm nút là render lại.

## Tại sao nhiều người hay lú ở chỗ này
Vì nhiều người từng quen kiểu framework template-first hoặc class-first:
- component có lifecycle tương đối rõ
- template được bind vào class instance

Còn React bắt mày nghĩ:
- state mới -> render mới
- function chạy lại -> closure mới -> reference mới

## Ví dụ object reference gây re-render logic khó hiểu

```jsx
function Parent() {
  const config = { pageSize: 10 };
  return <Child config={config} />;
}
```

Mỗi lần `Parent` render, `config` là object mới.
Điều này ảnh hưởng tới memo/effect.

## Cách sửa

```jsx
import { useMemo } from 'react';

function Parent() {
  const config = useMemo(() => ({ pageSize: 10 }), []);
  return <Child config={config} />;
}
```

## Kết luận
Nếu không hiểu re-render, mày sẽ:
- viết effect sai
- memo sai
- callback sai
- blame React vô cớ