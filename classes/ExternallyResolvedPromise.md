[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / ExternallyResolvedPromise

# Class: ExternallyResolvedPromise\<T\>

## Type Parameters

• **T**

## Implements

- `Promise`\<`T`\>

## Constructors

### new ExternallyResolvedPromise()

> **new ExternallyResolvedPromise**\<`T`\>(): [`ExternallyResolvedPromise`](ExternallyResolvedPromise.md)\<`T`\>

#### Returns

[`ExternallyResolvedPromise`](ExternallyResolvedPromise.md)\<`T`\>

## Properties

### \[toStringTag\]

> **\[toStringTag\]**: `string`

#### Implementation of

`Promise.[toStringTag]`

## Accessors

### isRejected

> `get` **isRejected**(): `boolean`

#### Returns

`boolean`

***

### isResolved

> `get` **isResolved**(): `boolean`

#### Returns

`boolean`

## Methods

### catch()

> **catch**\<`TResult`\>(`onrejected`?): `Promise`\<`T` \| `TResult`\>

Attaches a callback for only the rejection of the Promise.

#### Type Parameters

• **TResult** = `never`

#### Parameters

• **onrejected?**

The callback to execute when the Promise is rejected.

#### Returns

`Promise`\<`T` \| `TResult`\>

A Promise for the completion of the callback.

#### Implementation of

`Promise.catch`

***

### finally()

> **finally**(`onfinally`?): `Promise`\<`T`\>

Attaches a callback that is invoked when the Promise is settled (fulfilled or rejected). The
resolved value cannot be modified from the callback.

#### Parameters

• **onfinally?**

The callback to execute when the Promise is settled (fulfilled or rejected).

#### Returns

`Promise`\<`T`\>

A Promise for the completion of the callback.

#### Implementation of

`Promise.finally`

***

### reject()

> **reject**(`reason`): `void`

#### Parameters

• **reason**: `any`

#### Returns

`void`

***

### resolve()

> **resolve**(`res`): `void`

#### Parameters

• **res**: `T`

#### Returns

`void`

***

### then()

> **then**\<`TResult1`, `TResult2`\>(`onfulfilled`?, `onrejected`?): `Promise`\<`TResult1` \| `TResult2`\>

Attaches callbacks for the resolution and/or rejection of the Promise.

#### Type Parameters

• **TResult1** = `T`

• **TResult2** = `never`

#### Parameters

• **onfulfilled?**

The callback to execute when the Promise is resolved.

• **onrejected?**

The callback to execute when the Promise is rejected.

#### Returns

`Promise`\<`TResult1` \| `TResult2`\>

A Promise for the completion of which ever callback is executed.

#### Implementation of

`Promise.then`
