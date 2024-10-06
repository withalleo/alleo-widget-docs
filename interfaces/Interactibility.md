[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / Interactibility

# Interface: Interactibility

## Properties

### interactible

> **interactible**: `boolean`

The default interactibility state for a widget, it is computed as follows from values in [state](Interactibility.md#state)
```typescript
return (
   !state.transforming &&
   !state.multiSelected &&
   (
      state.selected ||
      state.viewOnly ||
      (state.followingUser && !state.canEdit) ||
      state.locked ||
      (state.selectableByLongpress)
   )
);
```

***

### state

> **state**: `object`

#### canEdit

> **canEdit**: `boolean`

#### followingUser

> **followingUser**: `boolean`

#### inViewport

> **inViewport**: `boolean`

#### locked

> **locked**: `boolean`

#### multiSelected

> **multiSelected**: `boolean`

#### presentationActive

> **presentationActive**: `boolean`

#### selectableByLongpress

> **selectableByLongpress**: `boolean`

#### selected

> **selected**: `boolean`

#### transforming

> **transforming**: `boolean`

#### viewOnly

> **viewOnly**: `boolean`
