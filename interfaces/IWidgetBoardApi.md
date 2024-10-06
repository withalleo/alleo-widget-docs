[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetBoardApi

# Interface: IWidgetBoardApi

## Properties

### assets

> `readonly` **assets**: [`IWidgetBoardAssets`](IWidgetBoardAssets.md)

Board files API

***

### followingUser

> `readonly` **followingUser**: `boolean`

Indicates whether the user is currently following a leader
(so their viewport updates when the leader moves)

***

### followingUser$

> `readonly` **followingUser$**: `Observable`\<`boolean`\>

Observable that emits when [followingUser](IWidgetBoardApi.md#followinguser) changes

***

### fonts$

> `readonly` **fonts$**: `Observable`\<`object`[]\>

Observable that emits when board font configuration is changed or initially subscribed

***

### id

> `readonly` **id**: `string`

Board id

***

### isMap

> `readonly` **isMap**: `boolean`

Indicates whether the board is map type

***

### isOrphan

> `readonly` **isOrphan**: `boolean`

Indicates whether the board is an orphan (public template clone) that can be saved to users
own context using the save topbar button or via a trigger board tool action

***

### leadingUsers

> `readonly` **leadingUsers**: `boolean`

Indicates whether the current user is leading others

***

### leadingUsers$

> `readonly` **leadingUsers$**: `Observable`\<`boolean`\>

Observable that emits when [leadingUsers](IWidgetBoardApi.md#leadingusers) changes

***

### meeting

> `readonly` **meeting**: [`IWidgetBoardMeeting`](IWidgetBoardMeeting.md)

Board meeting API

***

### name

> `readonly` **name**: `string`

Board name

***

### objects

> `readonly` **objects**: [`IWidgetBoardObjects`](IWidgetBoardObjects.md)

Board objects API

***

### presentationActive

> `readonly` **presentationActive**: `boolean`

Whether the board is in presentation mode currently.
Note that this indicates the local state not whether there's a presentation at all.

***

### presentationActive$

> `readonly` **presentationActive$**: `Observable`\<`boolean`\>

Observable that emits when [presentationActive](IWidgetBoardApi.md#presentationactive) changes

***

### ui

> `readonly` **ui**: [`IWidgetBoardUi`](IWidgetBoardUi.md)

Board UI API

***

### userJoined$

> `readonly` **userJoined$**: `Observable`\<[`UserDto`](../classes/UserDto.md)\>

Observable that emits whenever a user joined the session

***

### userLeft$

> `readonly` **userLeft$**: `Observable`\<[`UserDto`](../classes/UserDto.md)\>

Observable that emits whenever a user left the session

***

### users

> `readonly` **users**: [`IBoardUser`](IBoardUser.md)[]

Board users

***

### viewOnly

> `readonly` **viewOnly**: `boolean`

Indicates whether the board is in view-only mode

***

### viewOnly$

> `readonly` **viewOnly$**: `Observable`\<`boolean`\>

Observable that emits when [viewOnly](IWidgetBoardApi.md#viewonly) changes

***

### viewportChanged$

> `readonly` **viewportChanged$**: `Observable`\<`object`\>

Observable that emits when the viewport is changed

#### Type declaration

##### animation?

> `optional` **animation**: `boolean`

***

### viewportPanned$

> `readonly` **viewportPanned$**: `Observable`\<`object`\>

Observable that emits when the viewport is panned

#### Type declaration

##### animation?

> `optional` **animation**: `boolean`

***

### viewportZoomed$

> `readonly` **viewportZoomed$**: `Observable`\<`object`\>

Observable that emits when the viewport is zoomed

#### Type declaration

##### animation?

> `optional` **animation**: `boolean`

## Methods

### getMembers()

> **getMembers**(): `Promise`\<[`IBoardMember`](IBoardMember.md)[]\>

Observable Get the board members, including offline users

#### Returns

`Promise`\<[`IBoardMember`](IBoardMember.md)[]\>

***

### moveTo()

> **moveTo**(`position`): `any`

Move the current viewport to the given position immediately

#### Parameters

• **position**: [`IPosition`](../type-aliases/IPosition.md)

#### Returns

`any`

***

### panTo()

> **panTo**(`position`, `zoom`): `Promise`\<`void`\>

Move the current viewport to the given position, using default animation

#### Parameters

• **position**: [`IPosition`](../type-aliases/IPosition.md)

• **zoom**: `number`

#### Returns

`Promise`\<`void`\>

***

### zoomTo()

> **zoomTo**(`zoom`): `any`

Zoom the current viewport to the given zoom level immediately

#### Parameters

• **zoom**: `number`

#### Returns

`any`
