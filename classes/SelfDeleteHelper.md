[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SelfDeleteHelper

# Class: SelfDeleteHelper

## Constructors

### Constructor

> **new SelfDeleteHelper**(): `SelfDeleteHelper`

#### Returns

`SelfDeleteHelper`

## Properties

### deleteTriggerContent

> `protected` `static` **deleteTriggerContent**: `string` = `'deleteme'`

***

### storageKey

> `protected` `static` **storageKey**: `string` = `'ThisWidgetShouldBeDeleted'`

## Accessors

### shouldBeDeleted

#### Get Signature

> **get** **shouldBeDeleted**(): `boolean`

##### Returns

`boolean`

## Methods

### checkDeleteTrigger()

> `protected` **checkDeleteTrigger**(): `void`

#### Returns

`void`

***

### deleteSelf()

> **deleteSelf**(): `void`

Deletes the widget from the board

#### Returns

`void`

void

***

### setDeleteTrigger()

> `protected` **setDeleteTrigger**(): `void`

#### Returns

`void`
