[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / IBoardWidgetApi

# Type Alias: IBoardWidgetApi

```ts
type IBoardWidgetApi = Prettify<
    IWidgetApiBase &
        Omit<IWidgetApi, keyof IWidgetApiBase> & {
            __hasDom: true
        }
>
```

Widget API for Board Widgets (i.e. widgets that are not a service)
