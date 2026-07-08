[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / RateLimitFunctionHelper

# Class: RateLimitFunctionHelper

A helper class to limit the rapid runs of a function.

ie. you can have a callback that you want to run when there is an input to show some result.
But the arrives too rapidly so you might want to limit the rate of processing.

## Template

**T**

The type of the value being managed.

## Constructors

### Constructor

```ts
new RateLimitFunctionHelper(callback: () => void, maxDelay?: number): RateLimitFunctionHelper;
```

Creates an instance of RateLimitFunctionHelper.

#### Parameters

| Parameter   | Type         | Default value | Description                                        |
| ----------- | ------------ | ------------- | -------------------------------------------------- |
| `callback`  | () => `void` | `undefined`   | The callback function to be called                 |
| `maxDelay?` | `number`     | `250`         | The maximum delay between updates in milliseconds. |

#### Returns

`RateLimitFunctionHelper`

## Methods

### call()

```ts
call(): void;
```

#### Returns

`void`
