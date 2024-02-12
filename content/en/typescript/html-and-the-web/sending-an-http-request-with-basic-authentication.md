---
title:                "Sending an HTTP request with basic authentication"
aliases:
- en/typescript/sending-an-http-request-with-basic-authentication.md
date:                  2024-01-20T18:02:54.663141-07:00
model:                 gpt-4-1106-preview
simple_title:         "Sending an HTTP request with basic authentication"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/typescript/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why?

In TypeScript, sending an HTTP request with basic authentication means shooting data across the web with a simple username:password combo for access. It's widespread for quick-and-dirty auth because it's simple to use for protecting your API endpoints from unwelcome visitors.

## How to:

```typescript
import axios from 'axios';

// encode your username and password
const token = Buffer.from('yourUsername:yourPassword').toString('base64');
const url = 'https://your.api/endpoint';

// setup the HTTP request with Axios
axios.get(url, {
  headers: {
    'Authorization': `Basic ${token}`
  }
})
.then(response => {
  console.log(response.data); // this is your expected output
})
.catch(error => {
  console.error("Oops, something went wrong!", error);
});
```

Sample output:

```
{ "message": "You're in! Welcome to secret API land." }
```

## Deep Dive

Once upon a time, before OAuth and JWTs swarmed the scene, basic auth was the go-to. It's still nifty for internal tools or Proof of Concepts (PoCs). The idea is straightforward: tack on a header with 'Authorization', use 'Basic ' + a base64 encoded 'username:password'. Voilà, you're through the gates.

But it's not all rainbows. There're risks - if you're not using HTTPS, you're practically yelling your creds out loud. Alternatives? OAuth2 tokens, JWTs, API keys - they're like stronger, silent types. They serve similar purposes but with more complexity and security.

When implementing basic auth in TypeScript, the common choice is `axios` or `fetch`. In our case, `axios` makes setting custom headers a breeze. Plus, it returns promises, making it a dream with `async/await`.

Keep in mind: 'Basic' will soon reveal its age in the modern web where HTTPS is a must and security standards are higher. Yet, for internal networks or where higher security isn't crucial, it's a cinch.

## See Also

For more authentication methods and security best practices:

- [MDN Web Docs: Authorization](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization)
- [OWASP Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)
- Official `axios` documentation for custom HTTP headers: [Axios Docs](https://axios-http.com/docs/req_config)
