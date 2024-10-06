[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / IWidgetRoomLocalProxy

# Interface: IWidgetRoomLocalProxy

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

> **http**(`command`): `Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

Executes an HTTP request on the Room client

#### Parameters

• **command**: [`HTTPCommandPayload`](../type-aliases/HTTPCommandPayload.md)

#### Returns

`Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

***

### tcp()

> **tcp**(`command`): `Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

Executes a TCP request on the Room client

#### Parameters

• **command**: [`TCPCommandPayload`](../classes/TCPCommandPayload.md)

#### Returns

`Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

***

### udp()

> **udp**(`command`): `Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>

Executes a UDP request on the Room client

#### Parameters

• **command**: [`UDPCommandPayload`](../classes/UDPCommandPayload.md)

#### Returns

`Promise`\<[`IRoomProxyResult`](IRoomProxyResult.md)\>
