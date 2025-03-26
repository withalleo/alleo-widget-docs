[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SoundRecordingHelper

# Class: SoundRecordingHelper

Helper class for managing sound recording.

## Constructors

### Constructor

> **new SoundRecordingHelper**(`callback`, `options`): `SoundRecordingHelper`

#### Parameters

##### callback

(`blob`) => `void`

##### options

[`SoundRecordingHelperOptions`](../type-aliases/SoundRecordingHelperOptions.md) = `...`

#### Returns

`SoundRecordingHelper`

## Methods

### destroy()

> **destroy**(): `void`

Destroys the SoundRecordingHelper instance, and stops the recording if it is still running, without calling the callback.

#### Returns

`void`

***

### start()

> **start**(): `Promise`\<`void`\>

Starts recording sound.

#### Returns

`Promise`\<`void`\>

***

### stop()

> **stop**(): `Promise`\<`void`\>

Stops recording sound. Stopping usually triggers the callback function with the recorded sound.

#### Returns

`Promise`\<`void`\>
