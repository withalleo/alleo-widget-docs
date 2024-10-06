[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IBoardUser

# Interface: IBoardUser

## Properties

### canEdit

> `readonly` **canEdit**: `boolean`

Whether the user can modify content on the board, note that for [BoardMemberPermission.Contributor](../enumerations/BoardMemberPermission.md#contributor)
users this will be true however they can only interact with the board in a limited capability

***

### canEdit$

> `readonly` **canEdit$**: `Observable`\<`boolean`\>

Observable that emits whenever [canEdit](IBoardUser.md#canedit) changes

***

### canvasProperties

> `readonly` **canvasProperties**: `Partial`\<[`CanvasPropertiesUpdateDto`](../classes/CanvasPropertiesUpdateDto.md)\>

Describes the user's viewport position in the canvas

***

### canvasProperties$

> `readonly` **canvasProperties$**: `Observable`\<`Partial`\<[`CanvasPropertiesUpdateDto`](../classes/CanvasPropertiesUpdateDto.md)\>\>

Observable that emits whenever [canvasProperties](IBoardUser.md#canvasproperties) changes

***

### connectionId

> `readonly` **connectionId**: `string`

User client connection id

***

### cursorPos

> `readonly` **cursorPos**: `Partial`\<[`CursorPosUpdateDto`](../classes/CursorPosUpdateDto.md)\>

Describes the user's cursor position

***

### cursorPos$

> `readonly` **cursorPos$**: `Observable`\<`Partial`\<[`CursorPosUpdateDto`](../classes/CursorPosUpdateDto.md)\>\>

Observable that emits whenever [cursorPos](IBoardUser.md#cursorpos) changes

***

### id

> `readonly` **id**: `string`

User id

***

### imageUrl

> `readonly` **imageUrl**: `string`

User avatar if present

***

### lastActivityAt

> `readonly` **lastActivityAt**: `Date`

Last activity date (cursor move etc.)

***

### name

> `readonly` **name**: `string`

User full name

***

### permission

> `readonly` **permission**: [`BoardMemberPermission`](../enumerations/BoardMemberPermission.md)

User permission level

***

### permission$

> `readonly` **permission$**: `Observable`\<[`BoardMemberPermission`](../enumerations/BoardMemberPermission.md)\>

Observable that emits whenever [permission](IBoardUser.md#permission) changes

***

### profile

> `readonly` **profile**: [`PartialUserProfile`](../classes/PartialUserProfile.md)

Current user profile, the values iside [profile](IBoardUser.md#profile) are preferred over [name](IBoardUser.md#name) and [imageUrl](IBoardUser.md#imageurl)
as it is updated on change while the other 2 are not

***

### profile$

> `readonly` **profile$**: `Observable`\<[`PartialUserProfile`](../classes/PartialUserProfile.md)\>

Observable that emits whenever the user's [profile](IBoardUser.md#profile) changes
eg. they change their avatar, alias or color

***

### type

> `readonly` **type**: [`BoardHubUserType`](../enumerations/BoardHubUserType.md)

User type
