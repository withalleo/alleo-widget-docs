[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / WatsonxAiHelper

# Class: WatsonxAiHelper

Provides utilities and configurations for IBM Watsonx AI integration.

Offers standardized configuration, model selection, instruction management, and settings
dialogs for widgets using IBM Watsonx AI services. Includes predefined models, customizable
instructions, and form fields for AI configuration. Essential for widgets requiring
Watsonx AI capabilities with consistent configuration patterns.

## Example

```typescript
// Use default model and instructions
const model = WatsonxAiHelper.defaultModel;
const instructions = WatsonxAiHelper.defaultInstructions;

// Access enabled models for selection
const models = WatsonxAiHelper.EnabledModels;
console.log('Available models:', models);

// Use settings dialog fields in your widget
const settingsDialog = new SettingsDialogHelper({
  fields: [
    ...WatsonxAiHelper.settingsDialogFields,
    // Add your custom fields
    { key: 'myField', type: 'input', props: { label: 'My Setting' } }
  ]
});

// Create AI messages
const message: AiMessage = {
  type: AiMessageType.User,
  message: 'Hello, AI!'
};
```

## Constructors

### Constructor

> **new WatsonxAiHelper**(): `WatsonxAiHelper`

#### Returns

`WatsonxAiHelper`

## Properties

### backendApiKey

> `readonly` `static` **backendApiKey**: `string` = `WidgetSettings.settings.ApiKey`

***

### backendUrl

> `readonly` `static` **backendUrl**: `string` = `WidgetSettings.settings.ApiRoot`

***

### defaultInstructions

> `readonly` `static` **defaultInstructions**: [`Instruction`](../type-aliases/Instruction.md)[]

***

### defaultModel

> `readonly` `static` **defaultModel**: `string`

***

### defaultSharedVariables

> `readonly` `static` **defaultSharedVariables**: `object`

#### customModel

> **customModel**: `string`

#### customQuery

> **customQuery**: `string`

#### instruction

> **instruction**: `string`

***

### enableCustomQueries

> `readonly` `static` **enableCustomQueries**: `boolean` = `!WidgetSettings.settings.DisableCustomQuery`

***

### EnabledModels

> `readonly` `static` **EnabledModels**: [`ConfigDialogSetting`](../type-aliases/ConfigDialogSetting.md)[]

***

### settingsDialogFields

> `static` **settingsDialogFields**: `FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

## Accessors

### endpoint

#### Get Signature

> **get** **endpoint**(): `string`

##### Returns

`string`

***

### instruction

#### Get Signature

> **get** **instruction**(): `string`

##### Returns

`string`

***

### model

#### Get Signature

> **get** **model**(): `string`

##### Returns

`string`

***

### projectId

#### Get Signature

> **get** **projectId**(): `string`

##### Returns

`string`

***

### selectedInstruction

#### Get Signature

> **get** **selectedInstruction**(): [`Instruction`](../type-aliases/Instruction.md)

##### Returns

[`Instruction`](../type-aliases/Instruction.md)

***

### advancedSettings

#### Get Signature

> **get** `static` **advancedSettings**(): `FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

## Methods

### getChatResponse()

> **getChatResponse**(`messages`, `model?`): `Promise`\<`string`\>

#### Parameters

##### messages

[`AiMessage`](../interfaces/AiMessage.md)[]

##### model?

`string` = `...`

#### Returns

`Promise`\<`string`\>

***

### getDiscoveryResponse()

> **getDiscoveryResponse**(`query`, `region`, `collectionId`, `instanceId`, `projectId`, `wxProjectId?`, `textEndpoint?`): `Promise`\<`any`\>

#### Parameters

##### query

`string`

##### region

`string`

##### collectionId

`string`

##### instanceId

`string`

##### projectId

`string`

##### wxProjectId?

`string` = `...`

##### textEndpoint?

`string` = `...`

#### Returns

`Promise`\<`any`\>

***

### getTextResponse()

> **getTextResponse**(`input`, `model?`): `Promise`\<`string`\>

#### Parameters

##### input

`string`

##### model?

`string` = `...`

#### Returns

`Promise`\<`string`\>
