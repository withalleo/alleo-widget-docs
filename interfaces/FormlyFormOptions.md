[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / FormlyFormOptions

# Interface: FormlyFormOptions

## Properties

### build()?

> `optional` **build**: (`field`?) => [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

#### Parameters

• **field?**: [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

#### Returns

[`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

***

### checkExpressions()?

> `optional` **checkExpressions**: (`field`) => `void`

#### Parameters

• **field**: [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

#### Returns

`void`

***

### detectChanges()?

> `optional` **detectChanges**: (`field`) => `void`

#### Parameters

• **field**: [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

#### Returns

`void`

***

### fieldChanges?

> `optional` **fieldChanges**: `Subject`\<[`FormlyValueChangeEvent`](FormlyValueChangeEvent.md)\>

***

### formState?

> `optional` **formState**: `any`

***

### parentForm?

> `optional` **parentForm**: `FormGroupDirective`

***

### resetModel()?

> `optional` **resetModel**: (`model`?) => `void`

#### Parameters

• **model?**: `any`

#### Returns

`void`

***

### showError()?

> `optional` **showError**: (`field`) => `boolean`

#### Parameters

• **field**: `FieldType`\<[`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>\>

#### Returns

`boolean`

***

### updateInitialValue()?

> `optional` **updateInitialValue**: (`model`?) => `void`

#### Parameters

• **model?**: `any`

#### Returns

`void`
