[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / AnalyticsHelper

# Class: AnalyticsHelper

A helper collection for analytics and debugging.

## Constructors

### new AnalyticsHelper()

> **new AnalyticsHelper**(): [`AnalyticsHelper`](AnalyticsHelper.md)

#### Returns

[`AnalyticsHelper`](AnalyticsHelper.md)

## Methods

### debug()

> `static` **debug**(...`params`): `void`

Logs a debug message. Debug messages are only shown in development mode, and not logged.

#### Parameters

• ...**params**: `any`[]

The parameters to log.

#### Returns

`void`

***

### error()

> `static` **error**(...`params`): `void`

Logs an error message.

#### Parameters

• ...**params**: `any`[]

The parameters to log.

#### Returns

`void`

***

### getWidgetName()

> `static` **getWidgetName**(): `string`

Retrieves the widget name (id) from the configuration (or url)

#### Returns

`string`

The widget name or undefined if not found.

***

### info()

> `static` **info**(...`params`): `void`

Logs an info message. These are (usually) not shown in production, however are logged.

#### Parameters

• ...**params**: `any`[]

The parameters to log.

#### Returns

`void`

***

### LogAccessor()

> `static` **LogAccessor**(`target`, `propertyKey`, `descriptor`?): `void`

TypeScript decorator to log accessor calls.

#### Parameters

• **target**: `any`

The target object.

• **propertyKey**: `any`

The name of the accessor.

• **descriptor?**: `PropertyDescriptor` = `undefined`

The property descriptor.

#### Returns

`void`

***

### LogClass()

> `static` **LogClass**\<`T`\>(`constructor`): (...`args`) => `(Anonymous class)`\<`T`\> & `T`

TypeScript decorator to log class instantiation.

#### Type Parameters

• **T** *extends* (...`args`) => `object`

#### Parameters

• **constructor**: `T`

The class constructor.

#### Returns

(...`args`) => `(Anonymous class)`\<`T`\> & `T`

The new class with logging.

***

### LogMethod()

> `static` **LogMethod**(`target`, `propertyKey`, `descriptor`?): `void`

TypeScript decorator to log method calls.

#### Parameters

• **target**: `any`

The target object.

• **propertyKey**: `any`

The name of the method.

• **descriptor?**: `PropertyDescriptor` = `undefined`

The property descriptor.

#### Returns

`void`

***

### LogParameter()

> `static` **LogParameter**(`target`, `propertyKey`, `parameterIndex`?): `void`

TypeScript decorator to log parameter usage.

#### Parameters

• **target**: `any`

The target object.

• **propertyKey**: `any`

The name of the method.

• **parameterIndex?**: `number` = `undefined`

The index of the parameter.

#### Returns

`void`

***

### LogProperty()

> `static` **LogProperty**(`target`, `propertyKey`): `void`

TypeScript decorator to log property access.

#### Parameters

• **target**: `any`

The target object.

• **propertyKey**: `any`

The name of the property.

#### Returns

`void`

***

### trackEvent()

> `static` **trackEvent**(`action`, `payload`?): `void`

Tracks an analytics event.

#### Parameters

• **action**: `string`

The action name of the event.

• **payload?**: `Record`\<`string`, `any`\> = `{}`

Additional data to be sent with the event.

#### Returns

`void`

***

### warn()

> `static` **warn**(...`params`): `void`

Logs a warning message.

#### Parameters

• ...**params**: `any`[]

The parameters to log.

#### Returns

`void`
