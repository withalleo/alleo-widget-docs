[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetBaseManifest

# Interface: IWidgetBaseManifest

## Properties

### author

> **author**: `string`

Widget author

***

### authorUrl

> **authorUrl**: `string`

Widget author address (email, website or other)

***

### config?

> `optional` **config**: `object`

Widget specific configuration values, will be passed to widget
instances as `haptic.manifestConfig`

#### Additional Properties

true

***

### description

> **description**: `string`

Widget description

***

### entrypoints

> **entrypoints**: [`IWidgetEntrypoint`](IWidgetEntrypoint.md)[]

List of widget entrypoints

#### Min Items

1

***

### height

> **height**: `number`

Starting widget height

@TJS-type integer

***

### iconUrl

> **iconUrl**: `string`

Url to widget icon

***

### license?

> `optional` **license**: `string`

Widget license

***

### name

> **name**: `string`

Widget name

***

### tags?

> `optional` **tags**: `string`[]

List of tags describing this widget

***

### thumbnails?

> `optional` **thumbnails**: `string`[]

List of thumbnail urls

***

### version

> **version**: `string`

Current widget [version](../type-aliases/Semver.md) (to be used when creating new widgets).
Note that at least one [entrypoint](IWidgetBaseManifest.md#entrypoints) must match this version.

***

### width

> **width**: `number`

Starting widget width

@TJS-type integer
