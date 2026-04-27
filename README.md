# React Learning Series

Bộ seri này dành cho người muốn học React theo hướng thực chiến, tập trung vào cách code app thật thay vì chỉ học lý thuyết.

Mục tiêu:
- hiểu React theo cách thực dụng, tập trung vào render, state, effect và tổ chức app
- biết React mạnh ở đâu, thiếu gì, phải tự bù bằng gì
- code được app thật thay vì chỉ biết JSX và vài hook cơ bản

## Cách đọc
- đọc theo thứ tự 01 -> 20
- mỗi bài đều có ví dụ code cụ thể
- tập trung vào tư duy chuyển hệ, không chỉ syntax

## Danh sách bài học

### Phần 1. Tư duy nền tảng
1. [Đổi tư duy để học React đúng cách](./lessons/01-react-learning-mindset.md)
2. [JavaScript và TypeScript nào cần chắc trước khi học React](./lessons/02-js-ts-for-react.md)
3. [Component, JSX, props, state](./lessons/03-components-jsx-props-state.md)
4. [Render cycle, re-render và vì sao React hay gây lú](./lessons/04-render-cycle-and-rerender.md)

### Phần 2. Làm chủ dữ liệu và UI
5. [Event handling và form trong React](./lessons/05-events-and-forms.md)
6. [useEffect, lifecycle và side effects](./lessons/06-useeffect-and-lifecycle.md)
7. [useMemo, useCallback, memo và tối ưu re-render](./lessons/07-memoization-and-performance.md)
8. [Conditional rendering, list rendering, key](./lessons/08-rendering-list-conditional-key.md)

### Phần 3. Tổ chức ứng dụng
9. [State management trong React](./lessons/09-state-management-in-react.md)
10. [Context API dùng được tới đâu](./lessons/10-context-api.md)
11. [Custom hooks để tái sử dụng logic](./lessons/11-custom-hooks.md)
12. [Service layer, data fetching và gọi API](./lessons/12-data-fetching-and-services.md)
13. [TanStack Query cho React app nghiêm túc](./lessons/13-tanstack-query.md)
14. [Routing trong React](./lessons/14-routing-in-react.md)
15. [Project structure trong React](./lessons/15-project-structure.md)

### Phần 4. Nâng cấp lên thực chiến
16. [Những thứ React không cho sẵn và cách tự bù](./lessons/16-what-react-does-not-give-you.md)
17. [Form nghiêm túc với react-hook-form và zod](./lessons/17-react-hook-form-and-zod.md)
18. [Testing trong React](./lessons/18-testing-react.md)
19. [Làm mini app React để học nhanh](./lessons/19-mini-project-plan.md)
20. [Roadmap 30 ngày học React](./lessons/20-react-30-day-roadmap.md)

## Kết luận nhanh
React cho mày core UI library và quyền tự quyết nhiều hơn ở tầng tổ chức ứng dụng.

Muốn chuyển sang React không bị ngu thì phải chắc:
- JS/TS gốc
- render cycle
- state
- effect
- reference identity
- hook mindset
- cách tự tổ chức app khi framework không lo hộ
