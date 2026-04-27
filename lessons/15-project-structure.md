# 15. Project structure trong React

React không ép structure mạnh, nên nếu team không có convention thì code rất dễ loạn.

## Một structure đơn giản, đủ dùng

```text
src/
  app/
    router/
    providers/
  features/
    users/
      components/
      hooks/
      services/
      pages/
      types/
  shared/
    components/
    hooks/
    utils/
  lib/
```

## Ví dụ feature users

```text
features/users/
  components/UserCard.tsx
  pages/UserListPage.tsx
  services/userService.ts
  hooks/useUsers.ts
  types/user.ts
```

## Vì sao structure này dễ dùng
Vì nó vẫn giữ tư duy:
- tách theo feature
- tách UI và logic
- tách shared và domain-specific code

## Điều nên tránh
- để tất cả component trong một thư mục lớn
- service nằm lung tung
- hook nằm lung tung
- không tách feature

## Kết luận
React không ép structure, nhưng mày nên tự ép mình có structure.