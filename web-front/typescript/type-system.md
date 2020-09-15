## Index

- [Index](#index)
- [Utility Types](#utility-types)
  - [`Partial<T>`](#partialt)
  - [`Required<T>`](#requiredt)
  - [`Readonly<T>`](#readonlyt)
  - [`Pick<T, K extends keyof T>`](#pickt-k-extends-keyof-t)
  - [`Record<K extends keyof any, T>`](#recordk-extends-keyof-any-t)
  - [`Exclude<T, U>`](#excludet-u)
  - [`Extract<T, U>`](#extractt-u)
  - [`Omit<T, K extends keyof any>`](#omitt-k-extends-keyof-any)
  - [`NonNullable<T>`](#nonnullablet)
  - [`Parameters<T extends (...args: any) => any>`](#parameterst-extends-args-any--any)
  - [`ConstructorParameters<T>`](#constructorparameterst)
  - [`ReturnType<T extends (...args: any) => any>`](#returntypet-extends-args-any--any)
  - [`InstanceType<T extends new (...args: any) => any>`](#instancetypet-extends-new-args-any--any)
  - [`ThisParameterType<T>`](#thisparametertypet)
  - [`OmitThisParameter<T>`](#omitthisparametert)
  - [`ThisType<T>`](#thistypet)

## Utility Types

### `Partial<T>`

```typescript
/**
 * Make all properties in T optional
 */
type Partial<T> = {
  [P in keyof T]?: T[P];
};
```

### `Required<T>`

```typescript
/**
 * Make all properties in T required
 */
type Required<T> = {
  [P in keyof T]-?: T[P];
};
```

### `Readonly<T>`

```typescript
/**
 * Make all properties in T readonly
 */
type Readonly<T> = {
  readonly [P in keyof T]: T[P];
};
```

### `Pick<T, K extends keyof T>`

```typescript
/**
 * From T, pick a set of properties whose keys are in the union K
 */
type Pick<T, K extends keyof T> = {
  [P in K]: T[P];
};
```

### `Record<K extends keyof any, T>`

```typescript
/**
 * Construct a type with a set of properties K of type T
 */
type Record<K extends keyof any, T> = {
  [P in K]: T;
};
```

### `Exclude<T, U>`

```typescript
/**
 * Exclude from T those types that are assignable to U
 */
type Exclude<T, U> = T extends U ? never : T;
```

### `Extract<T, U>`

```typescript
/**
 * Extract from T those types that are assignable to U
 */
type Extract<T, U> = T extends U ? T : never;
```

### `Omit<T, K extends keyof any>`

```typescript
/**
 * Construct a type with the properties of T except for those in type K.
 */
type Omit<T, K extends keyof any> = Pick<T, Exclude<keyof T, K>>;
```

### `NonNullable<T>`

```typescript
/**
 * Exclude null and undefined from T
 */
type NonNullable<T> = T extends null | undefined ? never : T;
```

### `Parameters<T extends (...args: any) => any>`

```typescript
/**
 * Obtain the parameters of a function type in a tuple
 */
type Parameters<T extends (...args: any) => any> = T extends (
  ...args: infer P
) => any
  ? P
  : never;
```

### `ConstructorParameters<T>`

```typescript
/**
 * Obtain the parameters of a constructor function type in a tuple
 */
type ConstructorParameters<
  T extends new (...args: any) => any
> = T extends new (...args: infer P) => any ? P : never;
```

### `ReturnType<T extends (...args: any) => any>`

```typescript
/**
 * Obtain the return type of a function type
 */
type ReturnType<T extends (...args: any) => any> = T extends (
  ...args: any
) => infer R
  ? R
  : any;
```

### `InstanceType<T extends new (...args: any) => any>`

```typescript
/**
 * Obtain the return type of a constructor function type
 */
type InstanceType<T extends new (...args: any) => any> = T extends new (
  ...args: any
) => infer R
  ? R
  : any;
```

### `ThisParameterType<T>`

```typescript
/**
 * Extracts the type of the 'this' parameter of a function type, or 'unknown' if the function type has no 'this' parameter.
 */
type ThisParameterType<T> = T extends (this: infer U, ...args: any[]) => any
  ? U
  : unknown;
```

### `OmitThisParameter<T>`

```typescript
/**
 * Removes the 'this' parameter from a function type.
 */
type OmitThisParameter<T> = unknown extends ThisParameterType<T>
  ? T
  : T extends (...args: infer A) => infer R
  ? (...args: A) => R
  : T;
```

### `ThisType<T>`

```typescript
/**
 * Marker for contextual 'this' type
 */
interface ThisType<T> {}
```
