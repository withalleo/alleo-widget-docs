[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ImageObjectCaptureHelper

# Class: ImageObjectCaptureHelper

Captures and processes images from image and video objects on the board.

Provides utilities for extracting image data from board objects including static images,
videos, live video streams, and screen shares. Supports various output formats (data URLs,
Uint8Array, ImageData), automatic resizing, and quality control. Essential for widgets that
need to process or analyze visual content from the board.

## Example

```typescript
// Get image object from board
const imageObj = BoardObjectHelper.getBoardObjectById(imageId);

// Check if object is supported
if (ImageObjectCaptureHelper.supportedObjectTypes.includes(imageObj.type)) {
  // Capture as data URL
  const dataUrl = await ImageObjectCaptureHelper.getContentAsImage(imageObj, {
    maxWidth: 512,
    maxHeight: 512,
    returnDataUrl: true,
    imageQuality: 0.9
  });

  // Capture as Uint8Array for processing
  const imageData = await ImageObjectCaptureHelper.getContentAsImage(imageObj, {
    returnImageData: false
  });
}
```

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

> `static` **getContentAsImage**\<`FunctionResultType`\>(`object`, `options?`): `FunctionResultType`

Captures the content of a board object as an image.

#### Type Parameters

##### FunctionResultType

`FunctionResultType` *extends* `string` \| `Uint8Array`\<`ArrayBufferLike`\> \| `Uint8ClampedArray`\<`ArrayBufferLike`\> \| `CanvasRenderingContext2D` = `Uint8Array`\<`ArrayBufferLike`\>

#### Parameters

##### object

[`RealIBoardObject`](../interfaces/RealIBoardObject.md)

The board object to capture.

##### options?

`GetContentAsImageOptions` = `{}`

Options for capturing the content.

#### Returns

`FunctionResultType`

The captured content in the specified format.

#### Throws

Will throw an error if the object type is not supported or if the media is not ready.

***

### getImageOrVideoContentImage()

> `static` **getImageOrVideoContentImage**\<`FunctionResultType`\>(`element`, `options?`): `FunctionResultType`

Captures the visual content of an image or video element.

Renders the element to a canvas and returns the image data in the requested format.
Automatically handles resizing while maintaining aspect ratio and quality settings.

#### Type Parameters

##### FunctionResultType

`FunctionResultType` *extends* `string` \| `Uint8Array`\<`ArrayBufferLike`\> \| `Uint8ClampedArray`\<`ArrayBufferLike`\> \| `CanvasRenderingContext2D` = `Uint8Array`\<`ArrayBufferLike`\>

The return type based on options (Uint8Array, string, CanvasRenderingContext2D, or Uint8ClampedArray).

#### Parameters

##### element

`ImageBitmap` \| `HTMLImageElement` \| `HTMLVideoElement`

The source element to capture from.

##### options?

`GetContentAsImageOptions` = `{}`

Capture configuration options.

#### Returns

`FunctionResultType`

Image data in the format specified by options.

#### Throws

Throws if element is invalid or unsupported.

#### Static
