[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / BackendProxyHelper

# Class: BackendProxyHelper

BackendHelper class provides methods to handle backend requests.

It provides an interface to request data from the backend using the shared secret key.

## Constructors

### Constructor

> **new BackendProxyHelper**(`connectionId`): `BackendProxyHelper`

Creates an instance of BackendHelper.

#### Parameters

##### connectionId

`string` = `'default'`

the connection ID, as referenced in the DeploymentSettings.

#### Returns

`BackendProxyHelper`

## Properties

### cachedToken

> `protected` **cachedToken**: `string` = `undefined`

***

### connectionId

> `readonly` **connectionId**: `string` = `'default'`

the connection ID, as referenced in the DeploymentSettings.

## Accessors

### customKeyHandler

#### Get Signature

> **get** **customKeyHandler**(): `string`

##### Returns

`string`

***

### options

#### Get Signature

> **get** **options**(): `FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

***

### scope

#### Get Signature

> **get** **scope**(): [`BackendKeyConfigurationScope`](../enumerations/BackendKeyConfigurationScope.md)

Returns the currently used secret scope.

##### Warning

TODO This does not recognizes organization keys, and reports them as 'deployment'

##### Returns

[`BackendKeyConfigurationScope`](../enumerations/BackendKeyConfigurationScope.md)

#### Set Signature

> **set** **scope**(`value`): `void`

##### Parameters

###### value

[`BackendKeyConfigurationScope`](../enumerations/BackendKeyConfigurationScope.md)

##### Returns

`void`

***

### scopeHandler

#### Get Signature

> **get** **scopeHandler**(): `string`

##### Returns

`string`

## Methods

### getStatus()

> **getStatus**(): `Promise`\<`boolean`\>

#### Returns

`Promise`\<`boolean`\>

***

### getToken()

> `protected` **getToken**(): `Promise`\<`string`\>

Retrieves the authorization token, either from cache or by requesting a new one.

#### Returns

`Promise`\<`string`\>

- The authorization token.

#### Throws

Will throw an error if no key or provider is found for the shared secret, or if the token cannot be retrieved.

***

### request()

> **request**(`url`, `params`?, `doNotRetry`?): `Promise`\<`Response`\>

Makes a request to the specified URL with the provided parameters.
Retries the request once if the token is expired.

#### Parameters

##### url

`string`

The URL to request.

##### params?

`Omit`\<`RequestInit`, `"credentials"` \| `"mode"`\> = `...`

The request parameters.

##### doNotRetry?

`boolean` = `false`

Flag to indicate if the request should not be retried.

#### Returns

`Promise`\<`Response`\>

- The response from the request.

#### Throws

Will throw an error if the request fails and doNotRetry is true.

***

### requestJson()

> **requestJson**\<`T`\>(`url`, `params`?): `Promise`\<`T`\>

Makes a request to the specified URL and returns the JSON response.

#### Type Parameters

##### T

`T`

#### Parameters

##### url

`string`

The URL to request.

##### params?

`Omit`\<`RequestInit`, `"credentials"` \| `"mode"`\> = `...`

The request parameters.

#### Returns

`Promise`\<`T`\>

- The parsed JSON response from the request.

#### Throws

Will throw an error if the response is not successful.

***

### getAuthorizationToken()

> `static` **getAuthorizationToken**(`id`): `Promise`\<`any`\>

#### Parameters

##### id

`string`

#### Returns

`Promise`\<`any`\>

***

### getAuthorizationTokenForObject()

> `static` **getAuthorizationTokenForObject**(`id`): `Promise`\<`any`\>

#### Parameters

##### id

`string`

#### Returns

`Promise`\<`any`\>

***

### listSecretsAvailableForBoard()

> `static` **listSecretsAvailableForBoard**(`id`): `Promise`\<`any`\>

#### Parameters

##### id

`string`

#### Returns

`Promise`\<`any`\>

***

### proxyRequest()

> `static` **proxyRequest**(`url`, `token`, `params`): `Promise`\<`any`\>

#### Parameters

##### url

`string`

##### token

`string`

##### params

`Omit`\<`RequestInit`, `"credentials"` \| `"mode"`\>

#### Returns

`Promise`\<`any`\>
