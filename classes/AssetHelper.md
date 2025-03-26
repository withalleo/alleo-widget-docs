[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / AssetHelper

# Class: AssetHelper

A helper for handling file assets.

## Constructors

### Constructor

> **new AssetHelper**(`widgetContainerSelector`?): `AssetHelper`

Creates an instance of AssetHelper.

#### Parameters

##### widgetContainerSelector?

`string` = `'.widget-container'`

The CSS selector for the widget container.

#### Returns

`AssetHelper`

## Properties

### assetsRoot

> `readonly` `static` **assetsRoot**: `string`

The root path for assets (ending with a slash).

## Methods

### setupCSSUrls()

> **setupCSSUrls**(`cssArray`): `void`

Sets up CSS URLs for the specified array of CSS properties.

#### Parameters

##### cssArray

`object`[]

An array of objects containing CSS query, variable, and value.

#### Returns

`void`
