# Node.js Server Unresponsiveness Bug

This repository demonstrates a common issue in Node.js applications: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The `bug.js` file shows a server that becomes unresponsive because a 5-second CPU-bound loop blocks the event loop. The `bugSolution.js` file provides a corrected version using asynchronous operations and promises to prevent the event loop from being blocked.

## How to Reproduce

1. Clone the repository.
2. Run `node bug.js`.
3. Try to access the server (e.g., using `curl http://localhost:3000` or a web browser). Note the server's unresponsiveness.
4. Run `node bugSolution.js`.
5. Try to access the server again. You'll observe improved performance. 

## Solution

The solution involves refactoring the long-running task to use asynchronous operations or Promises, allowing other events to be processed while the task is in progress. The corrected version is in `bugSolution.js`.