[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / RateLimitUpdateHelper

# Class: RateLimitUpdateHelper\<T\>

A helper class to manage rapid updates to a shared variable.

## Type Parameters

• **T** = `any`

The type of the value being managed.

## Constructors

### new RateLimitUpdateHelper()

> **new RateLimitUpdateHelper**\<`T`\>(`key`, `maxDelay`?): [`RateLimitUpdateHelper`](RateLimitUpdateHelper.md)\<`T`\>

Creates an instance of RateLimitUpdateHelper.

#### Parameters

• **key**: `string`

The key used to store the value.

• **maxDelay?**: `number` = `250`

The maximum delay between updates in milliseconds.

#### Returns

[`RateLimitUpdateHelper`](RateLimitUpdateHelper.md)\<`T`\>

## Accessors

### newest

> `get` **newest**(): `T`

Gets the newest value.

#### Returns

`T`

- The newest value.

***

### stored

> `get` **stored**(): `T`

Gets the remotely stored value.

#### Returns

`T`

- The stored value.

## Methods

### set()

> **set**(`value`): `void`

Sets a new value and triggers an update if necessary.

#### Parameters

• **value**: `T`

The new value to set.

#### Returns

`void`

***

### update()

> `protected` **update**(): `void`

Updates the stored value remotely if it has changed.

#### Returns

`void`
