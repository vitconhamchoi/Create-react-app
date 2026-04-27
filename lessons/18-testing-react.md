# 18. Testing trong React

React test thường dùng:
- Vitest hoặc Jest
- React Testing Library

## Ví dụ component test

```jsx
import { render, screen } from '@testing-library/react';

function Hello({ name }) {
  return <h1>Hello {name}</h1>;
}

test('renders hello text', () => {
  render(<Hello name="Viet" />);
  expect(screen.getByText('Hello Viet')).toBeInTheDocument();
});
```

## Triết lý đúng
Test theo hành vi nhìn từ user, không test implementation detail quá nhiều.

## So với cách test quen thuộc ở framework khác
Một số framework khác có test harness riêng, còn React test thường nhẹ hơn.
React test thường nhẹ hơn, nhưng cũng dễ lỏng hơn nếu team không có kỷ luật.

## Kết luận
Không cần test tất cả.
Nhưng component quan trọng, form quan trọng, flow quan trọng nên có test.