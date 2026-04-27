# 01. Angular sang React: đổi tư duy thế nào

## Vì sao Angular dev hay bị hụt khi sang React
Người quen Angular thường nghĩ React cũng là một framework frontend đầy đủ. Đây là sai lệch lớn nhất.

### Angular cho sẵn
- DI
- Router chuẩn
- HttpClient chuẩn
- Forms chuẩn
- structure khá rõ
- lifecycle dễ hình dung
- RxJS nằm trong lõi cách code

### React không cho sẵn hết
React chủ yếu lo phần UI rendering. Những thứ khác mày phải tự chọn:
- router nào
- form library nào
- state management nào
- data fetching strategy nào
- project structure nào

## So sánh cách nghĩ

### Angular
Mày thường nghĩ kiểu:
- tạo module
- tạo component
- inject service
- gọi API qua HttpClient
- subscribe data
- render template

### React
Mày phải nghĩ kiểu:
- component render theo state hiện tại
- state đổi thì component re-render
- hook để quản lý state, effect, memoization
- service/query lib là thứ tự chọn thêm

## Ví dụ cùng một bài toán
### Angular

```ts
@Component({
  selector: 'app-user-list',
  template: `
    <ul>
      <li *ngFor="let user of users">{{ user.name }}</li>
    </ul>
  `
})
export class UserListComponent implements OnInit {
  users: any[] = [];

  constructor(private userService: UserService) {}

  ngOnInit() {
    this.userService.getUsers().subscribe(data => {
      this.users = data;
    });
  }
}
```

### React

```jsx
import { useEffect, useState } from 'react';

function UserList() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch('/api/users')
      .then(res => res.json())
      .then(setUsers);
  }, []);

  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

## Cái mày phải học thêm khi sang React
- render cycle
- state và re-render
- object identity
- hooks
- composition
- cách tách logic bằng custom hooks

## Kết luận
Angular cho sẵn đường ray.
React cho mày bộ bánh xe và bắt mày tự ráp hệ thống.

Muốn chuyển hệ không bị ngu thì phải bỏ tư duy: “React thiếu Angular”.
Tư duy đúng là: “React ít opinionated hơn, nên mình phải tự chủ hơn.”