# React Hooks


### Emulate `componentDidMound`.
If you want to run a hook only in component mount, and only once, you can use the second parameter of the `useEffect` hook with an empty array.

```javascript
useEffect(() => {
	// my run on mount code
}, []);
```