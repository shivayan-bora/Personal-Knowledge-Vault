---
id: fufxlumc2nu8oj9oniuqmys
title: Composition
desc: ''
updated: 1658061593233
created: 1658057010195
---

We can compose functions together to form some value:

```js
function getProfilePic(username) {
  return "https://photo.fb.com/" + username;
}

function getProfileLink(username) {
  return "https://www.fb.com/" + username;
}

function getAvatarInfo(username) {
  return {
    pic: getProfilePic(username),
    link: getProfileLink(username),
  };
}

getAvatarInfo("tylermcginnis");
```

We can use the same intuition i.e. composing functions together to get some UI:

```jsx
function ProfilePic (props) {
  return (
    <img src={'https://photo.fb.com/' + props.username'} />
  )
}

function ProfileLink (props) {
  return (
    <a href={'https://www.fb.com/' + props.username}>
      {props.username}
    </a>
  )
}

function Avatar (props) {
  return (
    <div>
      <ProfilePic username={props.username} />
      <ProfileLink username={props.username} />
    </div>
  )
}


<Avatar username="tylermcginnis" />
```

This is the foundation of React.

This is a language agnostic concept, so, the same intuition we have about building and composing functions together, can be directly applied to build and compose React components together.

This also brings the advantages of composition over inheritance into React.

Because of this, we also get a vibrant ecosystem of third-party components that can be reused in our applications.

React is like Legos for developers.
