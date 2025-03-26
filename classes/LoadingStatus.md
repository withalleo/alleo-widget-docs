[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / LoadingStatus

# Class: LoadingStatus

Class representing the loading status indicator for a service. indicates full-board loading.

## Constructors

### Constructor

> **new LoadingStatus**(`id`): `LoadingStatus`

Creates an instance of LoadingStatus.

#### Parameters

##### id

`string` = `...`

The unique identifier for the loading status.

#### Returns

`LoadingStatus`

## Properties

### showing

> **showing**: `boolean` = `false`

## Accessors

### loadingButtonHTML

#### Get Signature

> **get** `protected` **loadingButtonHTML**(): `string`

The HTML of the loading indicator.

##### Returns

`string`

## Methods

### hide()

> **hide**(): `void`

Hides the loading status by setting the opacity of the DOM element to 0.

#### Returns

`void`

***

### show()

> **show**(): `void`

Shows the loading status by setting the opacity of the DOM element to 1.

#### Returns

`void`
