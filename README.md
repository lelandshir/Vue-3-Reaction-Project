# Vue 3 Notes

Léland Shirley

### Useful Shortcuts:

- In a blank component, type `vue` and select top option for shortcut to component makeup

### Remember:

- props `===` []
- Use data binding to conditionally disable and enable something like a button

### Lifecycle Hooks in Vue

- Use hooks to write logic and fire functions
- Every component is `created`, `mounted`, `updated` and `destroyed`
- Use functions/hooks (`beforeCreate()`, `created()`) to fire code at different points throughout these life cycles
- [Lifecycle Diagram](https://v3.vuejs.org/guide/instance.html#lifecycle-diagram)
- A popular place to make fetch reqs if data is needed for the component is in the `mounted()` function, but we can make request in the `created()`, and `beforeMount()` functions too
- `beforeUnmount()` and `unmounted()` are great places for any component clean up
- When using `Vue Router` a component is `unmounted` (destroyed) when we navigate away it's page
- To use a `hook` place it directly in the component object

### Custom Events & Emits

- When we `emit` a custom event from a child component we can send data that we can access from the parent
- React to the event being emitted on the child component that is nested in the parent by grabbing the name of the `emit`
- Use a `custom event` to pass data up from a nested child component into the root/parent component, then down into another child component using the `emit` keyword
- Emit the event from a method in the component that holds the data, react to it
