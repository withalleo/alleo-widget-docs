[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / ExposeActionHelper

# Class: ExposeActionHelper

Helper class for exposing widget functionality to other objects on the board.

## Constructors

### new ExposeActionHelper()

> **new ExposeActionHelper**(): [`ExposeActionHelper`](ExposeActionHelper.md)

#### Returns

[`ExposeActionHelper`](ExposeActionHelper.md)

## Methods

### exposeActions()

> `static` **exposeActions**(`actions`): `void`

Exposes actions by adding them to the widget reference of the root node.

#### Parameters

• **actions**: `object`[]

The actions to expose.

#### Returns

`void`

***

### getExposedFunction()

> `static` **getExposedFunction**(`widget`, `functionName`): `AnyFunction`

Gets an exposed function from the widget by its name.

#### Parameters

• **widget**: `IBoardObject`

The widget object.

• **functionName**: `string`

The name of the function to get.

#### Returns

`AnyFunction`

The exposed function.

#### Throws

Will throw an error if no DOM is available or if the function is not found.

***

### getRootNode()

> `static` **getRootNode**(): `HTMLElementWithWidgetReference`

Gets the root node of the widget.

#### Returns

`HTMLElementWithWidgetReference`

The root node with widget reference.

#### Throws

Will throw an error if no DOM is available.

***

### handleAsyncMessage()

> `static` **handleAsyncMessage**(`widgetSyncMessage`, `filterType`?): `Promise`\<`void`\>

Handles an incoming asynchronous message from another widget.

#### Parameters

• **widgetSyncMessage**: [`WidgetSyncMessage`](../type-aliases/WidgetSyncMessage.md)

The widget synchronization message.

• **filterType?**: `string` = `undefined`

Optional filter type to process specific messages.

#### Returns

`Promise`\<`void`\>

***

### listExposedFunctions()

> `static` **listExposedFunctions**(`widget`): `Record`\<`string`, `AnyFunction`\>

Lists all exposed functions of the widget.

#### Parameters

• **widget**: `IBoardObject`

The widget object.

#### Returns

`Record`\<`string`, `AnyFunction`\>

A record of exposed functions.

#### Throws

Will throw an error if no DOM is available.

***

### sendAsyncMessage()

> `static` **sendAsyncMessage**(`functionName`, `type`?, `args`?): `any`

Sends an asynchronous message to connected widgets

#### Parameters

• **functionName**: `string`

The name of the function to call.

• **type?**: `string` = `''`

The type of the message.

• **args?**: `any` = `undefined`

The arguments to pass to the function.

#### Returns

`any`

The result of the function call.

***

### sendAsyncMessages()

> `static` **sendAsyncMessages**(`messages`): `any`

Sends multiple asynchronous messages to connected widgets.

#### Parameters

• **messages**: [`StandardSyncMessage`](../type-aliases/StandardSyncMessage.md)[]

The list of messages to send.

#### Returns

`any`

The result of the function calls.

***

### unExposeActions()

> `static` **unExposeActions**(`actions`): `void`

Removes an exposed functionality.

#### Parameters

• **actions**: `object`[]

The actions to unexpose.

#### Returns

`void`
