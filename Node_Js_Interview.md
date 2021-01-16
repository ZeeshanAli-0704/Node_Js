# Node Js Interview  Questions - Basic Node js

 ##  *Node Js*
Node.js® is a JavaScript runtime built on [Chrome's V8 JavaScript engine](https://v8.dev/).

Node.js is a very powerful JavaScript-based platform built on Google Chrome's JavaScript V8 Engine. It is used to develop I/O intensive web applications like video streaming sites, single-page applications, and other web applications. Node.js is open source, completely free, and used by thousands of developers around the world.

- It uses Google JavaScript V8 Engine to execute code.
- It is a cross platform environment and can run on Microsoft Windows Linux, FreeBSD and IBM
- It provides an event driven architecture and non-blocking I/O that is optimised & scalable.

[Node.js](https://nodejs.org/en/)
[Guides](https://nodejs.org/en/docs/guides/)
[Dependencies](https://nodejs.org/en/docs/meta/topics/dependencies/)

## Why Node.js?

As Node.js is a asynchronus programming we don’t need to wait for one requst to complete fully, it’s simply take the next request so there is no waiting time and that’s is the best part of the Node.js. It is very memory efficient because of it’s features.

***Advantages of Node.js***

**1) Non Blocking I/O
2) V8 engine
3) Asynchronous Request Handling
4) Event Driven Module - [Event based model]
5) Cross-Platform Development**

***Drawbacks of Node.js***

**1) Performance bottlenecks with heavy computation tasks
2) Callback hell issue
3) Growing demand for experienced professionals**

## IBM Example : The bank and the coffee shop

***Blocking versus non-blocking***

Blocking: At the bank, the teller helps you from start to finish. Customers in the queue behind you must wait until your entire transaction is complete. If there is a step in the transaction that cannot be completed by the teller, the teller is blocked while that step is completed.

Non-blocking: At the coffee shop, the counter employee and the barista work together to complete your order. The counter employee takes your order and is not blocked while the barista completes your order.

I realize this isn’t a perfect analogy (some banks use multiple tellers to complete transactions, and some coffee shops have multiple people taking orders), but hopefully you understand the difference between the two programming models.

Node uses the coffee shop model. A single thread of execution runs all of your JavaScript code, and you provide callbacks to wait for results.

Other software stacks use the bank model. To scale, more threads (or processes) are created. Apache web server is one example that uses the bank scalability model.

Both models, of course, can achieve horizontal scalability by adding more servers.

## The V8 JavaScript Engine
V8 is the name of the JavaScript engine that powers Google Chrome. It's the thing that takes our JavaScript and executes it while browsing with Chrome.

V8 provides the runtime environment in which JavaScript executes. The DOM, and the other Web Platform APIs are provided by the browser.

The cool thing is that the JavaScript engine is independent of the browser in which it's hosted. This key feature enabled the rise of Node.js. V8 was chosen to be the engine that powered Node.js back in 2009, and as the popularity of Node.js exploded, V8 became the engine that now powers an incredible amount of server-side code written in JavaScript.

V8 is written in C++, and it's continuously improved. It is portable and runs on Mac, Windows, Linux and several other systems.

In this V8 introduction, we will ignore the implementation details of V8: they can be found on more authoritative sites (e.g. the  [V8 official site](https://v8.dev/)), and they change over time, often radically.

V8 is always evolving, just like the other JavaScript engines around, to speed up the Web and the Node.js ecosystem.

The Node.js ecosystem is huge and thanks to it V8 also powers desktop apps, with projects like Electron.

## Other JS engines

Other browsers have their own JavaScript engine:

-   Firefox has  [**SpiderMonkey**](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/SpiderMonkey)
-   Safari has  [**JavaScriptCore**](https://developer.apple.com/documentation/javascriptcore)  (also called Nitro)
-   Edge was originally based on  [**Chakra**](https://github.com/Microsoft/ChakraCore)  but has more recently been  [rebuilt using Chromium](https://support.microsoft.com/en-us/help/4501095/download-the-new-microsoft-edge-based-on-chromium)  and the V8 engine.

and many others exist as well.

## Interview Question

 - What is Node.js?
 - [Basics of Javascript required for Node js](https://nodejs.dev/learn/how-much-javascript-do-you-need-to-know-to-use-nodejs)
 - What is diff between Node.js & Browser ?
 - What is the runtime environment in Node.js?
 - How to create a simple server in Node.js?
 - How do Node.js works?
 - What is NPM & Yarn?
 - Is Node.js really Single-Threaded?
 - What is Node.js Process Model?
 - Explain Event Model ?
 - What is Event loop in Node.js? And How does it work?
 - What is the difference between Blocking and Non-blocking?
 - What is the difference between Asynchronous and Synchronus ?
 - Explain FS module.
 - What is Node js File system?
 - How to read File `fs.readFile()`?
 - How to  append File `fs.appendFile()` ?
 - How to open File `fs.open()`? 
 - How to writeFile `fs.writeFile()` ?
 - How to delete File `fs.unlink()` ? 
 - How to rename File `fs.rename()`?
 - What is HTTP module ?
 - What is `createServer()`?
 - What is `res.writeHead()`?
 - What is `URL() Module` ?
 - How to parse data from URL ?
 - What is streams in node js ?
 - Explain 4 types of streams?
 - Difference between Events and Callbacks?
 - What is an error-first callback?
 - What is callback hell in Node.js?
 - What are Promises in Node.js?
 - What is REPL? What purpose it is used for?
 - How to Debug Node Js Application ?
 - What is nodeman? How to configure ?
 - How does Node.js handle child threads?
 - What is fork & child Process ?
 - What does emitter do and what is dispatcher?
- How to kill child processes that spawn their own child processes in Node.js?
- What do you mean by Reactor Pattern in Node.js?
- What are the key features of Node.js?
- What are globals in Node.js?
- What is chaining process in Node.js?
- What is a control flow function? what are the steps does it execute?
 - What is the difference between Node.js vs Ajax?
 - What are the timing features of Node.js &  Explain process.nextTick() and setImmediate()?
- What is LTS releases of Node.js why should you care?
- Why should you separate Express 'app' and 'server'?
- Explain RESTful Web Services in Node.js?
- Since node is a single threaded process, how to make use of all CPUs?
- Why to use Express.js?
- How to use JSON Web Token (JWT) for authentication in node js?
- Explain middleware in Node.js
- How to add middleware in Node.js ?
- What is child_process ?
- How do you install, update, and delete a dependency?
- What is the difference between fork() and spawn() methods in Node.js?
- What is the purpose of NODE_ENV?
- What is Tracing in Node.js?
- What is `libuv`?
- What is the use of DNS module in Node.js?
- What is the passport in Node.js?
- What is Mongoose ?
- How to create Table Model in Node.js?
- How to connect with External DB like MONGODB & NOSQL?
- Explain Error Handling in node js?
- Explain the terms body-parser, cookie-parser, debug, jade, morgan, nodemon, pm2, serve-favicon, cors in Express JS?
- In which Language Node Js is written ?

- 



