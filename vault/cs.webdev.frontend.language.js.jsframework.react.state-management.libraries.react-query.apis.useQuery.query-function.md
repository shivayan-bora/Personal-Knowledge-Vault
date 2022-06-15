---
id: qrv35f2jdzohdf9pvbg7lzr
title: Query Function
desc: ''
updated: 1654758725351
created: 1654697746260
---

Any function that returns a promise is a valid query function. This means apart from using the JavaScript `fetch` API, we can use any kind of third party data fetching libraries like Axios or graphql-request, or query any asynchronous browser API, like the geolocation API.

```jsx
async function getLocation() {
  return new Promise((resolve, reject) => {
    navigator
      .geolocation
      .getCurrentPosition(resolve, reject);
  });
}

function Location() {
  const locationQuery = useQuery(["location"], getLocation);

  if (locationQuery.isLoading) {
    return <p>Calculating location...</p>;
  }

  if (locationQuery.error) {
    return <p>Error: {userQuery.error.message}</p>;
  }

  return (
    <p>
      Your location is:
      {locationQuery.data.coords.latitude}, 
      {locationQuery.data.coords.longitude}
    </p>
  );
}
```
