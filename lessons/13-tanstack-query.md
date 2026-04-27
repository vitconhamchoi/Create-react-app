# 13. TanStack Query cho React app nghiêm túc

Nếu Angular dev quen service + RxJS thì khi sang React, một tool rất đáng học là TanStack Query.

## Nó giải quyết gì
- loading
- caching
- refetch
- retry
- stale data
- mutation

## Ví dụ cơ bản

```jsx
import { useQuery } from '@tanstack/react-query';

async function getUsers() {
  const res = await fetch('/api/users');
  if (!res.ok) throw new Error('Failed');
  return res.json();
}

function UsersPage() {
  const { data, isLoading, error } = useQuery({
    queryKey: ['users'],
    queryFn: getUsers,
  });

  if (isLoading) return <p>Loading...</p>;
  if (error) return <p>Error</p>;

  return (
    <ul>
      {data.map(user => <li key={user.id}>{user.name}</li>)}
    </ul>
  );
}
```

## Vì sao nên học
Nếu app React nghiêm túc mà vẫn fetch tay bằng `useEffect` khắp nơi thì sớm muộn cũng bừa.

## Kết luận
TanStack Query là một trong những thứ giúp React app bớt hỗn loạn nhất.