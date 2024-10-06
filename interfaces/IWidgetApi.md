[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetApi

# Interface: IWidgetApi

## Properties

### actionEffects

> **actionEffects**: [`ActionEffectDefinition`](ActionEffectDefinition.md)[]

Describe what actions this object can perform (for use in the action system)

***

### actionTriggers

> **actionTriggers**: [`ActionTriggerDefinition`](ActionTriggerDefinition.md)[]

Describe what actions this object can trigger (for use in the action system)

***

### board

> `readonly` **board**: [`IWidgetBoardApi`](IWidgetBoardApi.md)

Board API

***

### config

> `readonly` **config**: [`IWidgetConfiguration`](IWidgetConfiguration.md)

Widget initial config, including all widget data fields at instantiation time

***

### contextMenuButtons

> **contextMenuButtons**: [`ContextMenuButtonDefinition`](../type-aliases/ContextMenuButtonDefinition.md)[]

Describe custom buttons to be shown in the object context menu when selected.
Note that this will update the UI whenever it is assigned a new value so make sure
not to update in a `requestAnimationFrame` loop or similar since it will make the UI
unresponsive (due to the constant updates).

***

### creation

> `readonly` **creation**: `boolean`

Boolean indicating whether the widget is being added (new widget created)
or just instantiated, note that this will only be true for the client
that actually has created the object

***

### currentUser

> `readonly` **currentUser**: [`IBoardUser`](IBoardUser.md)

User API for the logged-in user

***

### dataChanged$

> `readonly` **dataChanged$**: `Observable`\<`Record`\<`string`, `any`\>\>

Observable that emits whenever the widget data is changed

***

### dblClickToZoom

> **dblClickToZoom**: `boolean`

Enable double click to zoom into an object

***

### enableResizing

> **enableResizing**: `boolean`

Enable object resizing mode (click on resize handle to get to the resize mode)

***

### extraDataCreated$

> `readonly` **extraDataCreated$**: `Observable`\<[`ObjectExtraDataCreatedDto`](../classes/ObjectExtraDataCreatedDto.md)\>

Observable that emits whenever a new extra data entry is created for this object

***

### extraDataDeleted$

> `readonly` **extraDataDeleted$**: `Observable`\<[`ObjectExtraDataDeletedDto`](../classes/ObjectExtraDataDeletedDto.md)\>

Observable that emits whenever an extra data entry is removed

***

### extraDataModified$

> `readonly` **extraDataModified$**: `Observable`\<[`ObjectExtraDataModifiedDto`](../classes/ObjectExtraDataModifiedDto.md)\>

Observable that emits whenever an extra data entry is modified

***

### finalScaleTransform

> `readonly` **finalScaleTransform**: `number`

This number combines the board canvas zoom level and this widget's scaling to
give you the final scale transform, this is useful when fixing 3rd party
libraries that assume the DOM element is not scaled via ```transform``` css.

***

### hideRemoteCursors

> **hideRemoteCursors**: `boolean`

Hide remote user cursors above the object

***

### humanTextId

> **humanTextId**: `string`

Human readable id for identifying the widget in selection dropdowns

***

### interactibility

> `readonly` **interactibility**: [`Interactibility`](Interactibility.md)

Contains last state from [IWidgetApi.interactibility$](IWidgetApi.md#interactibility$) observable.

***

### interactibility$

> `readonly` **interactibility$**: `Observable`\<[`Interactibility`](Interactibility.md)\>

An Observable that emits whenever the widget's interactibility should be updated.
You as the developer need to decide whether the widget needs to be interactible or not,
and specifically which part of the widget is interactible.
This is so the object can be moved when first selecting etc.

Most of the time it should suffice to set `pointer-events: none` on the root element of your widget

```typescript
haptic.interactibility$.subscribe((v:Interactibility) => {
   haptic.rootNode.style.pointerEvents = v.interactible ? '' : 'none';
})
```

The default value of [Interactibility.interactible](Interactibility.md#interactible) is computed for you and should fit most use cases.

***

### inViewport

> `readonly` **inViewport**: `boolean`

Indicates whether the object is inside the viewport

***

### inViewport$

> `readonly` **inViewport$**: `Observable`\<`boolean`\>

Observable that emits whenever [inViewport](IWidgetApi.md#inviewport) changes

***

### locked

> `readonly` **locked**: `boolean`

Indicates whether the object is selected by another client

***

### locked$

> `readonly` **locked$**: `Observable`\<`boolean`\>

Observable that emits whenever [locked](IWidgetApi.md#locked) changes

***

### logService

> `readonly` **logService**: [`ILogger`](ILogger.md)

Logging service

***

### manifestConfig?

> `readonly` `optional` **manifestConfig**: `Record`\<`string`, `any`\>

Configuration from widget manifest if applicable

***

### message$

> `readonly` **message$**: `Observable`\<[`WidgetMessageDto`](../classes/WidgetMessageDto.md)\>

An Observable that emits the payload whenever a message from [sendMessage](IWidgetApi.md#sendmessage) is received

***

### multiSelected

> `readonly` **multiSelected**: `boolean`

Indicates whether the object is multi-selected with other objects

***

### multiSelected$

> `readonly` **multiSelected$**: `Observable`\<`boolean`\>

Observable that emits whenever [multiSelected](IWidgetApi.md#multiselected) changes

***

### objectLinked$

> `readonly` **objectLinked$**: `Observable`\<[`ObjectLinkedNotificationData`](../classes/ObjectLinkedNotificationData.md)\>

Observable that emits whenever an object is linked to this one (so it will now
receive sync messages)

***

### objectLinksChanged$

> `readonly` **objectLinksChanged$**: `Observable`\<[`ObjectLinkedNotificationData`](../classes/ObjectLinkedNotificationData.md)\>

Observable that emits whenever this object's links are changed

***

### objectSettings

> **objectSettings**: [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>[]

Describe form fields for custom object settings to be shown in the settings dialog
(a 'Widget Settings' tab will be shown if present).
Note that this will update the UI whenever it is assigned a new value so make sure
not to update in a `requestAnimationFrame` loop or similar since it will make the UI
unresponsive (due to the constant updates).

***

### objectUnlinked$

> `readonly` **objectUnlinked$**: `Observable`\<[`ObjectLinkedNotificationData`](../classes/ObjectLinkedNotificationData.md)\>

Observable that emits whenever an object is unlinked

***

### room

> `readonly` **room**: [`IWidgetRoomApi`](IWidgetRoomApi.md)

Room API

***

### rootNode

> `readonly` **rootNode**: `HTMLElement`

Widget root DOM element, contents need to added under this element.
Adding content outside is *strongly* discouraged
(eg. via dialogs etc), any elements added outside *need* to be
cleaned up on removal by subscribing to [widgetDestroyed$](IWidgetApi.md#widgetdestroyed$)

***

### selected

> `readonly` **selected**: `boolean`

Indicates whether the object is selected by on this client

***

### selected$

> `readonly` **selected$**: `Observable`\<`boolean`\>

Observable that emits whenever [selected](IWidgetApi.md#selected) changes

***

### serverTime

> `readonly` **serverTime**: `number`

Server time, useful for synchronizing between clients eg. in timers,
countdown widgets etc.

***

### serverTimeMsec

> `readonly` **serverTimeMsec**: `number`

Same as [serverTime](IWidgetApi.md#servertime) but in milliseconds

***

### shouldConfirmRemoval

> **shouldConfirmRemoval**: `boolean`

Show confirm dialog before removing object

***

### syncMessage$

> `readonly` **syncMessage$**: `Observable`\<[`ObjectSyncMessageDto`](../classes/ObjectSyncMessageDto.md)\>

Observable that emits whenever a sync message is received

***

### transforming

> `readonly` **transforming**: `boolean`

Indicates whether the object is currently being transformed (scaled/moved/rotated)

***

### transforming$

> `readonly` **transforming$**: `Observable`\<`boolean`\>

Emits when [transforming](IWidgetApi.md#transforming) changes

***

### utils

> `readonly` **utils**: *typeof* [`Utils`](../classes/Utils.md)

Utilities

***

### widgetDestroyed$

> `readonly` **widgetDestroyed$**: `Observable`\<`void`\>

An Observable that emits when the widget is being destroyed, either by calling [destroy](IWidgetApi.md#destroy) or externally

***

### widgetId

> `readonly` **widgetId**: `string`

Widget object id

## Methods

### createExtraData()

> **createExtraData**(`dataType`, `data`, `referenceId`?): `Promise`\<`any`\>

Create a new extra data entry

#### Parameters

• **dataType**: [`BoardObjectExtraDataType`](../enumerations/BoardObjectExtraDataType.md)

• **data**: `any`

• **referenceId?**: `string`

#### Returns

`Promise`\<`any`\>

***

### deleteExtraData()

> **deleteExtraData**(`dataType`, `deletionType`, `referenceId`?): `Promise`\<`any`\>

Delete extra data entry or entries

#### Parameters

• **dataType**: [`BoardObjectExtraDataType`](../enumerations/BoardObjectExtraDataType.md)

• **deletionType**: [`ObjectExtraDataDeletionType`](../enumerations/ObjectExtraDataDeletionType.md)

• **referenceId?**: `string`

#### Returns

`Promise`\<`any`\>

***

### destroy()

> **destroy**(): `void`

Destroy the object

#### Returns

`void`

***

### getDataField()

> **getDataField**(`field`): `any`

Get widget's data field value

#### Parameters

• **field**: `any`

fieldname

#### Returns

`any`

***

### getFieldChanged$()

> **getFieldChanged$**(`field`, `startWithCurrent`?): `Observable`\<`any`\>

Get an Observable that fires only when a specific field changes

#### Parameters

• **field**: `string`

fieldname

• **startWithCurrent?**: `boolean`

if set to true the observable will emit immediately with current value

#### Returns

`Observable`\<`any`\>

***

### getLastSyncMessage()

> **getLastSyncMessage**(): `any`

Get last sync message

#### Returns

`any`

***

### getPosition()

> **getPosition**(): `object`

Get the widget's position

#### Returns

`object`

##### left

> **left**: `number`

##### top

> **top**: `number`

***

### getPositionLonLat()

> **getPositionLonLat**(): `object`

Get the widget's position based on geographical coordinates, only for map boards (see [IWidgetBoardApi.isMap](IWidgetBoardApi.md#ismap))

#### Returns

`object`

##### lat

> **lat**: `number`

##### lon

> **lon**: `number`

***

### getSize()

> **getSize**(): `object`

Get the widget's size and scale

#### Returns

`object`

##### height

> **height**: `number`

##### scaleX

> **scaleX**: `number`

##### scaleY

> **scaleY**: `number`

##### width

> **width**: `number`

***

### queryExtraData()

> **queryExtraData**(`query`): `Promise`\<[`BoardObjectExtraDataQueryResultDto`](../classes/BoardObjectExtraDataQueryResultDto.md)\>

Query the object's extra data. Extra data should be used for any data that's larger or
essentially not needed unless some condition is met eg. user interaction.

#### Parameters

• **query**: [`IExtraDataQuery`](IExtraDataQuery.md)

#### Returns

`Promise`\<[`BoardObjectExtraDataQueryResultDto`](../classes/BoardObjectExtraDataQueryResultDto.md)\>

***

### requireModule()

> **requireModule**(`module`): `Promise`\<`any`\>

Load bundled 3rd party js modules

#### Parameters

• **module**: [`AVAILABLE_MODULES`](../type-aliases/AVAILABLE_MODULES.md)

any of the supported modules

#### Returns

`Promise`\<`any`\>

***

### requireModules()

> **requireModules**(...`modules`): `Promise`\<`any`[]\>

Same as [requireModule](IWidgetApi.md#requiremodule) but takes any number of arguments and returns an array
when everything's loaded

#### Parameters

• ...**modules**: [`AVAILABLE_MODULES`](../type-aliases/AVAILABLE_MODULES.md)[]

any of the supported modules

#### Returns

`Promise`\<`any`[]\>

***

### sendMessage()

> **sendMessage**(`payload`, `userConnectionId`?, `widgetId`?): `any`

Send a message to widgets instances in other clients or if the target is not self as well to the local widget instance
The data is not stored anywhere so this should only be used when that's not needed.

#### Parameters

• **payload**: `Record`\<`string`, `unknown`\>

any JSON-serializable object

• **userConnectionId?**: `string`

if specified send the message only to that user

• **widgetId?**: `string`

if specified send the message to the specific widget otherwise defaults to self

#### Returns

`any`

***

### sendSyncMessage()

> **sendSyncMessage**(`data`): `any`

Send and store a sync message for all objects linked to this one,
the objects don't have to be initialized in other clients like with [sendMessage](IWidgetApi.md#sendmessage)
as this is persisted

#### Parameters

• **data**: `any`

any JSON-serializable payload

#### Returns

`any`

***

### setDataField()

#### setDataField(field, value, delta)

> **setDataField**(`field`, `value`, `delta`?): `Promise`\<`any`\>

Set the objects data field(s) to given values, for arrays the contents will be concatenated so
non-delta updates need to be used for removal/clearing

```typescript
setDataField('fieldA', 'value');

setDataField('users', ['userA','userB','userC'], false); // create or set array
setDataField('users', ['userD']); // append

setDataField('users', getDataField('users').filter(v => v === 'userB'), false); // remove 'userB'
setDataField('users', null, false); // remove array
```

##### Parameters

• **field**: `string` \| `Record`\<`string`, `any`\>

field name or key value object

• **value**: `any`

value, in case field is name

• **delta?**: `boolean`

indicate whether the changed values should be merged or replaced, can be omitted - defaults to true

##### Returns

`Promise`\<`any`\>

#### setDataField(fields, delta)

> **setDataField**(`fields`, `delta`?): `Promise`\<`any`\>

Set the objects data field(s) to given values, for arrays the contents will be concatenated so
non-delta updates need to be used for removal/clearing

```typescript
setDataField({
   fieldA: 'valueA',
   fieldB: 5,
   'users': ['userA','userB','userC'] // create array
}); // add some fields as an object

@param fields key-value object for fields
@param delta

##### Parameters

• **fields**: `Record`\<`string`, `any`\>

• **delta?**: `boolean`

##### Returns

`Promise`\<`any`\>

***

### setMinSize()

> **setMinSize**(`width`, `height`): `void`

Set the widget's minimum dimensions (for resieable widgets, see [enableResizing](IWidgetApi.md#enableresizing))

#### Parameters

• **width**: `number`

number

• **height**: `number`

number

#### Returns

`void`

***

### setPosition()

> **setPosition**(`left`, `top`): `any`

Set the widget's position, the object's origin is in the center

#### Parameters

• **left**: `number`

number

• **top**: `number`

number

#### Returns

`any`

***

### setPositionLonLat()

> **setPositionLonLat**(`lon`, `lat`): `any`

Set the widget's position based on geographical coordinates, only for map boards (see [IWidgetBoardApi.isMap](IWidgetBoardApi.md#ismap))

#### Parameters

• **lon**: `number`

longitude

• **lat**: `number`

latitude

#### Returns

`any`

***

### setScale()

> **setScale**(`scaleX`, `scaleY`): `any`

Set the widget's scale

#### Parameters

• **scaleX**: `number`

number

• **scaleY**: `number`

number

#### Returns

`any`

***

### setSize()

> **setSize**(`width`, `height`): `void`

Set the widget's dimensions

#### Parameters

• **width**: `number`

number

• **height**: `number`

number

#### Returns

`void`

***

### showFormDialog()

> **showFormDialog**\<`T`\>(`settings`): `Promise`\<`false` \| `""` \| `T`\>

Show an independent dialog with a custom Formly form for model type <T>.

#### Type Parameters

• **T** *extends* [`FormlyDialogModel`](../type-aliases/FormlyDialogModel.md) = [`FormlyDialogModel`](../type-aliases/FormlyDialogModel.md)

model type

#### Parameters

• **settings**: [`FormlyDialogSettings`](FormlyDialogSettings.md)\<`T`\>

dialog description

#### Returns

`Promise`\<`false` \| `""` \| `T`\>

***

### trackAnalyticsEvent()

> **trackAnalyticsEvent**(`name`, `payload`?): `void`

Track analytics event, note that this is throttled to one event every second

#### Parameters

• **name**: `string`

• **payload?**: `number` \| `Record`\<`string`, `any`\>

#### Returns

`void`

***

### triggerAction()

> **triggerAction**(`actionId`): `void`

Trigger an action

#### Parameters

• **actionId**: `string`

one of the `action.id`s listed in [actionTriggers](IWidgetApi.md#actiontriggers)

#### Returns

`void`

***

### updateExtraData()

> **updateExtraData**(`dataType`, `data`, `delta`?, `referenceId`?): `Promise`\<`any`\>

Update existing extra data entry

#### Parameters

• **dataType**: [`BoardObjectExtraDataType`](../enumerations/BoardObjectExtraDataType.md)

• **data**: `any`

• **delta?**: `boolean`

• **referenceId?**: `string`

#### Returns

`Promise`\<`any`\>

***

### upsertExtraData()

> **upsertExtraData**(`dataType`, `data`, `referenceId`?): `Promise`\<`any`\>

Create or update the extra data entry

#### Parameters

• **dataType**: [`BoardObjectExtraDataType`](../enumerations/BoardObjectExtraDataType.md)

• **data**: `any`

• **referenceId?**: `string`

#### Returns

`Promise`\<`any`\>

***

### widgetReady()

> **widgetReady**(): `void`

Notify the app that widget has finished instantiating, this *needs* to be
called at the end of init

#### Returns

`void`
