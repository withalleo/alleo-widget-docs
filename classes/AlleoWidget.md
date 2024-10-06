[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / AlleoWidget

# Class: AlleoWidget\<SharedVariableStructure\>

Class representing an Alleo Widget.

Provides access to shared variables, a constructor, and a destroy method.

## Type Parameters

• **SharedVariableStructure** *extends* `Record`\<`string`, `any`\> = `Record`\<`string`, `any`\>

The structure of the shared variables.

## Constructors

### new AlleoWidget()

> **new AlleoWidget**\<`SharedVariableStructure`\>(`defaultSharedVariables`?, `settings`?): [`AlleoWidget`](AlleoWidget.md)\<`SharedVariableStructure`\>

Creates an instance of AlleoWidget.

#### Parameters

• **defaultSharedVariables?**: `Partial`\<`SharedVariableStructure`\> = `{}`

The default shared variables.

• **settings?**: `WidgetInitSettings` = `...`

The settings for the widget.

#### Returns

[`AlleoWidget`](AlleoWidget.md)\<`SharedVariableStructure`\>

## Properties

### dom

> `protected` **dom**: `HTMLDivElement`

***

### shared

> `protected` **shared**: `Partial`\<`SharedVariableStructure`\>

***

### widgetStatus

> `protected` **widgetStatus**: `object`

#### loaded

> **loaded**: `boolean`

## Methods

### assertWidgetLoaded()

> `protected` **assertWidgetLoaded**(): `void`

Asserts that the widget is loaded.

#### Returns

`void`

#### Throws

- If the widget has been destroyed.

***

### destroy()

> **destroy**(): `void` \| `Promise`\<`void`\>

Called when the widget instance is destroyed (when unloaded, NOT when the widget is deleted from the board).

#### Returns

`void` \| `Promise`\<`void`\>

***

### domSelect()

> `protected` **domSelect**\<`HTMLElementType`\>(`query`): `HTMLElementType`

Selects a DOM element within the widget container.

#### Type Parameters

• **HTMLElementType** *extends* `HTMLElement` = `HTMLElement`

The type of the HTML element.

#### Parameters

• **query**: `string`

The query selector.

#### Returns

`HTMLElementType`

- The selected HTML element.

#### Throws

- If no DOM is available.

***

### setContainerClass()

> `protected` **setContainerClass**(`className`, `add`?): `void`

Sets an HTML class for the widget container.

#### Parameters

• **className**: `string`

The class name to set.

• **add?**: `boolean` = `true`

Whether to add or remove the class. (if !add the "not-className" class is added, and the original is removed)

#### Returns

`void`

#### Throws

- If no DOM is available.
