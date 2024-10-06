[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / SharedCache

# Class: SharedCache\<T\>

Class representing a shared cache.

## Type Parameters

• **T** = `any`

The type of the cached values.

## Constructors

### new SharedCache()

> **new SharedCache**\<`T`\>(`databaseId`?, `delayedWrite`?): [`SharedCache`](SharedCache.md)\<`T`\>

Constructs a new SharedCache.

#### Parameters

• **databaseId?**: `string` = `'cache'`

The ID of the database.

• **delayedWrite?**: `boolean` = `false`

Whether to delay writes to the cache.

#### Returns

[`SharedCache`](SharedCache.md)\<`T`\>

## Properties

### debug

> `static` **debug**: `boolean` = `false`

Indicates whether debugging is enabled.

## Methods

### deploy()

> **deploy**(): `void`

Deploys the delayed writes to the cache.

#### Returns

`void`

***

### get()

> **get**(`key`): `T`

Gets a value from the cache.

#### Parameters

• **key**: `string`

The key of the value.

#### Returns

`T`

The value from the cache.

***

### set()

> **set**(`key`, `value`): `void`

Sets a value in the cache.

#### Parameters

• **key**: `string`

The key of the value.

• **value**: `T`

The value to set.

#### Returns

`void`
