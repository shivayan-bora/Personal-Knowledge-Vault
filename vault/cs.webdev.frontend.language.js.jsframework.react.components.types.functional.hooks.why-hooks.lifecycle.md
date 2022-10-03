---
id: wn6a6fi5b26y3c1vy9tsmn2
title: Lifecycle
desc: ''
updated: 1663755595705
created: 1663754483373
---

Take a look at the below code:

```jsx
import React from 'react';
import UserContext from '../user-context';

class ChatFeed extends React.Component {
    static contextType = UserContext;
    state = {isScrolledToBottom: true};
    
    componentDidMount() {
        this.subscribetoFeed();
        this.setDocumentTitle();
        this.subscribeToOnlineStatus();
        this.subscribeToGeoLocation();
    }
    
    componentWillUnmount() {
        this.unsubscribetoFeed();
        this.restoreDocumentTitle();
        this.unsubscribeToOnlineStatus();
        this.unsubscribeToGeoLocation();
    }
    
    componentDidUpdate(prevProps, prevState) {
        // ... compare props and re-subsribe etc. 
    }
    
    render() {
        //...
    }
}
```

This code is not optimal and prone to bugs. This would be difficult to refactor as well. Sharing logic is difficult as well.
