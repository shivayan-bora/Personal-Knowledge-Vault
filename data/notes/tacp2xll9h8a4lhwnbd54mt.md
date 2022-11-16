
If we want to render components from an array of elements, we do the following:

```jsx
const allItems = [
  {id: 'apple', value: '🍎 apple'},
  {id: 'orange', value: '🍊 orange'},
  {id: 'grape', value: '🍇 grape'},
  {id: 'pear', value: '🍐 pear'},
]

function App() {
  const [items, setItems] = React.useState(allItems)

  function addItem() {
    const itemIds = items.map(i => i.id)
    setItems([...items, allItems.find(i => !itemIds.includes(i.id))])
  }

  function removeItem(item) {
    setItems(items.filter(i => i.id !== item.id))
  }

  return (
    <div className="keys">
      <button disabled={items.length >= allItems.length} onClick={addItem}>
        add item
      </button>
      <ul style={{listStyle: 'none', paddingLeft: 0}}>
        {items.map(item => (
          <li key={item.id}>
            <button onClick={() => removeItem(item)}>remove</button>{' '}
            <label htmlFor={`${item.id}-input`}>{item.value}</label>{' '}
            <input id={`${item.id}-input`} defaultValue={item.value} />
          </li>
        ))}
      </ul>
    </div>
  )
}
```

Notice that for each one of the list item, we're providing a key. That's very important to provide as this is how React uniquely identifies each one of the list items.

So if we don't provide a key, it will first of all throw a warning in the console. Apart from that if you add, modify or remove a particular element from the list, React needs to be able to uniquely identify which element was manipulated.

React takes a snapshot of the previous DOM and the latest DOM and then makes changes accordingly. So, it should know the element needs to be added, modified or removed, was at the first, the middle or the end. If we don't provide a key, it will try it's best to re-render the elements, however, it doesn't always nail the re-render and may lead to unexpected results especially when the element in picture is managed by some state.

It's also used to maintain focus, highlighted states etc.

**Note:** Providing the array index as a key doesn't solve this issue and you either need to give it a unique key or generate a unique key and provide it.

**Reference:**

1. [Understanding React's key prop](https://kentcdodds.com/blog/understanding-reacts-key-prop)
2. [Why React needs a key prop](https://epicreact.dev/why-react-needs-a-key-prop/)
