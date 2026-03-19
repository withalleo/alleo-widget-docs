[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / isTransparent

# Function: isTransparent()

> **isTransparent**(`color`): `boolean`

Checks if a CSS color value represents a fully transparent color.

Detects transparency in various formats including the 'transparent' keyword,
rgba() with alpha=0, and empty/undefined values.

## Parameters

### color

`string`

The CSS color string to check (e.g., 'transparent', 'rgba(255,0,0,0)', '#ff0000').

## Returns

`boolean`

True if the color is fully transparent or empty, false otherwise.

## Example

```typescript
isTransparent('transparent');        // true
isTransparent('rgba(255, 0, 0, 0)'); // true
isTransparent('');                   // true
isTransparent('#ff0000');            // false
isTransparent('rgba(0, 0, 0, 0.5)'); // false (semi-transparent)
```
