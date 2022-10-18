### Vue-Dragger

![](demo.gif)

### Installation & Dependencies

- [NodeJS](https://nodejs.org/en/)
- [VueJS](https://vuejs.org/)

### Usage

- To start a development server access the project directory through Terminal/Command Prompt and type in

```bash
npm run serve
```

- The component can be utitlized to make other components draggable. Simply import the `VueDraggable` component and insert any other components within it.

```html
  <VueDragger>
    <Component1 />
    <Component2 />
  </VueDragger>
```

- Methods can be called on drag start and drag end by passing them as `props`. Use the `onDragStart` and `onDragEnd` events to accomplish the same.

```html
  <VueDragger :onDragStart="start" :onDragEnd="stop">
    <Component />
  </VueDragger>
```

### TO-DO

- [ ] Add more functionality
- [ ] Allow passing data and display it as a draggable list of items.
- [ ] Fix bugs if any

### Note

> The draggable component encloses other component inside a `div` of its own and hence the styling should be done keeping this in mind.


