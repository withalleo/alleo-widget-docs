# Handling the state of the widget

Your widget can have multiple states based on multiple factors.

Including:

- loaded / unloaded
- in viewport or not

## Handling loaded / unloaded state

A widget can unload for multiple reasons: it can be removed from the board, the user can close the board (eg. to
navigate to the dashboard), the user can switch to another board, or in some situations Alleo will unload widgets that
are not in the user's viewport to save resources.

When a widget unloads:

- the widget DOM (the attached html) is removed
- the `haptic.widgetDestroyed$` event is triggered.
- the widget events are disabled.
- Some attached listeners are not removed. So typically widgets that use timers (including setInterval, setTimeout, RxJS
  timers), OR media playback, OR attached some HTML content to other parts of the board, etc should clean up those
  resources when the widget unloads.

typical use:

```javascript
haptic.widgetDestroyed$.subscribe(() => this.onDestroy())
```

When used in an `AlleoWidget` class, you can override the destroy() method:

```javascript
 public override destroy(): void {
    super.destroy()
    // your cleanup code here
}
```

On load, the while the widget code is used from cache, a new widget instance is created, and the AlleoWidget constructor
is called again.

## Is the widget within the viewport?

When a widget is not visible on the users device, it might make sense to pause some activities (eg. media playback,
timers, etc) to save resources.

When the "visibility" of the widget changes, the `haptic.inViewport$` event is triggered.

```javascript
haptic.inViewport$.subscribe((inViewport: boolean) => {
    if (inViewport) {
        console.log('at least part of the widget is now visible on the users device')
    } else {
        console.log('not a single pixel of the widget is visible on the users device')
    }
})
```

## Detailed widget state

The `haptic.interactibility$` observer is somewhat related, giving you more detailed information about the widget's
status (eg. is it selected?)

```javascript
interface
Interactibility
{
    interactible: boolean;
    state: {
        boardMode: BoardMode;
        canEdit: boolean;
        designMode: boolean;
        followingUser: boolean;
        inViewport: boolean;
        locked: boolean;
        multiSelected: boolean;
        presentationActive: boolean;
        selectableByLongpress: boolean;
        selected: boolean;
        transforming: boolean;
        viewOnly: boolean;
    }
    ;
}
```
