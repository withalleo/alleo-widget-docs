[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / WatsonxAiHelper

# ~~Class: WatsonxAiHelper~~

Provides utilities and configurations for IBM Watsonx AI integration.

## Deprecated

Abandoned and considered insecure. Do not use for new development.
Switch to AlleoAiService.

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
console.log("Available models:", models);

// Use settings dialog fields in your widget
const settingsDialog = new SettingsDialogHelper({
  fields: [
    ...WatsonxAiHelper.settingsDialogFields,
    // Add your custom fields
    { key: "myField", type: "input", props: { label: "My Setting" } },
  ],
});

// Create AI messages
const message: AiMessage = {
  type: AiMessageType.User,
  message: "Hello, AI!",
};
```

## Constructors

### Constructor

```ts
new WatsonxAiHelper(): WatsonxAiHelper;
```

#### Returns

`WatsonxAiHelper`

## Properties

### ~~backendApiKey~~

```ts
readonly static backendApiKey: string = WidgetSettings.settings.ApiKey;
```

---

### ~~backendUrl~~

```ts
readonly static backendUrl: string = WidgetSettings.settings.ApiRoot;
```

---

### ~~defaultInstructions~~

```ts
readonly static defaultInstructions: Instruction[];
```

---

### ~~defaultModel~~

```ts
readonly static defaultModel: string;
```

---

### ~~defaultSharedVariables~~

```ts
readonly static defaultSharedVariables: {
  customModel: string;
  customQuery: string;
  instruction: string;
};
```

#### ~~customModel~~

```ts
customModel: string;
```

#### ~~customQuery~~

```ts
customQuery: string;
```

#### ~~instruction~~

```ts
instruction: string;
```

---

### ~~enableCustomQueries~~

```ts
readonly static enableCustomQueries: boolean = !WidgetSettings.settings.DisableCustomQuery;
```

---

### ~~EnabledModels~~

```ts
readonly static EnabledModels: ConfigDialogSetting[];
```

---

### ~~settingsDialogFields~~

```ts
static settingsDialogFields: FormlyFieldConfig<FormlyFieldProps & {
[additionalProperties: string]: any;
}>[];
```

## Accessors

### ~~endpoint~~

#### Get Signature

```ts
get endpoint(): string;
```

##### Returns

`string`

---

### ~~instruction~~

#### Get Signature

```ts
get instruction(): string;
```

##### Returns

`string`

---

### ~~model~~

#### Get Signature

```ts
get model(): string;
```

##### Returns

`string`

---

### ~~projectId~~

#### Get Signature

```ts
get projectId(): string;
```

##### Returns

`string`

---

### ~~selectedInstruction~~

#### Get Signature

```ts
get selectedInstruction(): Instruction;
```

##### Returns

[`Instruction`](../type-aliases/Instruction.md)

---

### ~~advancedSettings~~

#### Get Signature

```ts
get static advancedSettings(): FormlyFieldConfig<FormlyFieldProps & {
[additionalProperties: string]: any;
}>[];
```

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & \{
\[`additionalProperties`: `string`\]: `any`;
\}\>[]

## Methods

### ~~getChatResponse()~~

```ts
getChatResponse(messages: AiMessage[], model?: string): Promise<string>;
```

#### Parameters

| Parameter  | Type                                        |
| ---------- | ------------------------------------------- |
| `messages` | [`AiMessage`](../interfaces/AiMessage.md)[] |
| `model`    | `string`                                    |

#### Returns

`Promise`\<`string`\>

---

### ~~getDiscoveryResponse()~~

```ts
getDiscoveryResponse(
   query: string,
   region: string,
   collectionId: string,
   instanceId: string,
   projectId: string,
   wxProjectId?: string,
textEndpoint?: string): Promise<any>;
```

#### Parameters

| Parameter      | Type     |
| -------------- | -------- |
| `query`        | `string` |
| `region`       | `string` |
| `collectionId` | `string` |
| `instanceId`   | `string` |
| `projectId`    | `string` |
| `wxProjectId`  | `string` |
| `textEndpoint` | `string` |

#### Returns

`Promise`\<`any`\>

---

### ~~getTextResponse()~~

```ts
getTextResponse(input: string, model?: string): Promise<string>;
```

#### Parameters

| Parameter | Type     |
| --------- | -------- |
| `input`   | `string` |
| `model`   | `string` |

#### Returns

`Promise`\<`string`\>
