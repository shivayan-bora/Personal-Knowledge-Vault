---
id: kwor9uu68paz3kuy4rd5hzr
title: Colocating the State
desc: ''
updated: 1654590204313
created: 1654590165240
---

Imagine the following example:

```jsx
function App() {
  return (
    <UserProvider username={username}>
      <NotificationsProvider>
        <ThemeProvider>
          <AuthenticationProvider>
            <Router>
              <HomeScreen path="/" />
              <AboutScreen path="/about" />
              <UserScreen path="/:userId" />
              <UserSettingsScreen path="/settings" />
              <NotificationsScreen path="/notifications" />
            </Router>
          </AuthenticationProvider>
        </ThemeProvider>
      </NotificationsProvider>
    </UserProvider>
  )
}
```

Here's what a file structure might look like for this:

```text
my-cool-app
└── src
    ├── index.js
    ├── providers
    │   ├── auth.js
    │   ├── notifications.js
    │   ├── theme.js
    │   ├── user.js
    │   └── ...etc
    ├── screens
    │   ├── about.js
    │   ├── home.js
    │   ├── notifications
    │   │   ├── index.js
    │   │   ├── list.js
    │   │   ├── tab.js
    │   │   └── type-list.js
    │   ├── settings.js
    │   └── user
    │       ├── activity.js
    │       ├── index.js
    │       ├── info.js
    │       └── nav.js
    └── utils
        └── ...etc
```

Let's colocate the context:

```jsx
function App() {
  return (
    <ThemeProvider>
      <AuthenticationProvider>
        <Router>
          <HomeScreen path="/" />
          <AboutScreen path="/about" />
          <UserScreen path="/:userId" />
          <UserSettingsScreen path="/settings" />
          <NotificationsScreen path="/notifications" />
        </Router>
      </AuthenticationProvider>
    </ThemeProvider>
  )
}

function NotificationsScreen() {
  return (
    <NotificationsProvider>
      <NotificationsTab />
      <NotificationsTypeList />
      <NotificationsList />
    </NotificationsProvider>
  )
}

function UserScreen({username}) {
  return (
    <UserProvider username={username}>
      <UserInfo />
      <UserNav />
      <UserActivity />
    </UserProvider>
  )
}
```

For this, the file structure would look like:

```text
my-cooler-app
└── src
    ├── index.js
    ├── providers
    │   ├── auth.js
    │   ├── theme.js
    │   └── ...etc
    ├── screens
    │   ├── about.js
    │   ├── home.js
    │   ├── notifications
    │   │   ├── index.js
    │   │   ├── list.js
    │   │   ├── provider.js
    │   │   ├── tab.js
    │   │   └── type-list.js
    │   ├── settings.js
    │   └── user
    │       ├── activity.js
    │       ├── index.js
    │       ├── info.js
    │       ├── nav.js
    │       └── provider.js
    └── utils
        └── ...etc
```

Notice that each page can have its own provider that has data necessary for the components underneath it. Code splitting "just works" for this stuff as well. How you get data _into_ each provider is up to the hooks those providers use and how you retrieve data in your application, but you know just where to start looking to find out how that works (in the provider).

**Advantages of Colocation:**

- Code-splitting just works.
- File structure scales well. (Read [File structure guide by Dan Abramov](http://react-file-structure.surge.sh/))
- Reduced indirection.
