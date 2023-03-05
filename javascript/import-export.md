# Import/Export

```typescript
// a.ts
export default variableA;

// b.ts
export { default } from "./a"; // -> export default variableA
export { default as variableA } from "./a"; // -> export { variableA }
```

```typescript
// a.ts
export { variableA };
export default variableB;

// b.ts
export * from "./a"; // -> export { variableA } (no variableB is exported)
export { variableA } from "./a";
```
