[**@withalleo/alleo-widget**](../README.md) • **Docs**

***

[@withalleo/alleo-widget](../globals.md) / ILogger

# Interface: ILogger

## Methods

### critical()

> **critical**(...`args`): `void`

#### Parameters

• ...**args**: `any`[]

#### Returns

`void`

***

### debug()

> **debug**(...`args`): `void`

#### Parameters

• ...**args**: `any`[]

#### Returns

`void`

***

### debugNoPersist()

> **debugNoPersist**(...`args`): `void`

#### Parameters

• ...**args**: `any`[]

#### Returns

`void`

***

### endSession()

> **endSession**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

***

### error()

> **error**(...`args`): `void`

#### Parameters

• ...**args**: `any`[]

#### Returns

`void`

***

### flush()

> **flush**(): `Promise`\<`void`\>

#### Returns

`Promise`\<`void`\>

***

### getCurrentSessionData()

> **getCurrentSessionData**(): `any`

#### Returns

`any`

***

### info()

> **info**(...`args`): `void`

#### Parameters

• ...**args**: `any`[]

#### Returns

`void`

***

### persistLog()

> **persistLog**(`level`, `args`): `void`

#### Parameters

• **level**: `string`

• **args**: `any`[]

#### Returns

`void`

***

### saveSessionData()

> **saveSessionData**(): `void`

#### Returns

`void`

***

### startSession()

> **startSession**(`sessionName`?): `Promise`\<`void`\>

#### Parameters

• **sessionName?**: `string`

#### Returns

`Promise`\<`void`\>

***

### toStorable()

> **toStorable**(`args`): `any`[]

#### Parameters

• **args**: `any`[]

#### Returns

`any`[]

***

### trace()

> **trace**(...`args`): `void`

#### Parameters

• ...**args**: `any`[]

#### Returns

`void`

***

### warn()

> **warn**(...`args`): `void`

#### Parameters

• ...**args**: `any`[]

#### Returns

`void`
