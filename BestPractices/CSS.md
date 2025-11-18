
# CSS

When a widget loads in Alleo, it is not contained in an iframe or something similar. It is directly attached to the DOM.

That means the CSS applies to the whole document, not a specific widget, so two instances of the same widget will use the same CSS. That's why in Alleo a widget can break the whole document (=board), not just the widget.

Some best practices around this:

- write a static CSS (ie. it should not be changed, or generated runtime. We use SCSS at build. I think tailwind should work, but tbh we haven't tried it.)
- contain your css into widget-based selectors. Ie. h1 --> .widget-container.my-widget-name h1 (that's why SCSS is practical)
- you can NEVER use id-s for your html objects. If there are two widgets with the same id, they will conflict. Using classes is okay.

- when you want to update the CSS on the fly:
    - in js, you can use this.domSelect('h1') which only returns the object from the specific widget instance. (it is based on querySelector())
    - in js this.dom refers to the inner container (ie. .widget-container) and the haptic.rootNode refers to the outer container. (using this.dom is preferred.)
    - I found that using css vars works really well. (eg. this.dom.style.setProperty('--widget-font-size', '11px'))
    - setting up classes for statuses also works well. (eg. this.dom.classList.add('currently-loading'))

Sidenotes:

- Alleo manages your widget interactions using the pointer-events css. Technically you can overwrite this. eg. .widget-container.my-widget-name button { pointer-events: auto } will make a button clickable, even when a user can't interact with the widget.
- (I don't like doing this, but) if needed, you can add an iframe to your widget and add the content there, so it is contained.
