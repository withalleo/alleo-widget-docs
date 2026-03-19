[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DefaultLocale

# Class: DefaultLocale

Provides locale-specific settings and utilities for internationalization.

Manages localization settings including time zones, languages, unit systems, and text translations.
Settings can be overridden via widget configuration for organization-specific customization.
Automatically detects browser locale preferences as fallbacks.

## Example

```typescript
// Use locale settings
const timezone = DefaultLocale.timeZone; // 'America/New_York'
const lang = DefaultLocale.language;     // 'EN-US'
const units = DefaultLocale.unitSystem;  // 'imperial' or 'si'
const time = DefaultLocale.timeFormat;   // '12hrs' or '24hrs'

// Translate text
const greeting = DefaultLocale.txt('Hello');           // Gets translation if available
const original = DefaultLocale.txt('Hello', 'original'); // Always returns English
```

## Constructors

### Constructor

> **new DefaultLocale**(): `DefaultLocale`

#### Returns

`DefaultLocale`

## Properties

### dateFormat

> `static` **dateFormat**: `unknown` = `undefined`

The date format string (currently not implemented).

#### Todo

Add date format implementation

***

### language

> `static` **language**: `string`

The language code for localization.

Follows ISO 639-1 language codes with optional region (e.g., 'EN-US', 'FR', 'DE-DE').
Used by the translation system to display text in the user's preferred language.

***

### timeZone

> `static` **timeZone**: `string`

The IANA time zone identifier for the user's location.

Used for displaying dates and times in the correct local time zone.
Can be overridden via widget settings, otherwise uses browser's time zone.

#### Example

```ts
'America/New_York', 'Europe/London', 'Asia/Tokyo'
```

## Accessors

### timeFormat

#### Get Signature

> **get** `static` **timeFormat**(): `"12hrs"` \| `"24hrs"`

The time format preference: '12hrs' (AM/PM) or '24hrs' (military time).

Automatically detected based on browser locale formatting. Can be overridden via
widget settings. Use this to display times in the user's familiar format.

##### Example

```typescript
if (DefaultLocale.timeFormat === '12hrs') {
  displayTime('3:30 PM');
} else {
  displayTime('15:30');
}
```

##### Returns

`"12hrs"` \| `"24hrs"`

***

### unitSystem

#### Get Signature

> **get** `static` **unitSystem**(): `"imperial"` \| `"si"`

The measurement unit system preference: 'imperial' (US) or 'si' (metric).

Automatically detected based on browser locale, defaulting to imperial for US/Liberia
and SI (metric) for all other regions. Can be overridden via widget settings.

##### Example

```typescript
if (DefaultLocale.unitSystem === 'imperial') {
  displayDistance(miles, 'mi');
} else {
  displayDistance(kilometers, 'km');
}
```

##### Returns

`"imperial"` \| `"si"`

***

### weekStartsSunday

#### Get Signature

> **get** `static` **weekStartsSunday**(): `boolean`

Whether the UI should treat Sunday as the first day of the week.

Priority:
1) Explicit WidgetSettings.settings.WeekStartsSunday (boolean) if provided.
2) Locale override on DefaultLocale (if present in DefaultLocale.localeOverrides.weekStartsSunday).
3) Browser language heuristic: US default to Sunday-first, others Monday-first.

##### Returns

`boolean`

## Methods

### txt()

> `static` **txt**(`englishDefaultText`, `languageCode?`): `string`

Retrieves translated text based on language settings with fallback to English.

Looks up translations in the following order:
1. Deployment-specific translations
2. Language-specific translations (exact match)
3. Language-specific translations (two-letter code only)
4. Generic translations
5. Original English text (fallback)

#### Parameters

##### englishDefaultText

`string`

The English text to translate (also used as lookup key).

##### languageCode?

`string` = `DefaultLocale.language`

Target language code, or 'original' to skip translation.

#### Returns

`string`

The translated text, or the original English if no translation exists.

#### Example

```typescript
// With translations configured
DefaultLocale.txt('Hello');           // 'Bonjour' (if French is configured)
DefaultLocale.txt('Hello', 'FR');     // 'Bonjour'
DefaultLocale.txt('Hello', 'original'); // 'Hello' (always English)

// Without translation
DefaultLocale.txt('Goodbye');         // 'Goodbye' (falls back to English)
```
