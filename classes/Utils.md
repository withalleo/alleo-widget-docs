[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / Utils

# Class: Utils

## Constructors

### new Utils()

> **new Utils**(): [`Utils`](Utils.md)

#### Returns

[`Utils`](Utils.md)

## Properties

### cancelAnimationFrame

> `static` **cancelAnimationFrame**: (`handle`) => `void` & (`handle`) => `void`

***

### clearInterval

> `static` **clearInterval**: (`id`) => `void` & (`id`) => `void`(`intervalId`) => `void`

***

### clearTimeout

> `static` **clearTimeout**: (`id`) => `void` & (`id`) => `void`(`timeoutId`) => `void`

***

### debounce()

> `static` **debounce**: \<`T`\>(`func`, `wait`, `options`) => `DebouncedFuncLeading`\<`T`\>\<`T_1`\>(`func`, `wait`?, `options`?) => `DebouncedFunc`\<`T_1`\>

#### Type Parameters

• **T** *extends* (...`args`) => `any`

#### Parameters

• **func**: `T`

• **wait**: `number`

• **options**: `DebounceSettingsLeading`

#### Returns

`DebouncedFuncLeading`\<`T`\>

#### Type Parameters

• **T_1** *extends* (...`args`) => `any`

#### Parameters

• **func**: `T_1`

• **wait?**: `number`

• **options?**: `DebounceSettings`

#### Returns

`DebouncedFunc`\<`T_1`\>

***

### ExternallyResolvedPromise

> `static` **ExternallyResolvedPromise**: *typeof* [`ExternallyResolvedPromise`](ExternallyResolvedPromise.md)

***

### get()

> `static` **get**: \<`TObject`, `TKey`\>(`object`, `path`) => `TObject`\[`TKey`\]\<`TObject_1`, `TKey_1`\>(`object`, `path`) => `TObject_1`\[`TKey_1`\]\<`TObject_2`, `TKey_2`, `TDefault`\>(`object`, `path`, `defaultValue`) => `TDefault` \| `Exclude`\<`TObject_2`\[`TKey_2`\], `undefined`\>\<`TObject_3`, `TKey1`, `TKey2`\>(`object`, `path`) => `TObject_3`\[`TKey1`\]\[`TKey2`\]\<`TObject_4`, `TKey1_1`, `TKey2_1`\>(`object`, `path`) => `TObject_4`\[`TKey1_1`\]\[`TKey2_1`\]\<`TObject_5`, `TKey1_2`, `TKey2_2`, `TDefault_1`\>(`object`, `path`, `defaultValue`) => `TDefault_1` \| `Exclude`\<`TObject_5`\[`TKey1_2`\]\[`TKey2_2`\], `undefined`\>\<`TObject_6`, `TKey1_3`, `TKey2_3`, `TKey3`\>(`object`, `path`) => `TObject_6`\[`TKey1_3`\]\[`TKey2_3`\]\[`TKey3`\]\<`TObject_7`, `TKey1_4`, `TKey2_4`, `TKey3_1`\>(`object`, `path`) => `TObject_7`\[`TKey1_4`\]\[`TKey2_4`\]\[`TKey3_1`\]\<`TObject_8`, `TKey1_5`, `TKey2_5`, `TKey3_2`, `TDefault_2`\>(`object`, `path`, `defaultValue`) => `TDefault_2` \| `Exclude`\<`TObject_8`\[`TKey1_5`\]\[`TKey2_5`\]\[`TKey3_2`\], `undefined`\>\<`TObject_9`, `TKey1_6`, `TKey2_6`, `TKey3_3`, `TKey4`\>(`object`, `path`) => `TObject_9`\[`TKey1_6`\]\[`TKey2_6`\]\[`TKey3_3`\]\[`TKey4`\]\<`TObject_10`, `TKey1_7`, `TKey2_7`, `TKey3_4`, `TKey4_1`\>(`object`, `path`) => `TObject_10`\[`TKey1_7`\]\[`TKey2_7`\]\[`TKey3_4`\]\[`TKey4_1`\]\<`TObject_11`, `TKey1_8`, `TKey2_8`, `TKey3_5`, `TKey4_2`, `TDefault_3`\>(`object`, `path`, `defaultValue`) => `TDefault_3` \| `Exclude`\<`TObject_11`\[`TKey1_8`\]\[`TKey2_8`\]\[`TKey3_5`\]\[`TKey4_2`\], `undefined`\>\<`T`\>(`object`, `path`) => `T`\<`T_1`\>(`object`, `path`) => `T_1`\<`T_2`, `TDefault_4`\>(`object`, `path`, `defaultValue`) => `T_2` \| `TDefault_4`\<`TDefault_5`\>(`object`, `path`, `defaultValue`) => `TDefault_5`(`object`, `path`) => `undefined`\<`TObject_12`, `TPath`\>(`data`, `path`) => `string` *extends* `TPath` ? `any` : `GetFieldType`\<`TObject_12`, `TPath`, `"Path"`\>\<`TObject_13`, `TPath_1`, `TDefault_6`\>(`data`, `path`, `defaultValue`) => `TDefault_6` \| `Exclude`\<`GetFieldType`\<`TObject_13`, `TPath_1`, `"Path"`\>, `null`\>(`object`, `path`, `defaultValue`?) => `any`

#### Type Parameters

• **TObject** *extends* `object`

• **TKey** *extends* `string` \| `number` \| `symbol`

#### Parameters

• **object**: `TObject`

• **path**: `TKey` \| [`TKey`]

#### Returns

`TObject`\[`TKey`\]

#### Type Parameters

• **TObject_1** *extends* `object`

• **TKey_1** *extends* `string` \| `number` \| `symbol`

#### Parameters

• **object**: `TObject_1`

• **path**: `TKey_1` \| [`TKey_1`]

#### Returns

`TObject_1`\[`TKey_1`\]

#### Type Parameters

• **TObject_2** *extends* `object`

• **TKey_2** *extends* `string` \| `number` \| `symbol`

• **TDefault**

#### Parameters

• **object**: `TObject_2`

• **path**: `TKey_2` \| [`TKey_2`]

• **defaultValue**: `TDefault`

#### Returns

`TDefault` \| `Exclude`\<`TObject_2`\[`TKey_2`\], `undefined`\>

#### Type Parameters

• **TObject_3** *extends* `object`

• **TKey1** *extends* `string` \| `number` \| `symbol`

• **TKey2** *extends* `string` \| `number` \| `symbol`

#### Parameters

• **object**: `TObject_3`

• **path**: [`TKey1`, `TKey2`]

#### Returns

`TObject_3`\[`TKey1`\]\[`TKey2`\]

#### Type Parameters

• **TObject_4** *extends* `object`

• **TKey1_1** *extends* `string` \| `number` \| `symbol`

• **TKey2_1** *extends* `string` \| `number` \| `symbol`

#### Parameters

• **object**: `TObject_4`

• **path**: [`TKey1_1`, `TKey2_1`]

#### Returns

`TObject_4`\[`TKey1_1`\]\[`TKey2_1`\]

#### Type Parameters

• **TObject_5** *extends* `object`

• **TKey1_2** *extends* `string` \| `number` \| `symbol`

• **TKey2_2** *extends* `string` \| `number` \| `symbol`

• **TDefault_1**

#### Parameters

• **object**: `TObject_5`

• **path**: [`TKey1_2`, `TKey2_2`]

• **defaultValue**: `TDefault_1`

#### Returns

`TDefault_1` \| `Exclude`\<`TObject_5`\[`TKey1_2`\]\[`TKey2_2`\], `undefined`\>

#### Type Parameters

• **TObject_6** *extends* `object`

• **TKey1_3** *extends* `string` \| `number` \| `symbol`

• **TKey2_3** *extends* `string` \| `number` \| `symbol`

• **TKey3** *extends* `string` \| `number` \| `symbol`

#### Parameters

• **object**: `TObject_6`

• **path**: [`TKey1_3`, `TKey2_3`, `TKey3`]

#### Returns

`TObject_6`\[`TKey1_3`\]\[`TKey2_3`\]\[`TKey3`\]

#### Type Parameters

• **TObject_7** *extends* `object`

• **TKey1_4** *extends* `string` \| `number` \| `symbol`

• **TKey2_4** *extends* `string` \| `number` \| `symbol`

• **TKey3_1** *extends* `string` \| `number` \| `symbol`

#### Parameters

• **object**: `TObject_7`

• **path**: [`TKey1_4`, `TKey2_4`, `TKey3_1`]

#### Returns

`TObject_7`\[`TKey1_4`\]\[`TKey2_4`\]\[`TKey3_1`\]

#### Type Parameters

• **TObject_8** *extends* `object`

• **TKey1_5** *extends* `string` \| `number` \| `symbol`

• **TKey2_5** *extends* `string` \| `number` \| `symbol`

• **TKey3_2** *extends* `string` \| `number` \| `symbol`

• **TDefault_2**

#### Parameters

• **object**: `TObject_8`

• **path**: [`TKey1_5`, `TKey2_5`, `TKey3_2`]

• **defaultValue**: `TDefault_2`

#### Returns

`TDefault_2` \| `Exclude`\<`TObject_8`\[`TKey1_5`\]\[`TKey2_5`\]\[`TKey3_2`\], `undefined`\>

#### Type Parameters

• **TObject_9** *extends* `object`

• **TKey1_6** *extends* `string` \| `number` \| `symbol`

• **TKey2_6** *extends* `string` \| `number` \| `symbol`

• **TKey3_3** *extends* `string` \| `number` \| `symbol`

• **TKey4** *extends* `string` \| `number` \| `symbol`

#### Parameters

• **object**: `TObject_9`

• **path**: [`TKey1_6`, `TKey2_6`, `TKey3_3`, `TKey4`]

#### Returns

`TObject_9`\[`TKey1_6`\]\[`TKey2_6`\]\[`TKey3_3`\]\[`TKey4`\]

#### Type Parameters

• **TObject_10** *extends* `object`

• **TKey1_7** *extends* `string` \| `number` \| `symbol`

• **TKey2_7** *extends* `string` \| `number` \| `symbol`

• **TKey3_4** *extends* `string` \| `number` \| `symbol`

• **TKey4_1** *extends* `string` \| `number` \| `symbol`

#### Parameters

• **object**: `TObject_10`

• **path**: [`TKey1_7`, `TKey2_7`, `TKey3_4`, `TKey4_1`]

#### Returns

`TObject_10`\[`TKey1_7`\]\[`TKey2_7`\]\[`TKey3_4`\]\[`TKey4_1`\]

#### Type Parameters

• **TObject_11** *extends* `object`

• **TKey1_8** *extends* `string` \| `number` \| `symbol`

• **TKey2_8** *extends* `string` \| `number` \| `symbol`

• **TKey3_5** *extends* `string` \| `number` \| `symbol`

• **TKey4_2** *extends* `string` \| `number` \| `symbol`

• **TDefault_3**

#### Parameters

• **object**: `TObject_11`

• **path**: [`TKey1_8`, `TKey2_8`, `TKey3_5`, `TKey4_2`]

• **defaultValue**: `TDefault_3`

#### Returns

`TDefault_3` \| `Exclude`\<`TObject_11`\[`TKey1_8`\]\[`TKey2_8`\]\[`TKey3_5`\]\[`TKey4_2`\], `undefined`\>

#### Type Parameters

• **T**

#### Parameters

• **object**: `NumericDictionary`\<`T`\>

• **path**: `number`

#### Returns

`T`

#### Type Parameters

• **T_1**

#### Parameters

• **object**: `NumericDictionary`\<`T_1`\>

• **path**: `number`

#### Returns

`T_1`

#### Type Parameters

• **T_2**

• **TDefault_4**

#### Parameters

• **object**: `NumericDictionary`\<`T_2`\>

• **path**: `number`

• **defaultValue**: `TDefault_4`

#### Returns

`T_2` \| `TDefault_4`

#### Type Parameters

• **TDefault_5**

#### Parameters

• **object**: `null`

• **path**: `PropertyPath`

• **defaultValue**: `TDefault_5`

#### Returns

`TDefault_5`

#### Parameters

• **object**: `null`

• **path**: `PropertyPath`

#### Returns

`undefined`

#### Type Parameters

• **TObject_12**

• **TPath** *extends* `string`

#### Parameters

• **data**: `TObject_12`

• **path**: `TPath`

#### Returns

`string` *extends* `TPath` ? `any` : `GetFieldType`\<`TObject_12`, `TPath`, `"Path"`\>

#### Type Parameters

• **TObject_13**

• **TPath_1** *extends* `string`

• **TDefault_6** = `GetFieldType`\<`TObject_13`, `TPath_1`, `"Path"`\>

#### Parameters

• **data**: `TObject_13`

• **path**: `TPath_1`

• **defaultValue**: `TDefault_6`

#### Returns

`TDefault_6` \| `Exclude`\<`GetFieldType`\<`TObject_13`, `TPath_1`, `"Path"`\>, `null`\>

#### Parameters

• **object**: `any`

• **path**: `PropertyPath`

• **defaultValue?**: `any`

#### Returns

`any`

***

### has()

> `static` **has**: \<`T`\>(`object`, `path`) => `boolean`

#### Type Parameters

• **T**

#### Parameters

• **object**: `T`

• **path**: `PropertyPath`

#### Returns

`boolean`

***

### imgCache

> `static` **imgCache**: `Map`\<`string`, `string`\>

***

### memoizeDebounce()

> `static` **memoizeDebounce**: \<`F`\>(`func`, `wait`?, `options`?, `resolver`?) => [`MemoizeDebouncedFunction`](../interfaces/MemoizeDebouncedFunction.md)\<`F`\>

#### Type Parameters

• **F** *extends* (...`args`) => `any`

#### Parameters

• **func**: `F`

• **wait?**: `number`

• **options?**: `DebounceSettings`

• **resolver?**

#### Returns

[`MemoizeDebouncedFunction`](../interfaces/MemoizeDebouncedFunction.md)\<`F`\>

***

### memoizeThrottle()

> `static` **memoizeThrottle**: \<`F`\>(`func`, `wait`?, `options`?, `resolver`?) => [`MemoizeThrottledFunction`](../interfaces/MemoizeThrottledFunction.md)\<`F`\>

#### Type Parameters

• **F** *extends* (...`args`) => `any`

#### Parameters

• **func**: `F`

• **wait?**: `number`

• **options?**: `ThrottleSettings`

• **resolver?**

#### Returns

[`MemoizeThrottledFunction`](../interfaces/MemoizeThrottledFunction.md)\<`F`\>

***

### merge()

> `static` **merge**: \<`TObject`, `TSource`\>(`object`, `source`) => `TObject` & `TSource`\<`TObject_1`, `TSource1`, `TSource2`\>(`object`, `source1`, `source2`) => `TObject_1` & `TSource1` & `TSource2`\<`TObject_2`, `TSource1_1`, `TSource2_1`, `TSource3`\>(`object`, `source1`, `source2`, `source3`) => `TObject_2` & `TSource1_1` & `TSource2_1` & `TSource3`\<`TObject_3`, `TSource1_2`, `TSource2_2`, `TSource3_1`, `TSource4`\>(`object`, `source1`, `source2`, `source3`, `source4`) => `TObject_3` & `TSource1_2` & `TSource2_2` & `TSource3_1` & `TSource4`(`object`, ...`otherArgs`) => `any`

#### Type Parameters

• **TObject**

• **TSource**

#### Parameters

• **object**: `TObject`

• **source**: `TSource`

#### Returns

`TObject` & `TSource`

#### Type Parameters

• **TObject_1**

• **TSource1**

• **TSource2**

#### Parameters

• **object**: `TObject_1`

• **source1**: `TSource1`

• **source2**: `TSource2`

#### Returns

`TObject_1` & `TSource1` & `TSource2`

#### Type Parameters

• **TObject_2**

• **TSource1_1**

• **TSource2_1**

• **TSource3**

#### Parameters

• **object**: `TObject_2`

• **source1**: `TSource1_1`

• **source2**: `TSource2_1`

• **source3**: `TSource3`

#### Returns

`TObject_2` & `TSource1_1` & `TSource2_1` & `TSource3`

#### Type Parameters

• **TObject_3**

• **TSource1_2**

• **TSource2_2**

• **TSource3_1**

• **TSource4**

#### Parameters

• **object**: `TObject_3`

• **source1**: `TSource1_2`

• **source2**: `TSource2_2`

• **source3**: `TSource3_1`

• **source4**: `TSource4`

#### Returns

`TObject_3` & `TSource1_2` & `TSource2_2` & `TSource3_1` & `TSource4`

#### Parameters

• **object**: `any`

• ...**otherArgs**: `any`[]

#### Returns

`any`

***

### Promise

> `static` **Promise**: `PromiseConstructor`

***

### requestAnimationFrame

> `static` **requestAnimationFrame**: (`callback`) => `number` & (`callback`) => `number`

***

### set()

> `static` **set**: \<`T`\>(`object`, `path`, `value`) => `T`\<`TResult`\>(`object`, `path`, `value`) => `TResult`

#### Type Parameters

• **T** *extends* `object`

#### Parameters

• **object**: `T`

• **path**: `PropertyPath`

• **value**: `any`

#### Returns

`T`

#### Type Parameters

• **TResult**

#### Parameters

• **object**: `object`

• **path**: `PropertyPath`

• **value**: `any`

#### Returns

`TResult`

***

### setInterval

> `static` **setInterval**: (`handler`, `timeout`?, ...`arguments`) => `number` & *typeof* `setInterval`

***

### setTimeout

> `static` **setTimeout**: (`handler`, `timeout`?, ...`arguments`) => `number` & *typeof* `setTimeout`

***

### stringify

> `static` **stringify**: `any`

***

### throttle()

> `static` **throttle**: \<`T`\>(`func`, `wait`?, `options`?) => `DebouncedFunc`\<`T`\>

#### Type Parameters

• **T** *extends* (...`args`) => `any`

#### Parameters

• **func**: `T`

• **wait?**: `number`

• **options?**: `ThrottleSettings`

#### Returns

`DebouncedFunc`\<`T`\>

***

### uniq()

> `static` **uniq**: \<`T`\>(`array`) => `T`[]

#### Type Parameters

• **T**

#### Parameters

• **array**: `List`\<`T`\>

#### Returns

`T`[]

## Methods

### abortGettingAudioContexts()

> `static` **abortGettingAudioContexts**(): `void`

#### Returns

`void`

***

### arraysEqual()

> `static` **arraysEqual**\<`T`\>(`a`, `b`, `comparator`?): `boolean`

#### Type Parameters

• **T**

#### Parameters

• **a**: `T`[]

• **b**: `T`[]

• **comparator?**

#### Returns

`boolean`

***

### assertUnreachable()

> `static` **assertUnreachable**(`param`): `never`

#### Parameters

• **param**: `never`

#### Returns

`never`

***

### asyncDefer()

> `static` **asyncDefer**(): `Promise`\<`void`\>

This basically is a queueMicrotask in a promise so effectively we can await queueMicrotask

#### Returns

`Promise`\<`void`\>

***

### blobToFile()

> `static` **blobToFile**(`blob`, `fileName`): `File`

#### Parameters

• **blob**: `Blob`

• **fileName**: `string`

#### Returns

`File`

***

### calculateAspectRatio()

> `static` **calculateAspectRatio**(`srcWidth`, `srcHeight`, `targetWidth`, `targetHeight`, `cover`?): `number`

#### Parameters

• **srcWidth**: `any`

• **srcHeight**: `any`

• **targetWidth**: `any`

• **targetHeight**: `any`

• **cover?**: `boolean`

#### Returns

`number`

***

### calculateAspectRatioFit()

> `static` **calculateAspectRatioFit**(`srcWidth`, `srcHeight`, `targetWidth`, `targetHeight`, `cover`?): `object`

#### Parameters

• **srcWidth**: `any`

• **srcHeight**: `any`

• **targetWidth**: `any`

• **targetHeight**: `any`

• **cover?**: `boolean`

#### Returns

`object`

##### height

> **height**: `number`

##### width

> **width**: `number`

***

### canvasToBlob()

> `static` **canvasToBlob**(`canvas`, `mimetype`?, `quality`?): `Promise`\<`Blob`\>

#### Parameters

• **canvas**: `HTMLCanvasElement`

• **mimetype?**: `string`

• **quality?**: `number`

#### Returns

`Promise`\<`Blob`\>

***

### capitalize()

> `static` **capitalize**(`s`): `string`

#### Parameters

• **s**: `string`

#### Returns

`string`

***

### clone()

> `static` **clone**\<`T`\>(`obj`): `T`

#### Type Parameters

• **T**

#### Parameters

• **obj**: `T`

#### Returns

`T`

***

### createOffscreenCanvas()

> `static` **createOffscreenCanvas**(`width`, `height`): `OffscreenCanvas` \| `HTMLCanvasElement`

#### Parameters

• **width**: `number`

• **height**: `number`

#### Returns

`OffscreenCanvas` \| `HTMLCanvasElement`

***

### createStyleElementFromJson()

> `static` **createStyleElementFromJson**(`cssData`, `prefixClass`): `HTMLStyleElement`

#### Parameters

• **cssData**: `any`

• **prefixClass**: `string`

#### Returns

`HTMLStyleElement`

***

### createWorker()

> `static` **createWorker**(`func`): `Worker`

#### Parameters

• **func**

#### Returns

`Worker`

***

### dataURItoBlob()

> `static` **dataURItoBlob**(`dataURI`): `Blob`

#### Parameters

• **dataURI**: `string`

#### Returns

`Blob`

***

### dataURItoFile()

> `static` **dataURItoFile**(`dataURI`, `fileName`): `File`

#### Parameters

• **dataURI**: `string`

• **fileName**: `string`

#### Returns

`File`

***

### dateToFormattedString()

> `static` **dateToFormattedString**(`date`): `string`

#### Parameters

• **date**: `Date`

#### Returns

`string`

***

### dayOfTheYear()

> `static` **dayOfTheYear**(): `number`

#### Returns

`number`

***

### deepMap()

> `static` **deepMap**(`obj`, `iterator`, `accumulatedKey`?, `context`?): `unknown`

#### Parameters

• **obj**: `any`

• **iterator**

• **accumulatedKey?**: `string`

• **context?**: `any`

#### Returns

`unknown`

***

### deepMapNoArray()

> `static` **deepMapNoArray**(`obj`, `iterator`, `accumulatedKey`?, `context`?): `unknown`

#### Parameters

• **obj**: `any`

• **iterator**

• **accumulatedKey?**: `string`

• **context?**: `any`

#### Returns

`unknown`

***

### defer()

> `static` **defer**(`fn`): `void`

#### Parameters

• **fn**

#### Returns

`void`

***

### doDownloadFile()

> `static` **doDownloadFile**(`url`, `filename`?): `Promise`\<`void`\>

#### Parameters

• **url**: `string`

• **filename?**: `string`

#### Returns

`Promise`\<`void`\>

***

### downloadBlob()

> `static` **downloadBlob**(`blob`, `filename`): `void`

#### Parameters

• **blob**: `Blob`

• **filename**: `string`

#### Returns

`void`

***

### downloadFile()

> `static` **downloadFile**(`url`, `filename`?): `Promise`\<`void`\>

#### Parameters

• **url**: `string`

• **filename?**: `string`

#### Returns

`Promise`\<`void`\>

***

### enterFullscreen()

> `static` **enterFullscreen**(): `void`

#### Returns

`void`

***

### escapeHTML()

> `static` **escapeHTML**(`str`): `string`

#### Parameters

• **str**: `any`

#### Returns

`string`

***

### escapeRegex()

> `static` **escapeRegex**(`str`): `any`

#### Parameters

• **str**: `any`

#### Returns

`any`

***

### executeWhen()

> `static` **executeWhen**(`condition`, `action`, `checkIntervalMs`?, `timeoutMs`?): `void`

the condition function result is checked for truthiness if a single value is returned
 and for values being non-null in case it returns an array

#### Parameters

• **condition**

• **action**

• **checkIntervalMs?**: `number`

• **timeoutMs?**: `number`

#### Returns

`void`

***

### exitFullscreen()

> `static` **exitFullscreen**(): `void`

#### Returns

`void`

***

### extractGuid()

> `static` **extractGuid**(`str`): `string`

#### Parameters

• **str**: `string`

#### Returns

`string`

***

### generateCombinations()

> `static` **generateCombinations**(`arr`, `size`): `Generator`\<`any`, `void`, `any`\>

#### Parameters

• **arr**: `any`[]

• **size**: `number`

#### Returns

`Generator`\<`any`, `void`, `any`\>

***

### generatePairs()

> `static` **generatePairs**\<`T`\>(`arr`): `Generator`\<[`T`, `T`, `number`, `number`], `void`, `unknown`\>

#### Type Parameters

• **T** = `unknown`

#### Parameters

• **arr**: `T`[]

#### Returns

`Generator`\<[`T`, `T`, `number`, `number`], `void`, `unknown`\>

***

### getAudioContext()

> `static` **getAudioContext**(): `Promise`\<`AudioContext`\>

#### Returns

`Promise`\<`AudioContext`\>

***

### getDeviceData()

> `static` **getDeviceData**(): `IResult`

#### Returns

`IResult`

***

### getDisplayMedia()

> `static` **getDisplayMedia**(`constraints`): `Promise`\<`MediaStream`\>

#### Parameters

• **constraints**: `any`

#### Returns

`Promise`\<`MediaStream`\>

***

### getDomainFromUrl()

> `static` **getDomainFromUrl**(`url`): `string`

#### Parameters

• **url**: `string`

#### Returns

`string`

***

### getElementPosition()

> `static` **getElementPosition**(`el`): `object`

#### Parameters

• **el**: `any`

#### Returns

`object`

##### left

> **left**: `any`

##### top

> **top**: `any`

***

### getFileExtension()

> `static` **getFileExtension**(`fileName`): `string`

#### Parameters

• **fileName**: `string`

#### Returns

`string`

***

### getFileName()

> `static` **getFileName**(`fileName`): `string`

#### Parameters

• **fileName**: `string`

#### Returns

`string`

***

### getFileType()

> `static` **getFileType**(`mimetype`, `ext`?): [`FileSystemNodeClassifier`](../enumerations/FileSystemNodeClassifier.md)

#### Parameters

• **mimetype**: `string`

• **ext?**: `string`

#### Returns

[`FileSystemNodeClassifier`](../enumerations/FileSystemNodeClassifier.md)

***

### getFileTypeFromExtension()

> `static` **getFileTypeFromExtension**(`ext`): [`FileSystemNodeClassifier`](../enumerations/FileSystemNodeClassifier.md)

#### Parameters

• **ext**: `any`

#### Returns

[`FileSystemNodeClassifier`](../enumerations/FileSystemNodeClassifier.md)

***

### getFirstInSet()

> `static` **getFirstInSet**\<`T`\>(`s`?): `T`

#### Type Parameters

• **T**

#### Parameters

• **s?**: `Set`\<`T`\>

#### Returns

`T`

***

### getImageSize()

> `static` **getImageSize**(`url`, `crossOrigin`?): `Promise`\<`object`\>

#### Parameters

• **url**: `string`

• **crossOrigin?**: `"use-credentials"` \| `"anonymous"`

#### Returns

`Promise`\<`object`\>

##### height

> **height**: `number`

##### width

> **width**: `number`

***

### getInitials()

> `static` **getInitials**(`str`): `string`

#### Parameters

• **str**: `string`

#### Returns

`string`

***

### getLocale()

> `static` **getLocale**(): `string`

#### Returns

`string`

***

### getMimetype()

> `static` **getMimetype**(`file`): `Promise`\<`any`\>

#### Parameters

• **file**: `File`

#### Returns

`Promise`\<`any`\>

***

### getObjectFromQuery()

> `static` **getObjectFromQuery**(`queryStr`): `any`

#### Parameters

• **queryStr**: `string`

#### Returns

`any`

***

### getPasteAsString()

> `static` **getPasteAsString**(`item`): `Promise`\<`object`\>

#### Parameters

• **item**: `Blob` \| `DataTransferItem`

#### Returns

`Promise`\<`object`\>

##### data

> **data**: `string`

##### type

> **type**: `string`

***

### getPreferredAudioFormat()

> `static` **getPreferredAudioFormat**(): `"mp3"` \| `"ogg"` \| `"wav"`

#### Returns

`"mp3"` \| `"ogg"` \| `"wav"`

***

### getScreenResolution()

> `static` **getScreenResolution**(): `string`

#### Returns

`string`

***

### getToplevelDomainFromUrl()

> `static` **getToplevelDomainFromUrl**(`url`): `string`

#### Parameters

• **url**: `string`

#### Returns

`string`

***

### getVideoSizeFromUrl()

> `static` **getVideoSizeFromUrl**(`url`, ...`additionalCacheKeys`): `Promise`\<`object`\>

#### Parameters

• **url**: `string`

• ...**additionalCacheKeys**: `any`[]

#### Returns

`Promise`\<`object`\>

##### height

> **height**: `number`

##### width

> **width**: `number`

***

### hashColor()

> `static` **hashColor**(`str`, `startColor`?): `string`

#### Parameters

• **str**: `string`

• **startColor?**: `string`

#### Returns

`string`

***

### hashObject()

> `static` **hashObject**(`object`): `number`

#### Parameters

• **object**: `any`

#### Returns

`number`

***

### hashString()

> `static` **hashString**(`key`, `seed`?): `number`

#### Parameters

• **key**: `string`

• **seed?**: `string`

#### Returns

`number`

***

### hasMaybeDevConsoleDocked()

> `static` **hasMaybeDevConsoleDocked**(): `boolean`

#### Returns

`boolean`

***

### imageToBlob()

> `static` **imageToBlob**(`img`): `Promise`\<`Blob`\>

#### Parameters

• **img**: `HTMLImageElement`

#### Returns

`Promise`\<`Blob`\>

***

### isApiError()

> `static` **isApiError**(`err`): `boolean`

#### Parameters

• **err**: `any`

#### Returns

`boolean`

***

### isApiErrorCode()

> `static` **isApiErrorCode**(`err`, `code`, `subCode`?): `boolean`

#### Parameters

• **err**: `any`

• **code**: [`ApiResponseErrorCode`](../enumerations/ApiResponseErrorCode.md)

• **subCode?**: `any`

#### Returns

`boolean`

***

### isApiErrorHttpStatusCode()

> `static` **isApiErrorHttpStatusCode**(`err`, `code`): `boolean`

#### Parameters

• **err**: `any`

• **code**: `number`

#### Returns

`boolean`

***

### isDocumentVisible()

> `static` **isDocumentVisible**(): `boolean`

#### Returns

`boolean`

***

### isEdge()

> `static` **isEdge**(): `boolean`

#### Returns

`boolean`

***

### isEraserEvent()

> `static` **isEraserEvent**(`event`): `boolean`

#### Parameters

• **event**: `PointerEvent`

#### Returns

`boolean`

***

### isFirefox()

> `static` **isFirefox**(): `boolean`

#### Returns

`boolean`

***

### isGuid()

> `static` **isGuid**(`str`): `boolean`

#### Parameters

• **str**: `string`

#### Returns

`boolean`

***

### isInFullscreen()

> `static` **isInFullscreen**(): `boolean`

#### Returns

`boolean`

***

### isIpAddress()

> `static` **isIpAddress**(`str`): `boolean`

#### Parameters

• **str**: `string`

#### Returns

`boolean`

***

### isIPhone()

> `static` **isIPhone**(): `boolean`

#### Returns

`boolean`

***

### isJson()

> `static` **isJson**(`str`): `boolean`

#### Parameters

• **str**: `string`

#### Returns

`boolean`

***

### isMacOs()

> `static` **isMacOs**(): `boolean`

#### Returns

`boolean`

***

### isMobile()

> `static` **isMobile**(): `boolean`

#### Returns

`boolean`

***

### isMouse()

> `static` **isMouse**(`event`): `boolean`

#### Parameters

• **event**: `any`

#### Returns

`boolean`

***

### isPenAndNotEraser()

> `static` **isPenAndNotEraser**(`event`): `boolean`

#### Parameters

• **event**: `PointerEvent`

#### Returns

`boolean`

***

### isPenEvent()

> `static` **isPenEvent**(`event`): `boolean`

#### Parameters

• **event**: `PointerEvent` \| `MouseEvent` \| `TouchEvent`

#### Returns

`boolean`

***

### isPenRightClick()

> `static` **isPenRightClick**(`event`): `boolean`

#### Parameters

• **event**: `PointerEvent`

#### Returns

`boolean`

***

### isSafari()

> `static` **isSafari**(): `boolean`

#### Returns

`boolean`

***

### isTablet()

> `static` **isTablet**(): `boolean`

#### Returns

`boolean`

***

### isTextInputFocused()

> `static` **isTextInputFocused**(): `boolean`

#### Returns

`boolean`

***

### isTouchSupported()

> `static` **isTouchSupported**(): `boolean`

#### Returns

`boolean`

***

### isUriComponentEncoded()

> `static` **isUriComponentEncoded**(`uri`): `boolean`

#### Parameters

• **uri**: `string`

#### Returns

`boolean`

***

### isUrlAbsolute()

> `static` **isUrlAbsolute**(`url`): `boolean`

#### Parameters

• **url**: `string`

#### Returns

`boolean`

***

### isValidDomain()

> `static` **isValidDomain**(`domain`): `boolean`

#### Parameters

• **domain**: `string`

#### Returns

`boolean`

***

### jsonEqual()

> `static` **jsonEqual**(`a`, `b`): `boolean`

#### Parameters

• **a**: `unknown`

• **b**: `unknown`

#### Returns

`boolean`

***

### jsonEqualOmitFields()

> `static` **jsonEqualOmitFields**(...`fields`): (`a`, `b`) => `boolean`

#### Parameters

• ...**fields**: `string`[]

#### Returns

`Function`

##### Parameters

• **a**: `unknown`

• **b**: `unknown`

##### Returns

`boolean`

***

### jsonEqualPickFields()

> `static` **jsonEqualPickFields**(...`fields`): (`a`, `b`) => `boolean`

#### Parameters

• ...**fields**: `string`[]

#### Returns

`Function`

##### Parameters

• **a**: `unknown`

• **b**: `unknown`

##### Returns

`boolean`

***

### loadImage()

> `static` **loadImage**(`fileUrl`): `Promise`\<`HTMLImageElement`\>

#### Parameters

• **fileUrl**: `string`

#### Returns

`Promise`\<`HTMLImageElement`\>

***

### loadImageIntoBlob()

> `static` **loadImageIntoBlob**(`url`): `Promise`\<`string`\>

#### Parameters

• **url**: `string`

#### Returns

`Promise`\<`string`\>

***

### loadImageViaWorker()

> `static` **loadImageViaWorker**(`url`): `Promise`\<`unknown`\>

#### Parameters

• **url**: `string`

#### Returns

`Promise`\<`unknown`\>

***

### localDateTime()

> `static` **localDateTime**(): `string`

#### Returns

`string`

***

### lowerCaseEqual()

> `static` **lowerCaseEqual**(`a`, `b`): `boolean`

#### Parameters

• **a**: `string`

• **b**: `string`

#### Returns

`boolean`

***

### makeDate()

> `static` **makeDate**(`date`): `Date`

#### Parameters

• **date**: `Date`

#### Returns

`Date`

***

### map()

> `static` **map**(`x`, `inMin`, `inMax`, `outMin`, `outMax`): `number`

#### Parameters

• **x**: `number`

• **inMin**: `number`

• **inMax**: `number`

• **outMin**: `number`

• **outMax**: `number`

#### Returns

`number`

***

### newGuid()

> `static` **newGuid**(): `string`

#### Returns

`string`

***

### objectToQueryString()

> `static` **objectToQueryString**(`a`, `useArrayIndex`?, `useArrayBrackets`?): `string`

#### Parameters

• **a**: `any`

• **useArrayIndex?**: `boolean`

• **useArrayBrackets?**: `boolean`

#### Returns

`string`

***

### paramsToObject()

> `static` **paramsToObject**(`entries`): `any`

#### Parameters

• **entries**: `any`

#### Returns

`any`

***

### playMuteSound()

> `static` **playMuteSound**(`sinkId`?): `void`

This is a safari workaround to allow starting audio, if we need to start audio in an async callback after
user interaction it won't play unless we have played a sound synchronously inside event for a user interaction

#### Parameters

• **sinkId?**: `string`

#### Returns

`void`

***

### randomInt()

> `static` **randomInt**(`min`, `max`): `any`

#### Parameters

• **min**: `any`

• **max**: `any`

#### Returns

`any`

***

### randomStr()

> `static` **randomStr**(`length`): `string`

#### Parameters

• **length**: `number`

#### Returns

`string`

***

### readClipboardTextData()

> `static` **readClipboardTextData**(`type`?): `Promise`\<`any`\>

#### Parameters

• **type?**: `string`

#### Returns

`Promise`\<`any`\>

***

### readFileAsText()

> `static` **readFileAsText**(`file`): `Promise`\<`string`\>

#### Parameters

• **file**: `File`

#### Returns

`Promise`\<`string`\>

***

### relativeTimeTo()

> `static` **relativeTimeTo**(`to`): `string`

#### Parameters

• **to**: `Date`

#### Returns

`string`

***

### replaceInvalidFileNameChars()

> `static` **replaceInvalidFileNameChars**(`name`, `separator`?): `string`

#### Parameters

• **name**: `string`

• **separator?**: `string`

#### Returns

`string`

***

### retry()

> `static` **retry**\<`T`\>(`action`, `maxRetries`?, `retryAction`?, `retryCount`?): `Promise`\<`Awaited`\<`ReturnType`\<`T`\>\>\>

#### Type Parameters

• **T** *extends* (...`arg0`) => `any`

#### Parameters

• **action**: `T`

• **maxRetries?**: `number`

• **retryAction?**

• **retryCount?**: `number`

#### Returns

`Promise`\<`Awaited`\<`ReturnType`\<`T`\>\>\>

***

### selectFile()

> `static` **selectFile**(`allowedMimetypes`?, `multiple`?): `Promise`\<`false` \| `File` \| `File`[]\>

#### Parameters

• **allowedMimetypes?**: `string`

• **multiple?**: `boolean`

#### Returns

`Promise`\<`false` \| `File` \| `File`[]\>

***

### setPropertyIfChanged()

> `static` **setPropertyIfChanged**(`domEl`, `property`, `value`): `void`

#### Parameters

• **domEl**: `HTMLElement`

• **property**: `string`

• **value**: `string`

#### Returns

`void`

***

### sleep()

> `static` **sleep**(`ms`?): `Promise`\<`unknown`\>

#### Parameters

• **ms?**: `any`

#### Returns

`Promise`\<`unknown`\>

***

### smoothstep()

> `static` **smoothstep**(`min`, `max`, `value`): `number`

#### Parameters

• **min**: `number`

• **max**: `number`

• **value**: `number`

#### Returns

`number`

***

### toEnumIgnoreCase()

> `static` **toEnumIgnoreCase**\<`T`\>(`target`, `key`): `T`\[keyof `T`\]

#### Type Parameters

• **T**

#### Parameters

• **target**: `T`

• **key**: `string`

#### Returns

`T`\[keyof `T`\]

***

### toMaxPrecision()

> `static` **toMaxPrecision**(`n`, `precision`): `string`

#### Parameters

• **n**: `number`

• **precision**: `number`

#### Returns

`string`

***

### trim()

> `static` **trim**(`s`, `c`): `any`

#### Parameters

• **s**: `any`

• **c**: `any`

#### Returns

`any`

***

### truncate()

> `static` **truncate**(`str`, `n`): `string`

#### Parameters

• **str**: `string`

• **n**: `number`

#### Returns

`string`

***

### unCapitalize()

> `static` **unCapitalize**(`s`): `string`

#### Parameters

• **s**: `string`

#### Returns

`string`

***

### uuidv4()

> `static` **uuidv4**(): `string`

#### Returns

`string`

***

### waitUntil()

> `static` **waitUntil**(`condition`, `checkIntervalMs`?, `timeoutMs`?): `Promise`\<`any`\>

the condition function result is checked for truthiness if a single value is returned
 and for values being non-null in case it returns an array

#### Parameters

• **condition**

• **checkIntervalMs?**: `number`

• **timeoutMs?**: `number`

#### Returns

`Promise`\<`any`\>

***

### waitWithTimeout()

> `static` **waitWithTimeout**\<`T`\>(`promise`, `ms`, `timeoutError`?): `Promise`\<`T`\>

#### Type Parameters

• **T**

#### Parameters

• **promise**: `Promise`\<`T`\>

• **ms**: `number`

• **timeoutError?**: `Error`

#### Returns

`Promise`\<`T`\>

***

### wildcardToRegexp()

> `static` **wildcardToRegexp**(`str`): `RegExp`

#### Parameters

• **str**: `string`

#### Returns

`RegExp`

***

### writeClipboardData()

> `static` **writeClipboardData**(`item`, `successNotification`?): `Promise`\<`boolean`\>

#### Parameters

• **item**: `ClipboardItem` \| `Partial`\<`object` & `Record`\<[`BoardClipboardMimeType`](../enumerations/BoardClipboardMimeType.md), `any`\>\>

• **successNotification?**: `string`

#### Returns

`Promise`\<`boolean`\>

***

### writeClipboardText()

> `static` **writeClipboardText**(`text`, `successNotification`?): `Promise`\<`boolean`\>

#### Parameters

• **text**: `string`

• **successNotification?**: `string`

#### Returns

`Promise`\<`boolean`\>
