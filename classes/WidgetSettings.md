[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / WidgetSettings

# Class: WidgetSettings

Provides access to widget configuration settings from multiple sources.

Settings are merged from three levels in order of priority:

1. Organization-level settings (highest priority)
2. Deployment-level settings
3. Widget defaults from manifest.json (lowest priority)

This class allows widgets to access configuration values that can be customized per
organization or deployment without requiring code changes.

## Example

```typescript
// Access merged settings
const apiEndpoint = WidgetSettings.settings.apiEndpoint;
const maxRetries = WidgetSettings.settings.maxRetries || 3;

// Access only manifest defaults
const defaultColor = WidgetSettings.manifestConfig.defaultColor;

// Check if a feature is enabled
if (WidgetSettings.settings.enableAdvancedMode) {
  // Show advanced features
}
```

## Extended by

- [`DeploymentSettingsHelper`](DeploymentSettingsHelper.md)

## Constructors

### Constructor

```ts
new WidgetSettings(): WidgetSettings;
```

#### Returns

`WidgetSettings`

## Properties

### manifestConfig

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

---

### settings

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
