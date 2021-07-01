# Node.js Express

`MERN stack`은 JavaScript 생태계에서 인기있는 프레임워크인 MongoDB, Express, React, Node를 지칭하는 말입니다. 이 중에서 Express.js는 Node.js 환경에서 웹 서버, 또는 API 서버를 제작하기 위해 사용되는 인기있는 프레임워크입니다.

Express framework는 npm을 통해 다운로드할 수 있습니다. Express로 구현한 서버가 http 모듈로 작성한 서버와 다른 점은 다음과 같습니다.

1. 미들웨어 추가가 편리하다.
2. [자체 라우터](https://expressjs.com/en/guide/routing.html)를 제공한다

메소드와 URL(`/lower`, `/upper` 등)로 분기점을 만드는 것을 라우팅(Routing)이라고 합니다.

> 클라이언트는 특정한 HTTP 요청 메소드(GET, POST 등)나 서버의 특정 URI(또는 경로)로 HTTP 요청을 보냅니다. 라우팅은 클라이언트의 요청에 해당하는 메소드와 Endpoint에 따라 서버가 응답하는 방법을 결정하는 것입니다.

## 미들웨어

미들웨어는 올라가있는 request에 필요한 기능을 더하거나 문제점을 제거하는 역할을 하는 express의 가장 큰 장점입니다

먼저, 미들웨어를 사용하는 상황은 다음과 같습니다.

1. 모든 요청에 대해 url이나 메소드를 확인할 때
2. POST 요청 등에 포함된 body(payload)를 구조화할 때(쉽게 얻어내고자 할 때)
3. 모든 요청/응답에 CORS 헤더를 붙여야할 때
4. 요청 헤더에 사용자 인증 정보가 담겨있는지 확인할 때

### **POST 요청 등에 포함된 body(payload)를 구조화할 때**

순수 node.js로 HTTP body(payload)를 받을 때에는 Buffer를 조합해서 다소 복잡한 방식으로 body를 얻을 수 있습니다.

```json
let body = [];
request.on('data', (chunk) => {
  body.push(chunk);
}).on('end', () => {
  body = Buffer.concat(body).toString();
  // body 변수에는 문자열 형태로 payload가 담겨져 있습니다.
});
```

[코드] 네트워크상의 chunk를 합치고, buffer를 body로 변환하는 작업이 필요합니다.

[body-parser 미들웨어](https://github.com/expressjs/body-parser)를 사용하면 이 과정을 간단하게 처리할 수 있습니다.

```
const bodyParser = require('body-parser')
const jsonParser = bodyParser.json()

// 생략
app.post('/api/users', jsonParser, function (req, res) {
  // req.body에는 JSON의 형태로 payload가 담겨져 있습니다.
})
```

[코드] bodyParser를 이용해 요청받은 데이터를 json 형태로 변환합니다.

### **모든 요청/응답에 CORS 헤더를 붙일 때**

순수 node.js 코드에 CORS 헤더를 붙이려면, 응답 객체의 `writeHead` 메소드 등을 이용합니다. 이런 메소드를 이용하더라도 `Access-Control-Allow-*` 헤더를 매번 재정의해야 합니다. 그뿐만 아니라, `OPTIONS` 메소드에 대한 라우팅도 따로 구현해야 합니다.

```
const defaultCorsHeader = {
  'Access-Control-Allow-Origin': '*',
  'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE, OPTIONS',
  'Access-Control-Allow-Headers': 'Content-Type, Accept',
  'Access-Control-Max-Age': 10
};

// 생략
if (req.method === 'OPTIONS') {
  res.writeHead(201, defaultCorsHeader);
  res.end()
}
```

[코드] 순수 node.js에 CORS를 적용하는 예시

[cors 미들웨어](https://github.com/expressjs/cors)를 사용하면 이 과정을 간단하게 처리할 수 있습니다.

```
const cors = require('cors')

// 생략
app.use(cors()) // 모든 요청에 대해 CORS 허용
```

[코드] cors 모듈을 이용해 CORS를 간단하게 처리할 수 있습니다.

```
const cors = require('cors')

// 생략
// 특정 요청에 대해 CORS 허용
app.get('/products/:id', cors(), function (req, res, next) {
  res.json({msg: 'This is CORS-enabled for a Single Route'})
})
```

[코드] 특정 요청에만 cors 모듈을 적용할 수도 있습니다.

### Request Properties

- `req.query`
  이 속성은 경로의 각 쿼리 문자열 매개 변수에 대한 속성이 포함된 개체다
  ex) [https://query/search?searchWord=구글](https://query/search?searchWord=구글) 이라면
  searchWord 매개변수의 구글이라는 값을 가져온다
- `req.body`
  JSON 등의 데이터를 담을때 사용한다
  주로 POST로 유저의 정보 또는 파일업로드를 했을때 사용하며
  요청 본문에 제출된 키-값 데이터 쌍을 포함한다 기본적으로 정의 되어있지 않으며
  express.json(), express.urlencoded()와 같은 미들웨어를 사용해야한다

즉 req.body는 body-parser를 사용하기전에는 default 값으로 Undefind 설정이 되기때문에 body-parser를 사용하여 해결해야 오류를 뱉지 않는다

```jsx
//미들웨어
app.use(bodyParser.json())
app.use(bodyParser.urlencoded({ extends: true }))
		↓
        	↓ // Express 4.16.0버전 부터 body-parser의 일부 기능이 익스프레스에 내장
        	↓ // 아래와 같이 사용 가능하다
app.use(express.json())
app.use(express.urlencoded({ extends: true}))
```

## 참조

[Express - Node.js 웹 애플리케이션 프레임워크](https://expressjs.com/ko/)

[4.x API](http://expressjs.com/ko/api.html#req.query)

[기본 라우팅](https://expressjs.com/ko/starter/basic-routing.html)

[Express와 미들웨어](https://velog.io/@leobit/%EB%AF%B8%EB%93%A4%EC%9B%A8%EC%96%B4%EC%99%80-Express)
