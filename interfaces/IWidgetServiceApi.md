[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetServiceApi

# Interface: IWidgetServiceApi

## Extends

- `Omit`\<[`IWidgetApi`](IWidgetApi.md), `"rootNode"` \| `"setSize"` \| `"setMinSize"` \| `"getSize"` \| `"setScale"` \| `"setPosition"` \| `"getPosition"` \| `"setPositionLonLat"` \| `"getPositionLonLat"` \| `"enableResizing"` \| `"dblClickToZoom"` \| `"hideRemoteCursors"` \| `"interactibility$"` \| `"interactibility"` \| `"locked"` \| `"locked$"` \| `"selected"` \| `"selected$"` \| `"multiSelected"` \| `"multiSelected$"` \| `"inViewport"` \| `"inViewport$"` \| `"finalScaleTransform"` \| `"finalScaleTransform$"` \| `"transforming"` \| `"transforming$"` \| `"contextMenuButtons"`\>

## Properties

### actionEffects

> **actionEffects**: [`ActionEffectDefinition`](ActionEffectDefinition.md)[]

Describe what actions this object can perform (for use in the action system)

#### Inherited from

`Omit.actionEffects`

***

### actionTriggers

> **actionTriggers**: [`ActionTriggerDefinition`](ActionTriggerDefinition.md)[]

Describe what actions this object can trigger (for use in the action system)

#### Inherited from

`Omit.actionTriggers`

***

### board

> `readonly` **board**: [`IWidgetBoardApi`](IWidgetBoardApi.md)

Board API

#### Inherited from

`Omit.board`

***

### config

> `readonly` **config**: [`IWidgetConfiguration`](IWidgetConfiguration.md)

Widget initial config, including all widget data fields at instantiation time

#### Inherited from

`Omit.config`

***

### creation

> `readonly` **creation**: `boolean`

Boolean indicating whether the widget is being added (new widget created)
or just instantiated, note that this will only be true for the client
that actually has created the object

#### Inherited from

`Omit.creation`

***

### currentUser

> `readonly` **currentUser**: [`IBoardUser`](IBoardUser.md)

User API for the logged-in user

#### Inherited from

`Omit.currentUser`

***

### dataChanged$

> `readonly` **dataChanged$**: `Observable`\<`Record`\<`string`, `any`\>\>

Observable that emits whenever the widget data is changed

#### Inherited from

`Omit.dataChanged$`

***

### extraDataCreated$

> `readonly` **extraDataCreated$**: `Observable`\<[`ObjectExtraDataCreatedDto`](../classes/ObjectExtraDataCreatedDto.md)\>

Observable that emits whenever a new extra data entry is created for this object

#### Inherited from

`Omit.extraDataCreated$`

***

### extraDataDeleted$

> `readonly` **extraDataDeleted$**: `Observable`\<[`ObjectExtraDataDeletedDto`](../classes/ObjectExtraDataDeletedDto.md)\>

Observable that emits whenever an extra data entry is removed

#### Inherited from

`Omit.extraDataDeleted$`

***

### extraDataModified$

> `readonly` **extraDataModified$**: `Observable`\<[`ObjectExtraDataModifiedDto`](../classes/ObjectExtraDataModifiedDto.md)\>

Observable that emits whenever an extra data entry is modified

#### Inherited from

`Omit.extraDataModified$`

***

### humanTextId

> **humanTextId**: `string`

Human readable id for identifying the widget in selection dropdowns

#### Inherited from

`Omit.humanTextId`

***

### logService

> `readonly` **logService**: [`ILogger`](ILogger.md)

Logging service

#### Inherited from

`Omit.logService`

***

### manifestConfig?

> `readonly` `optional` **manifestConfig**: `Record`\<`string`, `any`\>

Configuration from widget manifest if applicable

#### Inherited from

`Omit.manifestConfig`

***

### message$

> `readonly` **message$**: `Observable`\<[`WidgetMessageDto`](../classes/WidgetMessageDto.md)\>

An Observable that emits the payload whenever a message from [sendMessage](IWidgetApi.md#sendmessage) is received

#### Inherited from

`Omit.message$`

***

### objectLinked$

> `readonly` **objectLinked$**: `Observable`\<[`ObjectLinkedNotificationData`](../classes/ObjectLinkedNotificationData.md)\>

Observable that emits whenever an object is linked to this one (so it will now
receive sync messages)

#### Inherited from

`Omit.objectLinked$`

***

### objectLinksChanged$

> `readonly` **objectLinksChanged$**: `Observable`\<[`ObjectLinkedNotificationData`](../classes/ObjectLinkedNotificationData.md)\>

Observable that emits whenever this object's links are changed

#### Inherited from

`Omit.objectLinksChanged$`

***

### objectSettings

> **objectSettings**: [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>[]

Describe form fields for custom object settings to be shown in the settings dialog
(a 'Widget Settings' tab will be shown if present).
Note that this will update the UI whenever it is assigned a new value so make sure
not to update in a `requestAnimationFrame` loop or similar since it will make the UI
unresponsive (due to the constant updates).

#### Inherited from

`Omit.objectSettings`

***

### objectUnlinked$

> `readonly` **objectUnlinked$**: `Observable`\<[`ObjectLinkedNotificationData`](../classes/ObjectLinkedNotificationData.md)\>

Observable that emits whenever an object is unlinked

#### Inherited from

`Omit.objectUnlinked$`

***

### room

> `readonly` **room**: [`IWidgetRoomApi`](IWidgetRoomApi.md)

Room API

#### Inherited from

`Omit.room`

***

### serverTime

> `readonly` **serverTime**: `number`

Server time, useful for synchronizing between clients eg. in timers,
countdown widgets etc.

#### Inherited from

`Omit.serverTime`

***

### serverTimeMsec

> `readonly` **serverTimeMsec**: `number`

Same as [serverTime](IWidgetApi.md#servertime) but in milliseconds

#### Inherited from

`Omit.serverTimeMsec`

***

### shouldConfirmRemoval

> **shouldConfirmRemoval**: `boolean`

Show confirm dialog before removing object

#### Inherited from

`Omit.shouldConfirmRemoval`

***

### syncMessage$

> `readonly` **syncMessage$**: `Observable`\<[`ObjectSyncMessageDto`](../classes/ObjectSyncMessageDto.md)\>

Observable that emits whenever a sync message is received

#### Inherited from

`Omit.syncMessage$`

***

### utils

> `readonly` **utils**: *typeof* [`Utils`](../classes/Utils.md)

Utilities

#### Inherited from

`Omit.utils`

***

### widgetDestroyed$

> `readonly` **widgetDestroyed$**: `Observable`\<`void`\>

An Observable that emits when the widget is being destroyed, either by calling [destroy](IWidgetApi.md#destroy) or externally

#### Inherited from

`Omit.widgetDestroyed$`

***

### widgetId

> `readonly` **widgetId**: `string`

Widget object id

#### Inherited from

`Omit.widgetId`

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

#### Inherited from

`Omit.createExtraData`

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

#### Inherited from

`Omit.deleteExtraData`

***

### destroy()

> **destroy**(): `void`

Destroy the object

#### Returns

`void`

#### Inherited from

`Omit.destroy`

***

### getDataField()

> **getDataField**(`field`): `any`

Get widget's data field value

#### Parameters

• **field**: `any`

fieldname

#### Returns

`any`

#### Inherited from

`Omit.getDataField`

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

#### Inherited from

`Omit.getFieldChanged$`

***

### getLastSyncMessage()

> **getLastSyncMessage**(): `any`

Get last sync message

#### Returns

`any`

#### Inherited from

`Omit.getLastSyncMessage`

***

### queryExtraData()

> **queryExtraData**(`query`): `Promise`\<[`BoardObjectExtraDataQueryResultDto`](../classes/BoardObjectExtraDataQueryResultDto.md)\>

Query the object's extra data. Extra data should be used for any data that's larger or
essentially not needed unless some condition is met eg. user interaction.

#### Parameters

• **query**: [`IExtraDataQuery`](IExtraDataQuery.md)

#### Returns

`Promise`\<[`BoardObjectExtraDataQueryResultDto`](../classes/BoardObjectExtraDataQueryResultDto.md)\>

#### Inherited from

`Omit.queryExtraData`

***

### requireModule()

> **requireModule**(`module`): `Promise`\<`any`\>

Load bundled 3rd party js modules

#### Parameters

• **module**: [`AVAILABLE_MODULES`](../type-aliases/AVAILABLE_MODULES.md)

any of the supported modules

#### Returns

`Promise`\<`any`\>

#### Inherited from

`Omit.requireModule`

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

#### Inherited from

`Omit.requireModules`

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

#### Inherited from

`Omit.sendMessage`

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

#### Inherited from

`Omit.sendSyncMessage`

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

##### Inherited from

`Omit.setDataField`

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

##### Inherited from

`Omit.setDataField`

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

#### Inherited from

`Omit.showFormDialog`

***

### trackAnalyticsEvent()

> **trackAnalyticsEvent**(`name`, `payload`?): `void`

Track analytics event, note that this is throttled to one event every second

#### Parameters

• **name**: `string`

• **payload?**: `number` \| `Record`\<`string`, `any`\>

#### Returns

`void`

#### Inherited from

`Omit.trackAnalyticsEvent`

***

### triggerAction()

> **triggerAction**(`actionId`): `void`

Trigger an action

#### Parameters

• **actionId**: `string`

one of the `action.id`s listed in [actionTriggers](IWidgetApi.md#actiontriggers)

#### Returns

`void`

#### Inherited from

`Omit.triggerAction`

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

#### Inherited from

`Omit.updateExtraData`

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

#### Inherited from

`Omit.upsertExtraData`

***

### widgetReady()

> **widgetReady**(): `void`

Notify the app that widget has finished instantiating, this *needs* to be
called at the end of init

#### Returns

`void`

#### Inherited from

`Omit.widgetReady`
