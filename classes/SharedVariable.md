[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SharedVariable

# Class: SharedVariable

## Constructors

### Constructor

> **new SharedVariable**(): `SharedVariable`

#### Returns

`SharedVariable`

## Properties

### observer

> `static` **observer**: *typeof* `SharedVariableHelper` = `SharedVariableHelper`

## Methods

### append()

> `static` **append**(`variable`, `value`): `Promise`\<`any`\>

#### Parameters

##### variable

`string`

##### value

`any`[]

#### Returns

`Promise`\<`any`\>

***

### get()

> `static` **get**(`variable`): `any`

#### Parameters

##### variable

`string`

#### Returns

`any`

***

### getMultiple()

> `static` **getMultiple**(`variables`): `Record`\<`string`, `any`\>

#### Parameters

##### variables

`string`[]

#### Returns

`Record`\<`string`, `any`\>

***

### set()

> `static` **set**(`variable`, `value`): `Promise`\<`any`\>

#### Parameters

##### variable

`string`

##### value

`any`

#### Returns

`Promise`\<`any`\>

***

### setMultiple()

> `static` **setMultiple**(`variables`, `delta`): `Promise`\<`any`\>

#### Parameters

##### variables

`Record`\<`string`, `any`\>

##### delta

`boolean` = `true`

#### Returns

`Promise`\<`any`\>
