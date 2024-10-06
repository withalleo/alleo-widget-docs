[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetServiceManifest

# Interface: IWidgetServiceManifest

## Extends

- `Omit`\<[`IWidgetBaseManifest`](IWidgetBaseManifest.md), `"width"` \| `"height"`\>

## Properties

### author

> **author**: `string`

Widget author

#### Inherited from

`Omit.author`

***

### authorUrl

> **authorUrl**: `string`

Widget author address (email, website or other)

#### Inherited from

`Omit.authorUrl`

***

### config?

> `optional` **config**: `object`

Widget specific configuration values, will be passed to widget
instances as `haptic.manifestConfig`

#### Additional Properties

true

#### Inherited from

`Omit.config`

***

### description

> **description**: `string`

Widget description

#### Inherited from

`Omit.description`

***

### entrypoints

> **entrypoints**: [`IWidgetEntrypoint`](IWidgetEntrypoint.md)[]

List of widget entrypoints

#### Min Items

1

#### Inherited from

`Omit.entrypoints`

***

### iconUrl

> **iconUrl**: `string`

Url to widget icon

#### Inherited from

`Omit.iconUrl`

***

### license?

> `optional` **license**: `string`

Widget license

#### Inherited from

`Omit.license`

***

### name

> **name**: `string`

Widget name

#### Inherited from

`Omit.name`

***

### service

> **service**: `true`

Indicates this is a widget-service, this is a means to deploy always-running integration code to the client.
No visual component will be initialized for this widget and instead they are managed via the service panel.

***

### singleton

> **singleton**: `boolean`

Indicates this service can only be intantiated once per board.

***

### tags?

> `optional` **tags**: `string`[]

List of tags describing this widget

#### Inherited from

`Omit.tags`

***

### thumbnails?

> `optional` **thumbnails**: `string`[]

List of thumbnail urls

#### Inherited from

`Omit.thumbnails`

***

### version

> **version**: `string`

Current widget [version](../type-aliases/Semver.md) (to be used when creating new widgets).
Note that at least one [entrypoint](IWidgetBaseManifest.md#entrypoints) must match this version.

#### Inherited from

`Omit.version`
