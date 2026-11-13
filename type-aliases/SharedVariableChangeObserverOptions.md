[**@withalleo/alleo-widget**](../README.md)

---

[@withalleo/alleo-widget](../globals.md) / SharedVariableChangeObserverOptions

# Type Alias: SharedVariableChangeObserverOptions

```ts
type SharedVariableChangeObserverOptions = {
    runOnInit?: boolean
    startSuspended?: boolean
}
```

Options for [SharedVariable.observer](../classes/SharedVariable.md#observer).

## Example

```typescript
// render once now, then on every change
new SharedVariable.observer('title', (data) => this.render(data.title), { runOnInit: true })

// listen only after setup is done
const observer = new SharedVariable.observer('title', (data) => this.render(data.title), { startSuspended: true })
await this.setup()
observer.resume()
```

## Properties

### runOnInit?

```ts
runOnInit?: boolean;
```

Run the callback once right away with the current values, reporting every
observed variable as changed. Handy to render the initial state with the same code that handles updates.
Runs even when `startSuspended` is set.

---

### startSuspended?

```ts
startSuspended?: boolean;
```

Create the observer without listening yet. Call `resume()` to start.
