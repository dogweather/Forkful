---
aliases:
- /ko/javascript/sending-an-http-request-with-basic-authentication/
date: 2024-01-20 18:01:53.067422-07:00
description: "HTTP \uC694\uCCAD \uC2DC \uAE30\uBCF8 \uC778\uC99D\uC740 \uC0AC\uC6A9\
  \uC790 \uC774\uB984\uACFC \uD328\uC2A4\uC6CC\uB4DC\uB97C \uC11C\uBC84\uC5D0 \uBCF4\
  \uB0B4 \uB85C\uADF8\uC778\uD558\uB294 \uBC29\uBC95\uC785\uB2C8\uB2E4. \uC11C\uBC84\
  \ \uB9AC\uC18C\uC2A4\uC5D0 \uC548\uC804\uD558\uAC8C \uC811\uADFC\uD560 \uC218 \uC788\
  \uC5B4 \uAC1C\uBC1C\uC790\uB4E4\uC774 \uC790\uC8FC \uC0AC\uC6A9\uD569\uB2C8\uB2E4\
  ."
isCJKLanguage: true
lastmod: 2024-02-18 23:09:06.812100
model: gpt-4-1106-preview
summary: "HTTP \uC694\uCCAD \uC2DC \uAE30\uBCF8 \uC778\uC99D\uC740 \uC0AC\uC6A9\uC790\
  \ \uC774\uB984\uACFC \uD328\uC2A4\uC6CC\uB4DC\uB97C \uC11C\uBC84\uC5D0 \uBCF4\uB0B4\
  \ \uB85C\uADF8\uC778\uD558\uB294 \uBC29\uBC95\uC785\uB2C8\uB2E4. \uC11C\uBC84 \uB9AC\
  \uC18C\uC2A4\uC5D0 \uC548\uC804\uD558\uAC8C \uC811\uADFC\uD560 \uC218 \uC788\uC5B4\
  \ \uAC1C\uBC1C\uC790\uB4E4\uC774 \uC790\uC8FC \uC0AC\uC6A9\uD569\uB2C8\uB2E4."
title: "\uAE30\uBCF8 \uC778\uC99D\uC744 \uC0AC\uC6A9\uD55C HTTP \uC694\uCCAD \uBCF4\
  \uB0B4\uAE30"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
HTTP 요청 시 기본 인증은 사용자 이름과 패스워드를 서버에 보내 로그인하는 방법입니다. 서버 리소스에 안전하게 접근할 수 있어 개발자들이 자주 사용합니다.

## How to (어떻게):
```javascript
// Node.js 환경에서 axios 라이브러리를 사용한 예제입니다.

const axios = require('axios');

// 인코딩 전 사용자 이름과 비밀번호
const username = 'your_username';
const password = 'your_password';

// base64로 인코딩
const base64Credentials = Buffer.from(`${username}:${password}`).toString('base64');

// axios를 이용한 HTTP GET 요청
axios.get('https://your-api-endpoint.com/data', {
  headers: {
    // 기본 인증 헤더 설정
    'Authorization': `Basic ${base64Credentials}`
  }
})
.then(response => {
  console.log(response.data); // 성공적인 응답 출력
})
.catch(error => {
  console.error('Authentication failed:', error); // 인증 실패 시 에러 메시지 출력
});
```

## Deep Dive (심층 분석):
기본 인증(Basic Authentication)은 HTTP 1.0부터 존재하는 방식입니다. 인증 정보가 base64 인코딩으로 전송되기 때문에 HTTPS와 함께 사용하는 것이 좋습니다. base64 인코딩은 암호화가 아니라 인코딩이라는 점을 기억하세요. 

대안으로는, 예를 들어 OAuth나 JWT(Json Web Tokens) 등 더 안전한 인증 방법들이 있습니다. 그러나 간단한 어플리케이션에서는 기본 인증은 여전히 유용합니다.

실제 구현 시, `axios` 같은 HTTP 클라이언트 라이브러리를 사용하면 접근성이 좋고 에러 처리나 프로미스 구조를 활용하는 등의 이점이 있습니다. Node.js에서는 `http` 모듈을 사용할 수도 있지만, `axios`는 구성이 더 간단하고 다양한 HTTP 기능을 지원합니다.

## See Also (참고 자료):
- MDN Web Docs에서 [기본 인증](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#basic_authentication_scheme)에 대한 문서
- [Axios GitHub Repository](https://github.com/axios/axios)
- [Node.js HTTP 모듈 문서](https://nodejs.org/api/http.html)
- JWT에 관한 [소개](https://jwt.io/introduction/)
- OAuth에 대한 [RFC 6749](https://tools.ietf.org/html/rfc6749)
