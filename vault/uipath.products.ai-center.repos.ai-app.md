---
id: 4k5kw6npt95uxe9jh690no3
title: ai-app
desc: ''
updated: 1658062200099
created: 1657953079870
---

`ai-app` is the repository containing the Front-end code for AI Center.

It uses [[cs.webdev.frontend.language.js.jsframework.react]] as the framework of choice. We are also using [[cs.webdev.frontend.language.js.tools.typescript]]

First part when you open the application, the `portal-nav` Sidebar and top nav bar `portal-navbar` is created through [[uipath.products.apollo]] which is a UiPath specific Design System.

The project was created with [[cs.webdev.frontend.language.js.jsframework.react.tools.create-react-app]] and then ejected.

We host our application on an NGINX server.

Servers only serve the `index.html` file that gets generated after the build.

For Cloud:

The `.js` files are served by a CDN. => `aiAppAssetsPath` => To view => Azure end point => aifalphaassets => aifalphaterraform => containers => aifalphaassets => Folder with build number

CDN is used to reduce latency and the CDN server would be a server nearby the customer.

For On Prem:
`.js` files are run from inside the container.

aif-alpha-azure => Pipeline for cloud. =>

- AI App deployment task deploys the application on NGINX
- Upload ai-app assets to azure CDN takes care of `bundle.js` files of our application and deploys them on a CDN.
- Whenever we push a new docker image, our changes might not be visible as these two tasks need to be in sync. i.e. `index.html` takes in the path of the CDN, and if the CDN is not updated, it will take just the older ones.

`config.json` => initial configuration file. => When our app gets loaded. => Contains auth config and API endpoints. => Different for each environment.

`startup.sh` contains your paths to the CDN etc. => Tweaking environment variables if you can't achieve something via code or webpack. #important

`APP_PUBLIC_PATH` => Path to CDN. => Puts value to => `AIF_ASSETS_PATH`.

`IS_ON_PREM` => To check if the application is running on cloud or on prem.

`IS_FIRST_PARTY` => For first party services.

**Some more concepts:**

`smartling`: Something related to Visual Context that get injected => Definitions in `startup.sh` #todo

`APPEND_VISUAL_CONTEXT`

`sed` file.
