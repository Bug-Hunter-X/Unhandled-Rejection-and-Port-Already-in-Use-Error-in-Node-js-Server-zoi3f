# Unhandled Rejection and Port Already in Use Error in Node.js Server
This repository demonstrates a common error in Node.js servers: unhandled rejection when the specified port is already in use, and how to handle it gracefully.

## Bug
The `bug.js` file contains a simple HTTP server.  It listens on port 8080. If this port is already in use (e.g., by another instance of the server or another application), the server will throw an error. The current implementation fails to handle this error properly, resulting in an unhandled rejection.

## Solution
The `bugSolution.js` file provides a solution. It uses a `try...catch` block to handle the `EADDRINUSE` error and includes proper error handling for the `server.on('error', ...)` event.

## How to reproduce
1. Clone this repository.
2. Run `node bug.js`.  Note the error if port 8080 is already in use.
3. Run `node bugSolution.js`. Observe the improved error handling.
