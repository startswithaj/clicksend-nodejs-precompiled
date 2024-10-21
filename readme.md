# ClickSend NodeJs Compiled

The official [ClickSend](https://www.npmjs.com/package/clicksend) npm package does not come compiled.

See this [issue](https://github.com/ClickSend/clicksend-nodejs/issues/10). ¯\_(ツ)\_/¯

This unofficial package simply pulls the package at the version in package.json and compiles it. Still exports the typescript types.

The official package uses `request` which has been unmaintained for 5 years and suffers this [cve](https://github.com/request/request/issues/3442). This package forces it to use `@cypress/request` which is patched.

```
"request": "npm:@cypress/request@^3.0.5",
```

## Usage

```typescript
import { SMSApi } from "click-send-nodejs-precompiled";
const clickSend = new SMSApi(
  process.env.CLICKSEND_USERNAME!,
  process.env.CLICKSEND_API_KEY!
);
const smsCollection = {
  messages: [
    {
      from: "from",
      body: "message",
      to: "+614...",
    },
  ],
};

await clickSend.smsSendPost(smsCollection);
```
