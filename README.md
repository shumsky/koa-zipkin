# koa-zipkin

Zipkin middleware for Koa 2.x that traces incoming HTTP requests.

## Usage
```js
const Koa = require('koa');
const {Tracer, ConsoleRecorder, ExplicitContext} = require('zipkin');
const {zipkinMiddleware} = require('koa-zipkin');

const recorder = new ConsoleRecorder();
const ctxImpl = new ExplicitContext();
const tracer = new Tracer({recorder, ctxImpl});
const app = new Koa();

app.use(zipkinMiddleware({tracer, serviceName: 'zipkin-koa-demo', port: 3000}));
```
