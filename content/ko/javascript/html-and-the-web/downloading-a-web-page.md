---
date: 2024-01-20 17:44:42.242692-07:00
description: "\uC6F9 \uD398\uC774\uC9C0\uB97C \uB2E4\uC6B4\uB85C\uB4DC\uD55C\uB2E4\
  \uB294 \uAC83\uC740 \uC778\uD130\uB137\uC5D0\uC11C \uB370\uC774\uD130\uB97C \uAC00\
  \uC838\uC640 \uB85C\uCEEC \uD658\uACBD\uC5D0 \uC800\uC7A5\uD558\uB294 \uAC83\uC785\
  \uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uC790\uB3D9\uD654, \uB370\
  \uC774\uD130 \uBD84\uC11D, \uBC31\uC5C5 \uD639\uC740 \uC624\uD504\uB77C\uC778 \uC811\
  \uADFC\uC744 \uC704\uD574 \uC774 \uC791\uC5C5\uC744 \uC2E4\uD589\uD569\uB2C8\uB2E4\
  ."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.788929-06:00'
model: gpt-4-1106-preview
summary: "\uC6F9 \uD398\uC774\uC9C0\uB97C \uB2E4\uC6B4\uB85C\uB4DC\uD55C\uB2E4\uB294\
  \ \uAC83\uC740 \uC778\uD130\uB137\uC5D0\uC11C \uB370\uC774\uD130\uB97C \uAC00\uC838\
  \uC640 \uB85C\uCEEC \uD658\uACBD\uC5D0 \uC800\uC7A5\uD558\uB294 \uAC83\uC785\uB2C8\
  \uB2E4."
title: "\uC6F9 \uD398\uC774\uC9C0 \uB2E4\uC6B4\uB85C\uB4DC\uD558\uAE30"
weight: 42
---

## How to: (방법)
```Javascript
const https = require('https');
const fs = require('fs');

const downloadPage = (url, filename) => {
  https.get(url, response => {
    const data = [];
    response.on('data', chunk => {
      data.push(chunk);
    });
    response.on('end', () => {
      const completePage = Buffer.concat(data).toString();
      fs.writeFileSync(filename, completePage);
      console.log(`Downloaded and saved to ${filename}`);
    });
  }).on('error', err => {
    console.error('Error fetching page:', err);
  });
};

// 사용 예
downloadPage('https://example.com', 'examplePage.html');
```
Sample Output:
```
Downloaded and saved to examplePage.html
```

## Deep Dive (심층 분석)
과거에는 웹 페이지를 다운로드하기 위해 FTP와 같은 프로토콜이 사용되었습니다. 지금은 HTTPS를 통해 보안이 강화된 데이터 전송이 이루어집니다. 위 예제는 Node.js의 'https' 모듈을 사용하여 웹 페이지의 데이터를 버퍼에 담은 후, 합쳐서 문자열로 변환합니다. 마지막으로 'fs' (파일 시스템) 모듈로 파일에 저장합니다. 대안으로는 `request`나 `axios` 같은 서드 파티 라이브러리가 있습니다. 이러한 라이브러리들은 추가 기능과 사용의 용이함을 제공합니다.

## See Also (추가 정보)
- MDN Web Docs (https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)에서 Fetch API 사용법 배우기
- Axios GitHub repository (https://github.com/axios/axios)에서 Axios 라이브러리 살펴보기
- Node.js File System Documentation (https://nodejs.org/api/fs.html)에서 더 많은 파일 시스템 메소드 확인하기
