# Rendering on the Web

## Intro
* server rendering
* static rendering over full rehydration approach.

SSR - Server Side Rendering
CSR - Client Side Rendering
Rehydration - "booting up" javascript views on the client such that they reuse the server-rendered HTML's DOM tree and data.
Prerendering - running a client-side application at build time to capture its initial state as static HTML.


## Performance
* TTFB(Time to first byte): seen as the time between clicking a link and the first bit of content coming in.
* FP(First Paint) : the first time any pixel gets becomes visible to the user.
* FCP(First Contentful Paint): the time when requested content becomes visible.
* TTI(Time To Interactive): the time at which a page becomes interactive.

## Servier side rendering
* server rendering generates the full html for a page on the server.
* This avoids additional round-trips for data fetching and templating on the client.
* serverside rendering produces fast First Paint and First Contentful Paint.
* Running page logic and rendering  on the server makes it possible to avoid sending lots of js to client which helps fast TTI.
































## References

