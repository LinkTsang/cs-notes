
## `any`, `unknown`, `Object`(`object`), `{}`, `Record<string, unknown>` 联系


### `any`:

- 任何值
- 不检查类型

### `unknown`:

- TypeScript 3.0 引入
- `unknown` 类型只能被赋值给 `any` 类型和 `unknown` 类型本身。
- 提供类型检查和类型断言


### `Object`(`object`), `{}`:

> - Avoid the Object and {} types, as they mean "any non-nullish value".
>   - This is a point of confusion for many developers, who think it means "any object type".
> - Avoid the object type, as it is currently hard to use due to not being able to assert that keys exist. 

[ESLint/ban-types](https://github.com/typescript-eslint/typescript-eslint/blob/master/packages/eslint-plugin/docs/rules/ban-types.md)

Solution: Use `Record<string, unknown>` instead.
