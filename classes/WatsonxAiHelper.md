[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / WatsonxAiHelper

# Class: WatsonxAiHelper

## Constructors

### Constructor

> **new WatsonxAiHelper**(): `WatsonxAiHelper`

#### Returns

`WatsonxAiHelper`

## Properties

### backendApiKey

> `readonly` `static` **backendApiKey**: `string` = `DeploymentSettingsHelper.settings.ApiKey`

***

### backendUrl

> `readonly` `static` **backendUrl**: `string` = `DeploymentSettingsHelper.settings.ApiRoot`

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

> `readonly` `static` **enableCustomQueries**: `boolean` = `!DeploymentSettingsHelper.settings.DisableCustomQuery`

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

> **getChatResponse**(`messages`, `model`): `Promise`\<`string`\>

#### Parameters

##### messages

[`AiMessage`](../interfaces/AiMessage.md)[]

##### model

`string` = `...`

#### Returns

`Promise`\<`string`\>

***

### getDiscoveryResponse()

> **getDiscoveryResponse**(`query`, `region`, `collectionId`, `instanceId`, `projectId`, `wxProjectId`, `textEndpoint`): `Promise`\<`any`\>

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

##### wxProjectId

`string` = `...`

##### textEndpoint

`string` = `...`

#### Returns

`Promise`\<`any`\>

***

### getTextResponse()

> **getTextResponse**(`input`, `model`): `Promise`\<`string`\>

#### Parameters

##### input

`string`

##### model

`string` = `...`

#### Returns

`Promise`\<`string`\>
