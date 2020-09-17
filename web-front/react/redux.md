# Overview

## What?

- 使用事件 `action` 和相应的 `reducer` 来管理和更新 应用程序的*全局状态* `store`.

## Why?

- 管理和更新全局状态
- 处理应用组件间的通信

## When?

- App 组件中有大量需要共享的状态时
- 组件间维护状态更新的逻辑复杂时

## Libraries and tools

- React-Redux
- Redux Toolkit
- Redux DevTools Extension

## Concepts

- Actions
  - `{type: string; payload: any}`
- Action Creators
  - `() => action`
- Reduces
  - `(state, action) => newState`
- Store
  - `{[name]: any}`
- Dispatch
  - `store.dispatch(action)`
- selectors
  - `(state) => state.value`

## Dataflow

![Redux Data Flow Diagram](./redux.assets/ReduxDataFlowDiagram.gif "Redux Data Flow Diagram")
