# 17. Form nghiêm túc với react-hook-form và zod

Nếu app có form thật, đừng code controlled input tay hết.

## Ví dụ với react-hook-form

```jsx
import { useForm } from 'react-hook-form';

function LoginForm() {
  const { register, handleSubmit } = useForm();

  const onSubmit = (data) => {
    console.log(data);
  };

  return (
    <form onSubmit={handleSubmit(onSubmit)}>
      <input {...register('email')} />
      <input type="password" {...register('password')} />
      <button type="submit">Login</button>
    </form>
  );
}
```

## Ví dụ với zod

```ts
import { z } from 'zod';

const loginSchema = z.object({
  email: z.string().email(),
  password: z.string().min(6),
});
```

## Vì sao nên học cái này
Vì nếu app có form thật thì chỉ code tay sẽ rất mệt.
Sang React mà không có tool đúng, cảm giác form sẽ rất cùi.

## Kết luận
react-hook-form + zod là combo rất đáng học nếu mày làm app React nghiêm túc.