---
id: anvogtpsax0d5xrvennzd66
title: TS
desc: ''
updated: 1657023665997
created: 1657023366326
tags: #ts
---

```tsx
interface Props {
    todo: Todo;
    todos: Todo[];
    setTodos: React.Dispatch<React.SetStateAction<Todo[]>>;
}

const TodoCard: React.FC<Props> = ({todo, todos, setTodos}) => {
    ...
}
```
