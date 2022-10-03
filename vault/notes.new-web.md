---
id: q7wq3o6pqbfbutxxme5gizo
title: The Web's Next Transformation
desc: ''
updated: 1663908417969
created: 1663906298625
---

MPA (Multipage Apps) => PEMPA (Progressively enhanced multi-page apps - JS Sprinkles) => SPA (Single Page Apps) => The Next Phase

1. Data Persistence
2. Routes
3. Data Fetches (Reads)
4. Data Mutations (Creates, Updates, Deletes)
5. Rendering Logic

Prisma - ORM for Node.js and TypeScript

`<form>` only supports GET and POST

MPA => Whatever mutation we do, we have to reload the page and have a history of all the pages we have visited. => Everything on server => Server serves html, css and minimal to no js.

PEMPA => jQuery => jQuery is hard to maintain and is not a good fit for large applications. => jQuery used for DOM manipulation. => Code duplication. => Reandering happens partially in both client and server.

SPA => Rendering everything in client. => Server just stores data. => No rendering happening on servers.

PESPA (Progressively Enhanced SPA) => e.g. Remix, Svelte kit => No more API Routes

1. Functional is the baseline - JS Used to enhance not enable
2. Lazy Loading - intelligent pre-fetching (more than just JS Code)
3. Pushes code to the server
4. No manual duplication of UI code (as in PEMPAs)
5. Transparent browser emulation (#useThePlatform)

Remix makes all network requests and code splitting.

In Review:

1. Transitions involve both frontend and backend
2. Transitions are primarily about moving where the code lives (where it's written, who writes it and where it's run)
3. Every transition had motivations
4. Transtitions can impact UX and DX in both positive and negative ways
5. Every transition comes with tradeoffs
6. We are often unaware of the impact of tradeoffs untill after transition
7. The transition to PESPAs improves both UX and DX
