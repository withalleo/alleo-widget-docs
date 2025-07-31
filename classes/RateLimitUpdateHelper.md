[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / RateLimitUpdateHelper

# Class: RateLimitUpdateHelper\<T\>

A helper class to manage rapid updates to a shared variable.

## Type Parameters

### T

`T` = `any`

The type of the value being managed.

## Constructors

### Constructor

> **new RateLimitUpdateHelper**\<`T`\>(`key`, `maxDelay?`): `RateLimitUpdateHelper`\<`T`\>

Creates an instance of RateLimitUpdateHelper.

#### Parameters

##### key

`string`

The key used to store the value.

##### maxDelay?

`number` = `250`

The maximum delay between updates in milliseconds.

#### Returns

`RateLimitUpdateHelper`\<`T`\>

## Accessors

### latest

#### Get Signature

> **get** **latest**(): `T`

Gets the newest sent or received value.

##### Returns

`T`

- The newest sent or received value.

***

### newest

#### Get Signature

> **get** **newest**(): `T`

Gets the newest sent value.

##### Returns

`T`

- The newest sent value.

***

### stored

#### Get Signature

> **get** **stored**(): `T`

Gets the remotely stored value.

##### Returns

`T`

- The stored value.

## Methods

### set()

> **set**(`value`): `void`

Sets a new value and triggers an update if necessary.

#### Parameters

##### value

`T`

The new value to set.

#### Returns

`void`

***

### update()

> `protected` **update**(): `void`

Updates the stored value remotely if it has changed.

#### Returns

`void`
