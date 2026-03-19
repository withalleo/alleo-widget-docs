[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SoundRecordingHelper

# Class: SoundRecordingHelper

Manages audio recording from user's microphone with configurable constraints.

Provides simplified API for capturing audio using the MediaRecorder API, with automatic
handling of permissions, stream management, and blob generation. Supports minimum length
validation and auto-stop timers. Essential for widgets requiring voice input or audio
recording capabilities.

## Example

```typescript
// Basic audio recording
const recorder = new SoundRecordingHelper(
  (audioBlob) => {
    console.log('Recording complete:', audioBlob.size, 'bytes');
    // Upload or process the audio blob
    uploadAudio(audioBlob);
  },
  {
    waitForStop: 500,   // Wait 500ms before actually stopping
    minLength: 1000     // Require at least 1 second of audio
  }
);

// Start recording
await recorder.start();
console.log('Recording started...');

// Stop recording
await recorder.stop();
console.log('Recording stopped');

// Check if recording
if (recorder.isRecording) {
  console.log('Currently recording');
}
```

## Constructors

### Constructor

> **new SoundRecordingHelper**(`callback?`, `options?`): `SoundRecordingHelper`

Creates a SoundRecordingHelper for managing audio recording sessions.

#### Parameters

##### callback?

(`blob`) => `void`

Function invoked when recording completes, receives audio Blob.

##### options?

[`SoundRecordingHelperOptions`](../type-aliases/SoundRecordingHelperOptions.md) = `...`

Recording configuration.

#### Returns

`SoundRecordingHelper`

The new SoundRecordingHelper instance.

## Methods

### destroy()

> **destroy**(): `void`

Destroys the SoundRecordingHelper instance, and stops the recording if it is still running, without calling the callback.

#### Returns

`void`

***

### start()

> **start**(): `Promise`\<`void`\>

Initiates audio recording from the user's microphone.

Requests microphone permissions if needed and starts capturing audio.
Recording continues until stop() is called.

#### Returns

`Promise`\<`void`\>

Resolves when recording has started successfully.

***

### stop()

> **stop**(): `Promise`\<`void`\>

Stops recording sound. Stopping usually triggers the callback function with the recorded sound.

#### Returns

`Promise`\<`void`\>
