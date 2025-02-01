# Unhandled Exception in Node.js HTTP Server

This example demonstrates a common error in Node.js where an unhandled exception within an HTTP server's request handler causes the server to crash.  The `bug.js` file shows the problematic code, while `bugSolution.js` provides a corrected version.

## Problem

Node.js doesn't automatically catch exceptions thrown within the request handler of an HTTP server.  If an unexpected error occurs, the server will terminate unexpectedly. This is demonstrated in `bug.js` where an unhandled exception is thrown if the URL is `/error`.

## Solution

The solution involves proper error handling within the request handler using try...catch blocks.  The corrected code in `bugSolution.js` gracefully handles the exception, preventing the server from crashing and logging the error for debugging purposes.  Alternatively,  using a process event listener like `uncaughtException` can globally catch errors, but this is often a less preferred approach as it masks problems rather than directly addressing them.  Always strive to handle errors at their source.