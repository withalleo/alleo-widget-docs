[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / ImageObjectCaptureHelper

# Class: ImageObjectCaptureHelper

Helper class for capturing image or video content from an object on the board.

## Constructors

### new ImageObjectCaptureHelper()

> **new ImageObjectCaptureHelper**(): [`ImageObjectCaptureHelper`](ImageObjectCaptureHelper.md)

#### Returns

[`ImageObjectCaptureHelper`](ImageObjectCaptureHelper.md)

## Properties

### supportedImageObjectTypes

> `static` **supportedImageObjectTypes**: [`BoardFabricObjectType`](../enumerations/BoardFabricObjectType.md)[]

***

### supportedObjectTypes

> `static` **supportedObjectTypes**: [`BoardFabricObjectType`](../enumerations/BoardFabricObjectType.md)[]

***

### supportedVideoObjectTypes

> `static` **supportedVideoObjectTypes**: [`BoardFabricObjectType`](../enumerations/BoardFabricObjectType.md)[]

## Methods

### getContentAsImage()

> `static` **getContentAsImage**\<`FunctionResultType`\>(`object`, `options`): `FunctionResultType`

Captures the content of a board object as an image.

#### Type Parameters

• **FunctionResultType** *extends* `string` \| `Uint8Array` \| `Uint8ClampedArray` \| `CanvasRenderingContext2D` = `Uint8Array`

#### Parameters

• **object**: [`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to capture.

• **options**: `GetContentAsImageOptions` = `{}`

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

• **FunctionResultType** *extends* `string` \| `Uint8Array` \| `Uint8ClampedArray` \| `CanvasRenderingContext2D` = `Uint8Array`

#### Parameters

• **element**: `ImageBitmap` \| `HTMLImageElement` \| `HTMLVideoElement`

The HTML element (video or image) to capture.

• **options**: `GetContentAsImageOptions` = `{}`

Options for capturing the content.

#### Returns

`FunctionResultType`

The captured content in the specified format.

#### Throws

Will throw an error if the element is invalid.
