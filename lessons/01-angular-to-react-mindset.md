# 01. Tư duy chuyển từ Angular sang React

## Vấn đề lớn nhất
Người quen Angular sang React hay bị hụt vì nghĩ React là một framework đầy đủ như Angular.

Thực tế:
- Angular là framework full-stack frontend
- React chủ yếu là thư viện xây UI

Nghĩa là trong Angular, nhiều thứ có sẵn:
- dependency injection
- router chuẩn
- form chuẩn
- http client chuẩn
- structure khá rõ
- RxJS nằm trong hệ sinh thái

Còn React thì không ép mạnh như vậy.
Mày phải tự chọn:
- router nào
- form library nào
- state management nào
- data fetching nào
- project structure nào

## Nếu mang tư duy Angular sang React sẽ lỗi ở đâu

### 1. Tìm service, module, DI nhưng không thấy
React không tổ chức app theo kiểu module/service chuẩn như Angular.

### 2. Tìm lifecycle giống Angular
React có render cycle và hooks, không giống `ngOnInit`, `ngOnDestroy` theo kiểu cũ.

### 3. Nghĩ rằng React “thiếu”
Thực ra React không hẳn thiếu. Nó chỉ ít opinionated hơn, bắt mày tự lắp ghép.

## Cách nghĩ đúng

### Angular
- framework định hướng mạnh
- app structure tương đối rõ
- code dễ đồng nhất nếu team đi cùng convention

### React
- linh hoạt hơn
- ít rào hơn
- dễ mạnh, nhưng cũng dễ loạn nếu team yếu

## Kỹ năng phải đổi
Từ Angular sang React, mày phải nâng mạnh mấy thứ này:
- JavaScript/TypeScript gốc
- state và re-render
- effect
- object identity/reference
- composition
- custom hooks

## Một câu chốt
Angular cho sẵn đường ray.
React đưa bộ bánh và bắt mày tự ráp xe.