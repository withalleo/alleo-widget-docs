[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / BackendProxyHelper

# Class: BackendProxyHelper

Manages secure backend API connections with automatic authentication and token management.

Provides a comprehensive interface for making authenticated requests to backend services,
handling API key management at deployment/organization/custom scopes, token caching,
and settings UI generation. Supports multiple authentication scopes and automatic
token refresh. Essential for widgets that need to communicate with external APIs securely.

## Example

```typescript
// Initialize with connection ID from manifest
const backend = new BackendProxyHelper('myApiConnection');

// Make authenticated GET request
const data = await backend.get('/api/users');

// Make POST request with body
const result = await backend.post('/api/data', { name: 'John' });

// Check connection status
if (backend.isKeyConfigured()) {
  console.log('API key is configured');
}
```

## Constructors

### Constructor

> **new BackendProxyHelper**(`connectionId?`, `helperSettings?`): `BackendProxyHelper`

Creates a BackendProxyHelper instance for managing authenticated backend connections.

Sets up token caching, scope management, and watches for API key changes.
The connection ID should match a backend configuration defined in the widget's
deployment settings.

#### Parameters

##### connectionId?

`string` = `'default'`

The connection identifier from deployment settings matching the backend configuration.

##### helperSettings?

`BackendProxyHelperSettings` = `{}`

Additional configuration options.

#### Returns

`BackendProxyHelper`

## Properties

### cachedToken

> `protected` **cachedToken**: `string` = `undefined`

***

### connectionId

> `readonly` **connectionId**: `string` = `'default'`

The connection identifier from deployment settings matching the backend configuration.

***

### helperSettings

> `protected` `readonly` **helperSettings**: `BackendProxyHelperSettings` = `{}`

Additional configuration options.

***

### defaultTimeoutInMs

> `readonly` `static` **defaultTimeoutInMs**: `number`

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

### getStatusDisplay()

> **getStatusDisplay**(`serviceDisplayName?`): `FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

#### Parameters

##### serviceDisplayName?

`string` = `''`

#### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & `object`\>[]

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

> **request**(`url`, `params?`, `retryNumber?`, `timeoutMs?`): `Promise`\<`Response`\>

Makes a request to the specified URL with the provided parameters.
Retries the request once if the token is expired.

#### Parameters

##### url

`string`

The URL to request.

##### params?

`Omit`\<`RequestInit`, `"credentials"` \| `"mode"`\> = `...`

The request parameters.

##### retryNumber?

`number` \| `boolean`

The number of retries to attempt if the request fails. (set to 0 to disable retry)

##### timeoutMs?

`number` = `...`

The timeout in milliseconds for the request.

#### Returns

`Promise`\<`Response`\>

- The response from the request.

#### Throws

Will throw an error if the request fails and doNotRetry is true.

***

### requestJson()

> **requestJson**\<`T`\>(`url`, `params?`, `retryNumber?`, `timeoutMs?`, `returnContentOnError?`): `Promise`\<`T`\>

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

##### retryNumber?

`number` \| `boolean`

The number of retries to attempt if the request fails. (set to 0 to disable retry)

##### timeoutMs?

`number` = `...`

The timeout in milliseconds for the request.

##### returnContentOnError?

`boolean` = `false`

Whether to try to return the JSON on error responses.

#### Returns

`Promise`\<`T`\>

- The parsed JSON response from the request.

#### Throws

Will throw an error if the response is not successful.

***

### getAuthorizationToken()

> `static` **getAuthorizationToken**(`id`): `Promise`\<`OAuthTokenDto`\>

#### Parameters

##### id

`string`

#### Returns

`Promise`\<`OAuthTokenDto`\>

***

### getAuthorizationTokenForObject()

> `static` **getAuthorizationTokenForObject**(`id`): `Promise`\<`OAuthTokenDto`\>

#### Parameters

##### id

`string`

#### Returns

`Promise`\<`OAuthTokenDto`\>

***

### listSecretsAvailableForBoard()

> `static` **listSecretsAvailableForBoard**(`id`): `Promise`\<`ThirdPartyConnectionApiDto`[]\>

#### Parameters

##### id

`string`

#### Returns

`Promise`\<`ThirdPartyConnectionApiDto`[]\>

***

### proxyRequest()

> `static` **proxyRequest**(`url`, `token`, `params`): `Promise`\<`Response`\>

#### Parameters

##### url

`string`

##### token

`string`

##### params

`Omit`\<`RequestInit`, `"credentials"` \| `"mode"`\>

#### Returns

`Promise`\<`Response`\>
