[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / AssetHelper

# Class: AssetHelper

Helper class for managing and accessing widget asset files and resources.

Provides utilities for resolving asset paths, widget root paths, and setting up CSS background
images with proper URLs. Handles both local development and production deployment scenarios,
automatically adapting paths based on the widget's configuration and hosting environment.

## Example

```typescript
// Get the path to an asset file
const iconPath = AssetHelper.assetsRoot + 'icons/star.png';
const img = document.createElement('img');
img.src = iconPath;

// Set up CSS background images
const helper = new AssetHelper('.my-widget');
helper.setupCSSUrls([
  { query: '.header', variable: '--bg-image', value: AssetHelper.assetsRoot + 'bg.jpg' },
  { query: '.icon', variable: '--icon', value: AssetHelper.assetsRoot + 'icon.svg' }
]);
```

## Constructors

### Constructor

> **new AssetHelper**(`widgetContainerSelector?`): `AssetHelper`

Creates an instance of AssetHelper with a specified widget container selector.

#### Parameters

##### widgetContainerSelector?

`string` = `'.widget-container'`

The CSS selector for the widget's main container element.

#### Returns

`AssetHelper`

## Accessors

### assetsRoot

#### Get Signature

> **get** `static` **assetsRoot**(): `string`

The absolute root path for widget assets, ending with a slash.

This path points to the directory containing the widget's asset files (images, fonts, etc.).
The path is automatically determined based on deployment settings and widget configuration,
supporting both centralized widget hosting and standalone deployment scenarios.

##### Example

```typescript
const logoUrl = AssetHelper.assetsRoot + 'logo.png';
// Result: "https://widgets.alleo.com/my-widget/assets/widgetAssets/logo.png"
```

##### Returns

`string`

***

### widgetRoot

#### Get Signature

> **get** `static` **widgetRoot**(): `string`

The absolute root path for the widget's base directory, ending with a slash.

This path points to the widget's root folder containing manifest.json and other widget files.
Used as a base for resolving relative paths to widget resources and configuration files.

##### Example

```typescript
const configUrl = AssetHelper.widgetRoot + 'config.json';
// Result: "https://widgets.alleo.com/my-widget/config.json"
```

##### Returns

`string`

## Methods

### setupCSSUrls()

> **setupCSSUrls**(`cssArray`): `void`

Configures CSS custom properties (variables) with URL values for multiple elements.

This method automatically wraps asset URLs with the `url()` CSS function and sets them
as CSS custom properties on specified elements. Useful for dynamically setting background
images, masks, or other URL-based CSS properties.

#### Parameters

##### cssArray

`object`[]

Array of CSS configuration objects.

#### Returns

`void`

#### Example

```typescript
const assetHelper = new AssetHelper('.my-widget');
assetHelper.setupCSSUrls([
  {
    query: '.hero-section',
    variable: '--hero-bg',
    value: AssetHelper.assetsRoot + 'backgrounds/hero.jpg'
  },
  {
    query: '.button',
    variable: '--button-icon',
    value: AssetHelper.assetsRoot + 'icons/arrow.svg'
  }
]);
// CSS can then use: background-image: var(--hero-bg);
```
