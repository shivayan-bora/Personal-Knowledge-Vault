
In React, all the event handlers will be passed an instance of `SyntheticEvent` which is a cross-browser wrapper around the browser's native events. It has the same interface as the browser's native event, including `stopPropagation()` and `preventDefault()`, except the event works identically across all the browsers. If you want to use the underlying browser event for some reason, you can access it via the `nativeEvent` attribute. For example in `onMouseLeave` `event.nativeEvent` will point to a `mouseout` event.

This is done for performance reasons and also React does something called as event delegation.
