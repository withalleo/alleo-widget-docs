[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / SelfDeleteHelper

# Class: SelfDeleteHelper

Helper class that enables a widget to delete itself from the board programmatically.

Provides a mechanism for widgets to remove themselves from the board in response to
certain conditions or events. Uses a shared variable trigger pattern to coordinate
deletion across multiple widget instances and handle async deletion scenarios.

## Example

```typescript
class MyWidget extends AlleoWidget {
  private deleteHelper: SelfDeleteHelper;

  constructor() {
    super();
    this.deleteHelper = new SelfDeleteHelper();

    // Delete widget after some condition
    if (someCondition) {
      this.deleteHelper.deleteSelf();
    }
  }
}
```

## Constructors

### Constructor

> **new SelfDeleteHelper**(): `SelfDeleteHelper`

#### Returns

`SelfDeleteHelper`

## Properties

### deleteTriggerContent

> `protected` `static` **deleteTriggerContent**: `string` = `'deleteme'`

***

### storageKey

> `protected` `static` **storageKey**: `string` = `'ThisWidgetShouldBeDeleted'`

## Accessors

### shouldBeDeleted

#### Get Signature

> **get** **shouldBeDeleted**(): `boolean`

##### Returns

`boolean`

## Methods

### checkDeleteTrigger()

> `protected` **checkDeleteTrigger**(): `void`

#### Returns

`void`

***

### deleteSelf()

> **deleteSelf**(): `void`

Programmatically removes the widget from the board.

This method triggers the deletion process by setting a shared variable flag, which is
monitored by all instances of the widget. The actual deletion is performed through
the BoardObjectHelper, removing the widget object from the Alleo board.

#### Returns

`void`

#### Example

```typescript
// Delete widget when a timeout expires
setTimeout(() => {
  selfDeleteHelper.deleteSelf();
}, 60000); // Delete after 1 minute
```

***

### setDeleteTrigger()

> `protected` **setDeleteTrigger**(): `void`

#### Returns

`void`
