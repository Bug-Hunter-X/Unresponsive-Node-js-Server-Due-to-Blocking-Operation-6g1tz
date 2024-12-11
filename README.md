# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js applications: an unresponsive server caused by a long-running synchronous operation that blocks the event loop.  The provided `server.js` file contains a simple HTTP server with a request handler that performs a CPU-intensive task for 5 seconds. This blocks the event loop, preventing the server from responding to other requests.

The `serverSolution.js` file demonstrates how to solve this problem using asynchronous operations or by offloading the long-running task to a worker thread. 

## How to Reproduce

1. Clone this repository.
2. Run `node server.js`.
3. Make a request to `http://localhost:3000`. You'll see the response eventually, but any other requests will be ignored during that 5-second period. 

## Solution

The solution is available in the `serverSolution.js` file.  It uses asynchronous programming to avoid blocking the event loop.