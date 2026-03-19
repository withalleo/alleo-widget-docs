[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SharedVariable

# Class: SharedVariable

Static utility for interacting with shared variables.

## Constructors

### Constructor

> **new SharedVariable**(): `SharedVariable`

#### Returns

`SharedVariable`

## Properties

### observer

> `static` **observer**: *typeof* `SharedVariableHelper` = `SharedVariableHelper`

Returns a SharedVariableHelper observer class.

## Methods

### append()

> `static` **append**(`variable`, `value`): `Promise`\<`any`\>

Appends values to a shared variable (array).

#### Parameters

##### variable

`string`

The variable name.

##### value

`any`[]

The values to append.

#### Returns

`Promise`\<`any`\>

***

### get()

> `static` **get**(`variable`): `any`

Gets the value of a shared variable.

#### Parameters

##### variable

`string`

The variable name.

#### Returns

`any`

***

### getMultiple()

> `static` **getMultiple**(`variables`): `Record`\<`string`, `any`\>

Gets multiple shared variable values.

#### Parameters

##### variables

`string`[]

Array of variable names.

#### Returns

`Record`\<`string`, `any`\>

***

### set()

> `static` **set**(`variable`, `value`): `Promise`\<`any`\>

Sets the value of a shared variable.

#### Parameters

##### variable

`string`

The variable name.

##### value

`any`

The value to set.

#### Returns

`Promise`\<`any`\>

***

### setMultiple()

> `static` **setMultiple**(`variables`, `delta?`): `Promise`\<`any`\>

Sets multiple shared variable values.

#### Parameters

##### variables

`Record`\<`string`, `any`\>

Object mapping variable names to values.

##### delta?

`boolean` = `true`

If true, applies changes as a delta.

#### Returns

`Promise`\<`any`\>
