# ClickSend NodeJs Compiled

The official [ClickSend](https://www.npmjs.com/package/clicksend) npm package does not come compiled.

See this [issue](https://github.com/ClickSend/clicksend-nodejs/issues/10). ¯\_(ツ)\_/¯

This unofficial package simply pulls the package at the version in package.json and compiles it. Still exports the typescript types.

## Usage

```typescript
import { SMSApi } from "click-send-nodejs-precompiled";
const clickSend = new SMSApi(
  process.env.CLICKSEND_USERNAME!,
  process.env.CLICKSEND_API_KEY!
);
const { mobile, message } = props;
const smsCollection = {
  messages: [
    {
      from: "Epilog",
      body: message,
      to: mobile,
    },
  ],
};

await clickSend.smsSendPost(smsCollection);
```
