# frenzy.js

> **Warning**
> frenzy.js is currently being rewritten, it's pretty much ready for use for most applications but is still not entirely feature complete.
>
> You can find the [version 6 README here](https://github.com/FrenzyComs/frenzy.js/tree/v6).

![frenzy.js](https://img.shields.io/npm/v/frenzy.js) ![frenzy-api](https://img.shields.io/npm/v/frenzy-api?label=Frenzy%20API)

**frenzy.js** is a JavaScript library for interacting with the entire Frenzy API.

## Example Usage

```javascript
// esm / typescript
import { Client } from "frenzy.js";
// ...or commonjs
const { Client } = require("frenzy.js");

let client = new Client();

client.on("ready", async () =>
  console.info(`Logged in as ${client.user.username}!`)
);

client.on("messageCreate", async (message) => {
  if (message.content === "hello") {
    message.channel.sendMessage("world");
  }
});

client.loginBot("..");
```

## Reactivity with Signals & Solid.js Primitives

All objects have reactivity built-in and can be dropped straight into any Solid.js project.

```tsx
const client = new Client();
// initialise the client

function MyApp() {
  return (
    <h1>Your username is: {client.user?.username ?? "[logging in...]"}</h1>
  );
}
```

## Frenzy API Types

All `frenzy-api` types are re-exported from this library under `API`.

> **Warning**
> It is advised you do not use this unless necessary, if you find somewhere that isn't covered by the library, please open an issue as this library aims to transform all objects.

```typescript
import { API } from "frenzy.js";

// API.Channel;
// API.[..];
```
