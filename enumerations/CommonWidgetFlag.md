[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / CommonWidgetFlag

# Enumeration: CommonWidgetFlag

Widget flags used by `AlleoWidget` itself.

## Enumeration Members

### WidgetInitiallyConfigured

```ts
WidgetInitiallyConfigured: 'widget-initially-configured'
```

Set during the creation phase, ending it, when:

- the widget is unloaded for the first time, or
- any `SettingsDialogHelper` dialog of the widget is closed (saved or cancelled)

Can be set to indicate that the widget has been initially configured, preventing `justCreatedOptionalUI()` from running.
