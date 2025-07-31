[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DefaultLocale

# Class: DefaultLocale

A class that provides default locale settings for the widget.

## Constructors

### Constructor

> **new DefaultLocale**(): `DefaultLocale`

#### Returns

`DefaultLocale`

## Properties

### dateFormat

> `static` **dateFormat**: `any` = `undefined`

The date format.

***

### language

> `static` **language**: `string`

The language code.

***

### timeZone

> `static` **timeZone**: `string`

The time zone.

## Accessors

### timeFormat

#### Get Signature

> **get** `static` **timeFormat**(): `"12hrs"` \| `"24hrs"`

The time format, either '12hrs' or '24hrs'.

##### Returns

`"12hrs"` \| `"24hrs"`

***

### unitSystem

#### Get Signature

> **get** `static` **unitSystem**(): `"imperial"` \| `"si"`

The unit system, either 'imperial' or 'si'.

##### Returns

`"imperial"` \| `"si"`

## Methods

### txt()

> `static` **txt**(`englishDefaultText`, `languageCode?`): `string`

Retrieves the translated text (if available) based on the provided language code.

#### Parameters

##### englishDefaultText

`string`

The default text in English.

##### languageCode?

`string` = `DefaultLocale.language`

The language code or 'original' to use the default text.

#### Returns

`string`

The translated text or the default text if no translation is found.
