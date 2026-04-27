# 01. Đổi tư duy để học React đúng cách

## Vì sao người mới học React hay bị hụt
Nhiều người mới học React hay tưởng nó là một framework frontend full sẵn mọi thứ. Đây là sai lệch lớn nhất.

### Nhiều framework full thường cho sẵn
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

### Cách nghĩ kiểu framework full
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
### Cách nghĩ kiểu framework full

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
Nhiều framework full cho sẵn đường ray.
React cho mày bộ bánh xe và bắt mày tự ráp hệ thống.

Muốn học React không bị lệch thì phải bỏ tư duy so bì framework trước khi hiểu bản chất React.
Tư duy đúng là: “React ít opinionated hơn, nên mình phải tự chủ hơn.”