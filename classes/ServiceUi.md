[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / ServiceUi

# Class: ServiceUi

Helper class for managing UI elements in service-type widgets (widgets without a board presence).

Service widgets run in the background and may display UI elements in Alleo's interface panels.
This class provides access to button management and loading status indicators for service UIs.

## Example

```typescript
class MyServiceWidget {
  private ui: ServiceUi = new ServiceUi();

  constructor() {
    // Add a button to the service UI
    this.ui.buttons.add({
      label: 'Start Process',
      onClick: () => this.startProcess()
    });

    // Show loading status
    this.ui.loadingStatus.show('Processing...');
  }

  async startProcess() {
    this.ui.loadingStatus.show('Working...');
    await doWork();
    this.ui.loadingStatus.hide();
  }
}
```

## Constructors

### Constructor

> **new ServiceUi**(): `ServiceUi`

Creates an instance of ServiceUi with initialized button and loading status helpers.

#### Returns

`ServiceUi`

## Properties

### buttons

> **buttons**: [`UiButtonHelper`](UiButtonHelper.md)

Helper for managing UI buttons in the service interface.

Provides methods to add, remove, and configure interactive buttons that appear
in the service widget's UI panel.

***

### loadingStatus

> **loadingStatus**: [`LoadingStatus`](LoadingStatus.md)

Helper for displaying loading status indicators to users.

Provides methods to show/hide loading messages and spinners during
asynchronous operations.
