[**@withalleo/alleo-widget**](../README.md)

---

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
const backend = new BackendProxyHelper("myApiConnection");

// Make authenticated GET request
const response = await backend.request("/api/users");
const data = await response.json();

// Make POST request with JSON body and parse the response
const result = await backend.requestJson("/api/data", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ name: "John" }),
});

// Check connection status
if (await backend.getStatus()) {
  console.log("Connection is operational");
}
```

## Constructors

### Constructor

```ts
new BackendProxyHelper(connectionId?: string, helperSettings?: BackendProxyHelperSettings): BackendProxyHelper;
```

Creates a BackendProxyHelper instance for managing authenticated backend connections.

Sets up token caching, scope management, and watches for API key changes.
The connection ID should match a backend configuration defined in the widget's
deployment settings.

#### Parameters

| Parameter         | Type                                                                          | Default value | Description                                                                            |
| ----------------- | ----------------------------------------------------------------------------- | ------------- | -------------------------------------------------------------------------------------- |
| `connectionId?`   | `string`                                                                      | `'default'`   | The connection identifier from deployment settings matching the backend configuration. |
| `helperSettings?` | [`BackendProxyHelperSettings`](../type-aliases/BackendProxyHelperSettings.md) | `{}`          | Additional configuration options.                                                      |

#### Returns

`BackendProxyHelper`

## Properties

### cachedToken

```ts
protected cachedToken: string = undefined;
```

Cached authorization token. Cleared on scope or API key change and on expiry.

---

### connectionId

```ts
readonly connectionId: string = 'default';
```

The connection identifier from deployment settings matching the backend configuration.

---

### helperSettings

```ts
protected readonly helperSettings: BackendProxyHelperSettings = {};
```

Additional configuration options.

---

### optionListHideAdditionalCheck

```ts
optionListHideAdditionalCheck: (m: FormlyFieldConfig) => boolean;
```

Additional hide predicate evaluated for every settings UI field.
When it returns `true` the field is hidden. Reassign to conditionally suppress backend UI options.

#### Parameters

| Parameter | Type                |
| --------- | ------------------- |
| `m`       | `FormlyFieldConfig` |

#### Returns

`boolean`

---

### defaultTimeoutInMs

```ts
readonly static defaultTimeoutInMs: number;
```

Fallback timeout in milliseconds used for all proxy requests when no per-request timeout is specified.

## Accessors

### customKeyHandler

#### Get Signature

```ts
get customKeyHandler(): string;
```

Widget data field key used to persist and retrieve the custom API key for this connection.

##### Returns

`string`

---

### options

#### Get Signature

```ts
get options(): FormlyFieldConfig<FormlyFieldProps & {
[additionalProperties: string]: any;
}>[];
```

Formly field configurations for the backend connection settings panel.
Returns an empty array when `EnableUI` is `false` in deployment settings.

##### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & \{
\[`additionalProperties`: `string`\]: `any`;
\}\>[]

---

### scope

#### Get Signature

```ts
get scope(): BackendKeyConfigurationScope;
```

Returns the currently used secret scope.

##### Warning

TODO This does not recognizes organization keys, and reports them as 'deployment'

##### Returns

[`BackendKeyConfigurationScope`](../enumerations/BackendKeyConfigurationScope.md)

#### Set Signature

```ts
set scope(value: BackendKeyConfigurationScope): void;
```

##### Parameters

| Parameter | Type                                                                              |
| --------- | --------------------------------------------------------------------------------- |
| `value`   | [`BackendKeyConfigurationScope`](../enumerations/BackendKeyConfigurationScope.md) |

##### Returns

`void`

---

### scopeHandler

#### Get Signature

```ts
get scopeHandler(): string;
```

Widget data field key used to persist and retrieve the selected [BackendScope](../enumerations/BackendKeyConfigurationScope.md) for this connection.

##### Returns

`string`

---

### settings

#### Get Signature

```ts
get settings(): Required<BackendConfiguration>;
```

##### Returns

`Required`\<`BackendConfiguration`\>

#### Set Signature

```ts
set settings(value: Required<BackendConfiguration>): void;
```

##### Parameters

| Parameter | Type                                 |
| --------- | ------------------------------------ |
| `value`   | `Required`\<`BackendConfiguration`\> |

##### Returns

`void`

## Methods

### addAndConfigurePresetKey()

```ts
addAndConfigurePresetKey(): Promise<string>;
```

#### Returns

`Promise`\<`string`\>

---

### getStatus()

```ts
getStatus(): Promise<boolean>;
```

Returns `true` if a valid authorization token can be obtained for the current connection scope.

#### Returns

`Promise`\<`boolean`\>

---

### getStatusDisplay()

```ts
getStatusDisplay(serviceDisplayName?: string): FormlyFieldConfig<FormlyFieldProps & {
[additionalProperties: string]: any;
}>[];
```

Returns Formly field configurations for a status indicator showing whether the current connection is operational.
The indicator updates on init by attempting to retrieve a token.

#### Parameters

| Parameter             | Type     | Default value | Description                                           |
| --------------------- | -------- | ------------- | ----------------------------------------------------- |
| `serviceDisplayName?` | `string` | `''`          | Optional label shown alongside the connection status. |

#### Returns

`FormlyFieldConfig`\<`FormlyFieldProps` & \{
\[`additionalProperties`: `string`\]: `any`;
\}\>[]

Formly fields containing the status template.

---

### getToken()

```ts
protected getToken(): Promise<string>;
```

Retrieves the authorization token, either from cache or by requesting a new one.
Tokens are cached until they expire (with a 30-second safety margin).

#### Returns

`Promise`\<`string`\>

The authorization token.

#### Throws

If no key or provider is found for the configured shared secret, or if the token exchange fails.

---

### request()

```ts
request(
   url: string,
   params?: Omit<RequestInit, "credentials" | "mode">,
   retryNumber?: number | boolean,
timeoutMs?: number): Promise<Response>;
```

Makes an authenticated request to the specified URL through the backend proxy.
Automatically obtains and attaches an authorization token. Retries once on timeout
with an increased timeout (1.75×).

#### Parameters

| Parameter      | Type                                                 | Default value | Description                                                                                               |
| -------------- | ---------------------------------------------------- | ------------- | --------------------------------------------------------------------------------------------------------- |
| `url`          | `string`                                             | `undefined`   | The URL to request.                                                                                       |
| `params?`      | `Omit`\<`RequestInit`, `"credentials"` \| `"mode"`\> | `...`         | Standard fetch options (defaults to a JSON GET request).                                                  |
| `retryNumber?` | `number` \| `boolean`                                | `1`           | Number of retries on timeout. Pass `0` or `true` to disable retries. A boolean `false` is treated as `1`. |
| `timeoutMs?`   | `number`                                             | `...`         | Timeout in milliseconds. Defaults to the connection's configured timeout.                                 |

#### Returns

`Promise`\<`Response`\>

The proxied response.

#### Throws

If the authorization token cannot be obtained or the request fails after all retries.

---

### requestJson()

```ts
requestJson<T>(
   url: string,
   params?: Omit<RequestInit, "credentials" | "mode">,
   retryNumber?: number | boolean,
   timeoutMs?: number,
returnContentOnError?: boolean): Promise<T>;
```

Makes an authenticated request and returns the parsed JSON response.

#### Type Parameters

| Type Parameter |
| -------------- |
| `T`            |

#### Parameters

| Parameter               | Type                                                 | Default value | Description                                                                                                |
| ----------------------- | ---------------------------------------------------- | ------------- | ---------------------------------------------------------------------------------------------------------- |
| `url`                   | `string`                                             | `undefined`   | The URL to request.                                                                                        |
| `params?`               | `Omit`\<`RequestInit`, `"credentials"` \| `"mode"`\> | `...`         | Standard fetch options (defaults to a JSON GET request).                                                   |
| `retryNumber?`          | `number` \| `boolean`                                | `1`           | Number of retries on timeout. Pass `0` or `true` to disable retries.                                       |
| `timeoutMs?`            | `number`                                             | `...`         | Timeout in milliseconds. Defaults to the connection's configured timeout.                                  |
| `returnContentOnError?` | `boolean`                                            | `false`       | When `true`, attempts to parse and return the JSON body even on non-success responses instead of throwing. |

#### Returns

`Promise`\<`T`\>

The parsed JSON response body.

#### Throws

If the response is not successful (and `returnContentOnError` is `false`), or if the body cannot be parsed as JSON.

---

### getAuthorizationToken()

```ts
static getAuthorizationToken(id: string): Promise<OAuthTokenDto>;
```

Exchanges a secret provider ID for a time-limited authorization token.

#### Parameters

| Parameter | Type     | Description             |
| --------- | -------- | ----------------------- |
| `id`      | `string` | The secret provider ID. |

#### Returns

`Promise`\<`OAuthTokenDto`\>

---

### getAuthorizationTokenForObject()

```ts
static getAuthorizationTokenForObject(id: string): Promise<OAuthTokenDto>;
```

Exchanges a widget-object-scoped secret ID for a time-limited authorization token.

#### Parameters

| Parameter | Type     | Description                  |
| --------- | -------- | ---------------------------- |
| `id`      | `string` | The object-scoped secret ID. |

#### Returns

`Promise`\<`OAuthTokenDto`\>

---

### listSecretsAvailableForBoard()

```ts
static listSecretsAvailableForBoard(id: string): Promise<ThirdPartyConnectionApiDto[]>;
```

Retrieves all secrets available to the current board for the given provider ID.

#### Parameters

| Parameter | Type     | Description                        |
| --------- | -------- | ---------------------------------- |
| `id`      | `string` | The secret provider ID to look up. |

#### Returns

`Promise`\<`ThirdPartyConnectionApiDto`[]\>

---

### proxyRequest()

```ts
static proxyRequest(
   url: string,
   token: string,
params: Omit<RequestInit, "credentials" | "mode">): Promise<Response>;
```

Forwards an authenticated HTTP request through the Alleo backend proxy.

#### Parameters

| Parameter | Type                                                 | Description                                                                            |
| --------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `url`     | `string`                                             | The target URL.                                                                        |
| `token`   | `string`                                             | The authorization token obtained from [getAuthorizationToken](#getauthorizationtoken). |
| `params`  | `Omit`\<`RequestInit`, `"credentials"` \| `"mode"`\> | Standard fetch options excluding credentials and mode.                                 |

#### Returns

`Promise`\<`Response`\>
