[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / DefaultLocale

# Class: DefaultLocale

A class that provides default locale settings for the widget.

## Constructors

### new DefaultLocale()

> **new DefaultLocale**(): [`DefaultLocale`](DefaultLocale.md)

#### Returns

[`DefaultLocale`](DefaultLocale.md)

## Properties

### dateFormat

> `static` **dateFormat**: `any` = `undefined`

The date format.

***

### language

> `static` **language**: `string`

The language code.

***

### timeFormat

> `static` **timeFormat**: `"12hrs"` \| `"24hrs"`

The time format, either '12hrs' or '24hrs'.

***

### timeZone

> `static` **timeZone**: `string`

The time zone.

***

### unitSystem

> `static` **unitSystem**: `"imperial"` \| `"si"`

The unit system, either 'imperial' or 'si'.

## Methods

### txt()

> `static` **txt**(`englishDefaultText`, `languageCode`?): `string`

Retrieves the translated text (if available) based on the provided language code.

#### Parameters

• **englishDefaultText**: `string`

The default text in English.

• **languageCode?**: `string` = `DefaultLocale.language`

The language code or 'original' to use the default text.

#### Returns

`string`

The translated text or the default text if no translation is found.
