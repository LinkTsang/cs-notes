# React

# Hook

## useCallback

返回一个 _memoized 回调函数_。

```javascript
const memoizedCallback = useCallback(() => {
  doSomething(a, b);
}, [a, b]);
```

`useCallback(fn, deps)` 相当于 `useMemo(() => fn, deps)`。

## useMemo

返回一个 _memoized 值_。仅在某个依赖项改变时才重新计算 memoized 值。

```javascript
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```
