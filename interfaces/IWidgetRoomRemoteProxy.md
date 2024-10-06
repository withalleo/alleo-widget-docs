[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetRoomRemoteProxy

# Interface: IWidgetRoomRemoteProxy

## Extends

- [`IWidgetRoomProxy`](IWidgetRoomProxy.md)

## Properties

### isAvailable

> `readonly` **isAvailable**: `boolean`

Indicates whether the proxy is available

#### Inherited from

[`IWidgetRoomProxy`](IWidgetRoomProxy.md).[`isAvailable`](IWidgetRoomProxy.md#isavailable)

## Methods

### http()

> **http**(`command`, `roomId`): `Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

Executes an HTTP request on the Room client

#### Parameters

• **command**: [`HTTPCommandPayload`](../type-aliases/HTTPCommandPayload.md)

• **roomId**: `string`

#### Returns

`Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

***

### tcp()

> **tcp**(`command`, `roomId`): `Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

Executes a TCP request on the Room client

#### Parameters

• **command**: [`TCPCommandPayload`](../classes/TCPCommandPayload.md)

• **roomId**: `string`

#### Returns

`Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

***

### udp()

> **udp**(`command`, `roomId`): `Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

Executes a UDP request on the Room client

#### Parameters

• **command**: [`UDPCommandPayload`](../classes/UDPCommandPayload.md)

• **roomId**: `string`

#### Returns

`Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>
