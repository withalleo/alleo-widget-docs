[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / LoadSharingHelper

# Class: LoadSharingHelper

Helper class for managing load sharing through a shared lock mechanism.

The idea is that something will be handled by a single frontend instance only.

eg. a weather widget might need a data update every 5 minutes. However only one client needs to do this, and share the data as a shared variable.

## Constructors

### new LoadSharingHelper()

> **new LoadSharingHelper**(`callback`, `checkInterval`, `takeOverTimeout`, `dataFieldName`): [`LoadSharingHelper`](LoadSharingHelper.md)

Creates an instance a periodical task, that is performed by only one frontend instance.

#### Parameters

• **callback**

The callback function to be called when the lock is acquired.

• **checkInterval**: `number` = `300`

The interval in milliseconds to check the lock status.

• **takeOverTimeout**: `number` = `...`

The timeout in milliseconds to take over the lock if not updated.

• **dataFieldName**: `string` = `'processLock'`

The name of the data field to store the lock information.

#### Returns

[`LoadSharingHelper`](LoadSharingHelper.md)

## Properties

### defaultLock

> `static` **defaultLock**: [`SharedLock`](../type-aliases/SharedLock.md)

The default shared lock.

## Methods

### restartTimer()

> **restartTimer**(`interval`, `takeOverTimeOut`): `void`

Restarts the timer with a new interval and takeover timeout.

#### Parameters

• **interval**: `number` = `undefined`

The new interval in milliseconds to check the lock status.

• **takeOverTimeOut**: `number` = `...`

The new timeout in milliseconds to take over the lock if not updated.

#### Returns

`void`

***

### startTimer()

> **startTimer**(): `void`

Starts the timer that checks the lock status.

#### Returns

`void`

***

### stopTimer()

> **stopTimer**(): `void`

Stops the timer that checks the lock status.

#### Returns

`void`
