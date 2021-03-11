# Vue 3 Notes

Léland Shirley

### Useful Shortcuts:

- In a blank component, type `vue` and select top option for shortcut to component makeup

### Remember:

- props === array
- Use data binding to conditionally disable and enable something like a button

### Lifecycle Hooks in Vue

- Every component is `created`, `mounted`, `updated` and `destroyed`
- Use functions/hooks (`beforeCreate()`, `created()`) to fire code at different points throughout these life cycles
- [Lifecycle Diagram](https://v3.vuejs.org/guide/instance.html#lifecycle-diagram)
- A popular place to make fetch reqs if data is needed for the component is in the `mounted()` function, but we can make request in the `created()`, and `beforeMount()` functions too
- `beforeUnmount()` and `unmounted()` are great places for any component clean up
- When using `Vue Router` a component is `unmounted` (destroyed) when we navigate away it's page
- To use a `hook` place it directly in the component object
