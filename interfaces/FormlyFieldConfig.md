[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / FormlyFieldConfig

# Interface: FormlyFieldConfig\<Props\>

## Type Parameters

• **Props** = [`FormlyFieldProps`](FormlyFieldProps.md) & `object`

## Properties

### asyncValidators?

> `optional` **asyncValidators**: [`FormlyValidation`](FormlyValidation.md)\<`AsyncValidatorFn`, `Promise`\<`boolean`\> \| `Observable`\<`boolean`\>\>

Use this one for anything that needs to validate asynchronously.
Pretty much exactly the same as the validators api, except it must be a function that returns a promise.

***

### className?

> `optional` **className**: `string`

You can specify your own class that will be applied to the `formly-field` component.

***

### defaultValue?

> `optional` **defaultValue**: `any`

Use `defaultValue` to initialize it the model. If this is provided and the value of the model at compile-time is undefined, then the value of the model will be assigned to `defaultValue`.

***

### ~~expressionProperties?~~

> `optional` **expressionProperties**: `object`

An object where the key is a property to be set on the main field config and the value is an expression used to assign that property.

#### Index Signature

 \[`property`: `string`\]: `string` \| (`model`, `formState`, `field`?) => `any` \| `Observable`\<`any`\>

#### Deprecated

use `expressions`

***

### expressions?

> `optional` **expressions**: `object`

An object where the key is a property to be set on the main field config and the value is an expression used to assign that property.

#### Index Signature

 \[`property`: `string`\]: `string` \| (`field`) => `any` \| `Observable`\<`any`\>

***

### fieldArray?

> `optional` **fieldArray**: [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\> \| (`field`) => [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

***

### fieldGroup?

> `optional` **fieldGroup**: [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>[]

A field group is a way to group fields together, making advanced layout very simple.
It can also be used to group fields that are associated with the same model (useful if it's different than the model for the rest of the fields).

***

### fieldGroupClassName?

> `optional` **fieldGroupClassName**: `string`

Specify your own class that will be applied to the `formly-group` component.

***

### focus?

> `optional` **focus**: `boolean`

Whether to focus or blur the element field. Defaults to false. If you wish this to be conditional use `expressions`

***

### form?

> `readonly` `optional` **form**: `FormGroup`\<`any`\> \| `FormArray`\<`any`\>

The parent form.

***

### formControl?

> `readonly` `optional` **formControl**: `AbstractControl`\<`any`, `any`\>

This is the [FormControl](https://angular.io/api/forms/FormControl) for the field.
It provides you more control like running validators, calculating status, and resetting state.

***

### get()?

> `optional` **get**: (`key`) => [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

Returns child field by key name

#### Parameters

• **key**: `string` \| `number` \| (`string` \| `number`)[]

#### Returns

[`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

***

### hide?

> `optional` **hide**: `boolean`

Whether to hide the field. Defaults to false. If you wish this to be conditional use `expressions: { hide: ... }`

***

### ~~hideExpression?~~

> `optional` **hideExpression**: `string` \| `boolean` \| (`model`, `formState`, `field`?) => `boolean`

Conditionally hiding Field based on values from other Fields

#### Deprecated

use `expressions: { hide: ... }`

***

### hooks?

> `optional` **hooks**: [`FormlyHookConfig`](FormlyHookConfig.md)

***

### id?

> `optional` **id**: `string`

This allows you to specify the `id` of your field. Note, the `id` is generated if not set.

***

### key?

> `optional` **key**: `string` \| `number` \| (`string` \| `number`)[]

The key that relates to the model. This will link the field value to the model

***

### model?

> `readonly` `optional` **model**: `any`

The model that stores all the data, where the model[key] is the value of the field

***

### modelOptions?

> `optional` **modelOptions**: `object`

An object with a few useful properties to control the model changes
- `debounce`: integer value which contains the debounce model update value in milliseconds. A value of 0 triggers an immediate update.
- `updateOn`: string event value that instructs when the control should be updated

#### debounce?

> `optional` **debounce**: `object`

#### debounce.default

> **default**: `number`

#### updateOn?

> `optional` **updateOn**: `"blur"` \| `"change"` \| `"submit"`

***

### name?

> `optional` **name**: `string`

If you wish, you can specify a specific `name` for your field. This is useful if you're posting the form to a server using techniques of yester-year.

***

### options?

> `readonly` `optional` **options**: [`FormlyFormOptions`](FormlyFormOptions.md)

The form options.

***

### ~~optionsTypes?~~

> `optional` **optionsTypes**: `string`[]

#### Deprecated

***

### parent?

> `readonly` `optional` **parent**: [`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>

The parent field.

***

### parsers?

> `optional` **parsers**: (`value`) => `any`[]

Array of functions to execute, as a pipeline, whenever the model updates, usually via user input.

***

### props?

> `optional` **props**: `Props`

This is reserved for the templates. Any template-specific options go in here. Look at your specific template implementation to know the options required for this.

***

### resetOnHide?

> `optional` **resetOnHide**: `boolean`

Whether to reset the value on hide or not. Defaults to `true`.

***

### template?

> `optional` **template**: `string`

Can be set instead of `type` to render custom html content.

***

### ~~templateOptions?~~

> `optional` **templateOptions**: [`FormlyTemplateOptions`](FormlyTemplateOptions.md)

#### Deprecated

Use `props` instead.

***

### type?

> `optional` **type**: `string` \| `Type`\<`FieldType`\<[`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>\>\>

This should be a formly-field type added either by you or a plugin. More information over at Creating Formly Fields.

***

### validation?

> `optional` **validation**: `object`

An object with a few useful properties
- `validation.messages`: A map of message names that will be displayed when the field has errors.
- `validation.show`: A boolean you as the developer can set to force displaying errors whatever the state of field. This is useful when you're trying to call the user's attention to some fields for some reason.

#### Index Signature

 \[`additionalProperties`: `string`\]: `any`

#### messages?

> `optional` **messages**: `object` & `object`

##### Type declaration

###### ~~maxlength?~~

> `optional` **maxlength**: `string` \| (`error`, `field`) => `string` \| `Observable`\<`string`\>

###### Deprecated

use `maxLength`

###### ~~minlength?~~

> `optional` **minlength**: `string` \| (`error`, `field`) => `string` \| `Observable`\<`string`\>

###### Deprecated

use `minLength`

#### show?

> `optional` **show**: `boolean`

***

### validators?

> `optional` **validators**: [`FormlyValidation`](FormlyValidation.md)\<`ValidatorFn`, `boolean`\>

Used to set validation rules for a particular field.
Should be an object of key - value pairs. The value can either be an expression to evaluate or a function to run.
Each should return a boolean value, returning true when the field is valid. See Validation for more information.

***

### wrappers?

> `optional` **wrappers**: (`string` \| `Type`\<`FieldWrapper`\<[`FormlyFieldConfig`](FormlyFieldConfig.md)\<[`FormlyFieldProps`](FormlyFieldProps.md) & `object`\>\>\>)[]

It is expected to be the name of the wrappers.
 The formly field template will be wrapped by the first wrapper, then the second, then the third, etc.
 You can also specify these as part of a type (which is the recommended approach).
