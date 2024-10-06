[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetBoardAssets

# Interface: IWidgetBoardAssets

## Properties

### fileChanged$

> **fileChanged$**: `Observable`\<[`FileChangedNotificationData`](../classes/FileChangedNotificationData.md)\>

Emits whenever a file is changed

***

### fileProcessingCompleted$

> **fileProcessingCompleted$**: `Observable`\<[`FileProcessingNotificationData`](../classes/FileProcessingNotificationData.md)\>

Emits whenever a file's processing is finished, eg extracting thumbnails or converting formats

## Methods

### getCorsMode()

> **getCorsMode**(`url`): `string`

Get appropriate CORS mode for loading file based on url

#### Parameters

• **url**: `string`

#### Returns

`string`

***

### getFileContent()

> **getFileContent**(`fileId`, `revisionId`?, `fileSize`?): `Promise`\<`string`\>

Get file contents as text

#### Parameters

• **fileId**: `string`

• **revisionId?**: `string`

can be omitted, defaults to latest revision

• **fileSize?**: `string`

can be omitted, defaults to `Original` filesize

#### Returns

`Promise`\<`string`\>

***

### getFileContentJson()

> **getFileContentJson**(`fileId`, `revisionId`?, `fileSize`?): `Promise`\<`any`\>

Get file contents as JSON

#### Parameters

• **fileId**: `string`

• **revisionId?**: `string`

can be omitted, defaults to latest revision

• **fileSize?**: `string`

can be omitted, defaults to `Original` filesize

#### Returns

`Promise`\<`any`\>

***

### getFileNode()

> **getFileNode**(`fileId`): `Promise`\<[`FileSystemNodeDto`](../classes/FileSystemNodeDto.md)\>

Get file entry

#### Parameters

• **fileId**: `string`

#### Returns

`Promise`\<[`FileSystemNodeDto`](../classes/FileSystemNodeDto.md)\>

***

### getFileUrl()

> **getFileUrl**(`fileId`, `revisionId`?, `fileSize`?): `Promise`\<`string`\>

Get url for a given file's contents

#### Parameters

• **fileId**: `string`

• **revisionId?**: `string`

can be omitted, defaults to latest revision

• **fileSize?**: `string`

can be omitted, defaults to `Original` filesize

#### Returns

`Promise`\<`string`\>

***

### putFileContents()

> **putFileContents**(`fileId`, `fileName`, `contents`): `Promise`\<[`StorageNodeCreatedResponseDto`](../classes/StorageNodeCreatedResponseDto.md)\>

Update existing file contents

#### Parameters

• **fileId**: `string`

• **fileName**: `string`

• **contents**: `any`

#### Returns

`Promise`\<[`StorageNodeCreatedResponseDto`](../classes/StorageNodeCreatedResponseDto.md)\>

***

### selectAndLoadImage()

> **selectAndLoadImage**(): `Promise`\<`HTMLImageElement`\>

Show selection dialog for [FileSystemNodeClassifier.Image](../enumerations/FileSystemNodeClassifier.md#image) and load the selected file into a HTMLImageElement

#### Returns

`Promise`\<`HTMLImageElement`\>

***

### selectFileId()

> **selectFileId**(`types`): `Promise`\<`string`\>

Show selection dialog and return selected file id

#### Parameters

• **types**: [`FileSystemNodeClassifier`](../enumerations/FileSystemNodeClassifier.md)[]

list of types to allow

#### Returns

`Promise`\<`string`\>

***

### uploadFile()

> **uploadFile**(`file`): `Promise`\<[`StorageNodeCreatedResponseDto`](../classes/StorageNodeCreatedResponseDto.md)\>

Upload new file

#### Parameters

• **file**: `File`

#### Returns

`Promise`\<[`StorageNodeCreatedResponseDto`](../classes/StorageNodeCreatedResponseDto.md)\>
