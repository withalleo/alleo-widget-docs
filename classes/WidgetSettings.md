[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / WidgetSettings

# Class: WidgetSettings

Interface to provide access to widget settings and configurations.

## Extended by

- [`DeploymentSettingsHelper`](DeploymentSettingsHelper.md)

## Constructors

### Constructor

> **new WidgetSettings**(): `WidgetSettings`

#### Returns

`WidgetSettings`

## Properties

### manifestConfig

> `readonly` `static` **manifestConfig**: `Record`\<`string`, `any`\>

The widget settings from the widget's `manifest.json` file.
These settings usually represent the default configuration for the widget, which can be overridden at the organization level.

***

### settings

> `readonly` `static` **settings**: `Record`\<`string`, `any`\>

The settings for the widget. The settings are merged from the followings:
- organization settings
- deployment settings
- widget defaults from the widget's `manifest.json` configuration file.
