---
id: njw1l4r18jwxpm5evcceyha
title: Logic Reuse
desc: ''
updated: 1663755932924
created: 1663755617332
---

Earlier we used to share logic via mixins. Then we used to share logic via Higher Order Components. Then we moved onto Render Props.

```javascript
import React from 'react'
import UserContext from '../user-context'

function ChatFeed({feedId}) {
  return (
    <UserContext.Consumer>
      {user => (
        <SubscribeToFeed feedId={feedId}>
          {posts => (
            <>
              <DocumentTitle title={posts.length} />
              // Pyramid of Doom
              // Pseudo-Hierarchy
              <OnlineStatus>
                {isOnline => (
                  <GeoLocation>
                    {location => (
                      <>
                        <StickyScroller>
                          <Posts posts={posts} />
                        </StickyScroller>
                        <PostInput feedId={feedId} user={user} />
                      </>
                    )}
                  </GeoLocation>
                )}
              </OnlineStatus>
            </>
          )}
        </SubscribeToFeed>
      )}
    </UserContext.Consumer>
  )
}
```
