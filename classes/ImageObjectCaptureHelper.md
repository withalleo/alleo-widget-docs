[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ImageObjectCaptureHelper

# Class: ImageObjectCaptureHelper

Helper class for capturing image or video content from an object on the board.

## Constructors

### Constructor

> **new ImageObjectCaptureHelper**(): `ImageObjectCaptureHelper`

#### Returns

`ImageObjectCaptureHelper`

## Properties

### supportedImageObjectTypes

> `static` **supportedImageObjectTypes**: `BoardFabricObjectType`[]

***

### supportedObjectTypes

> `static` **supportedObjectTypes**: `BoardFabricObjectType`[]

***

### supportedVideoObjectTypes

> `static` **supportedVideoObjectTypes**: `BoardFabricObjectType`[]

## Methods

### getContentAsImage()

> `static` **getContentAsImage**\<`FunctionResultType`\>(`object`, `options`): `FunctionResultType`

Captures the content of a board object as an image.

#### Type Parameters

##### FunctionResultType

`FunctionResultType` *extends* `string` \| `Uint8Array`\<`ArrayBufferLike`\> \| `Uint8ClampedArray`\<`ArrayBufferLike`\> \| `CanvasRenderingContext2D` = `Uint8Array`\<`ArrayBufferLike`\>

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to capture.

##### options

`GetContentAsImageOptions` = `{}`

Options for capturing the content.

#### Returns

`FunctionResultType`

The captured content in the specified format.

#### Throws

Will throw an error if the object type is not supported or if the media is not ready.

***

### getImageOrVideoContentImage()

> `static` **getImageOrVideoContentImage**\<`FunctionResultType`\>(`element`, `options`): `FunctionResultType`

Captures the content of an image or video element as an image.

#### Type Parameters

##### FunctionResultType

`FunctionResultType` *extends* `string` \| `Uint8Array`\<`ArrayBufferLike`\> \| `Uint8ClampedArray`\<`ArrayBufferLike`\> \| `CanvasRenderingContext2D` = `Uint8Array`\<`ArrayBufferLike`\>

#### Parameters

##### element

The HTML element (video or image) to capture.

`ImageBitmap` | `HTMLImageElement` | `HTMLVideoElement`

##### options

`GetContentAsImageOptions` = `{}`

Options for capturing the content.

#### Returns

`FunctionResultType`

The captured content in the specified format.

#### Throws

Will throw an error if the element is invalid.
