[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / AssetHelper

# Class: AssetHelper

A helper for handling file assets.

## Constructors

### new AssetHelper()

> **new AssetHelper**(`widgetContainerSelector`?): [`AssetHelper`](AssetHelper.md)

Creates an instance of AssetHelper.

#### Parameters

• **widgetContainerSelector?**: `string` = `'.widget-container'`

The CSS selector for the widget container.

#### Returns

[`AssetHelper`](AssetHelper.md)

## Properties

### assetsRoot

> `readonly` `static` **assetsRoot**: `string`

The root path for assets (ending with a slash).

## Methods

### setupCSSUrls()

> **setupCSSUrls**(`cssArray`): `void`

Sets up CSS URLs for the specified array of CSS properties.

#### Parameters

• **cssArray**: `object`[]

An array of objects containing CSS query, variable, and value.

#### Returns

`void`
