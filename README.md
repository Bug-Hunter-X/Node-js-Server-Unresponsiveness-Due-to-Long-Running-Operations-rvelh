# Node.js Server Unresponsiveness Due to Long-Running Operations

This repository demonstrates a common issue in Node.js servers: unresponsiveness caused by long-running operations within request handlers.  The provided `bug.js` file showcases the problem, while `bugSolution.js` offers a solution using asynchronous operations.

## Problem

Node.js is single-threaded.  If a request handler performs a lengthy operation (like a database query or file I/O) without using asynchronous methods, the entire server will block, preventing it from handling other requests.  This leads to poor performance and potential timeouts.

## Solution

The solution involves using asynchronous techniques like `setTimeout` with callbacks or Promises/async/await to prevent blocking.  This allows the server to continue processing other requests while long-running operations complete in the background.