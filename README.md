# Node.js Server Hang on Request

This repository demonstrates a common issue in Node.js where a server hangs due to blocking I/O operations.  The bug showcases how synchronous operations can lead to performance degradation and unresponsive servers.  The solution provides a corrected implementation using asynchronous patterns to ensure the server remains responsive even under significant load.

## Bug

The `bug.js` file contains a simple HTTP server that introduces a 5-second delay in the request handling.  This delay is a simulated blocking operation. Under high load, this blocking nature can cause the server to become unresponsive.

## Solution

The `bugSolution.js` file provides a solution that uses asynchronous methods to handle requests concurrently. This prevents the server from blocking, even with many simultaneous requests.

## How to Reproduce the Bug

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.
4. Make multiple requests to `http://localhost:3000/` using tools like `curl` or a web browser.  Observe the server response time, which will significantly increase with more concurrent requests.

## How to Test the Solution

1. Run `node bugSolution.js`.
2. Repeat the same multiple request test.  Observe that response time remains consistent, even with many requests.