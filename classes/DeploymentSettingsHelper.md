[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / DeploymentSettingsHelper

# ~~Class: DeploymentSettingsHelper~~

## Deprecated

Use `WidgetSettings` instead. (This provides the same functionality for compatibility.)

## Extends

- [`WidgetSettings`](WidgetSettings.md)

## Constructors

### Constructor

```ts
new DeploymentSettingsHelper(): DeploymentSettingsHelper;
```

#### Returns

`DeploymentSettingsHelper`

#### Inherited from

[`WidgetSettings`](WidgetSettings.md).[`constructor`](WidgetSettings.md#constructor)

## Properties

### ~~manifestConfig~~

```ts
readonly static manifestConfig: Record<string, any>;
```

Widget's default configuration from the `manifest.json` file.

Contains only the base configuration defined in the widget's manifest, without any
organization or deployment overrides applied. Useful when you need to access the
original default values regardless of customizations.

#### Example

```typescript
// Get the default color even if organization changed it
const defaultColor = WidgetSettings.manifestConfig.defaultColor;

// Check if user customized a setting
const isCustomized =
  WidgetSettings.settings.theme !== WidgetSettings.manifestConfig.theme;
```

#### Inherited from

[`WidgetSettings`](WidgetSettings.md).[`manifestConfig`](WidgetSettings.md#manifestconfig)

---

### ~~settings~~

```ts
readonly static settings: Record<string, any>;
```

Merged widget settings from all configuration sources.

Contains the final, resolved configuration values after merging:

- Organization-level settings (highest priority - overrides everything)
- Deployment-level settings (medium priority - overrides widget defaults)
- Widget defaults from `manifest.json` (lowest priority - fallback values)

Use this property to access any configuration value that should respect
organization customizations.

#### Example

```typescript
const maxFileSize = WidgetSettings.settings.maxFileSize || 10 * 1024 * 1024;
const apiUrl = WidgetSettings.settings.apiEndpoint;
```

#### Inherited from

[`WidgetSettings`](WidgetSettings.md).[`settings`](WidgetSettings.md#settings)
