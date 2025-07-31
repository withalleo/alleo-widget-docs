[**@withalleo/alleo-widget**](../README.md)

***

[@withalleo/alleo-widget](../globals.md) / DeploymentSettingsHelper

# ~~Class: DeploymentSettingsHelper~~

## Deprecated

Use `WidgetSettings` instead. (This provides the same functionality for compatibility.)

## Extends

- [`WidgetSettings`](WidgetSettings.md)

## Constructors

### Constructor

> **new DeploymentSettingsHelper**(): `DeploymentSettingsHelper`

#### Returns

`DeploymentSettingsHelper`

#### Inherited from

[`WidgetSettings`](WidgetSettings.md).[`constructor`](WidgetSettings.md#constructor)

## Properties

### ~~manifestConfig~~

> `readonly` `static` **manifestConfig**: `Record`\<`string`, `any`\>

The widget settings from the widget's `manifest.json` file.
These settings usually represent the default configuration for the widget, which can be overridden at the organization level.

#### Inherited from

[`WidgetSettings`](WidgetSettings.md).[`manifestConfig`](WidgetSettings.md#manifestconfig)

***

### ~~settings~~

> `readonly` `static` **settings**: `Record`\<`string`, `any`\>

The settings for the widget. The settings are merged from the followings:
- organization settings
- deployment settings
- widget defaults from the widget's `manifest.json` configuration file.

#### Inherited from

[`WidgetSettings`](WidgetSettings.md).[`settings`](WidgetSettings.md#settings)
