# Node.js Server Crash on High Load

This repository demonstrates a common issue in Node.js applications where the server crashes unexpectedly when it receives a large number of concurrent requests.  The problem stems from unhandled exceptions or resource exhaustion.  This example showcases the problem and provides a solution.

## Problem

The `server.js` file contains a basic HTTP server. Under heavy load, this server may crash due to unhandled exceptions or memory leaks.  The lack of proper error handling and resource management makes it vulnerable.

## Solution

The `server-fixed.js` file addresses this by implementing more robust error handling and resource management.  This improved version is more resilient to high load and less prone to unexpected crashes.

## How to reproduce

1. Clone this repository.
2. Run `server.js` using `node server.js`.
3. Simulate high load using tools like `ab` (Apache Benchmark) or a load testing tool of your choice.
4. Observe the server's behavior under load.  You'll likely see crashes or performance degradation.
5. Replace `server.js` with `server-fixed.js` and repeat steps 2-4.  The improved version should be significantly more stable.

## Lessons learned

- Always handle exceptions properly using `try...catch` blocks.
- Implement proper resource management, such as closing connections and releasing resources when they're no longer needed.
- Use a process manager like PM2 for better process supervision and automatic restarts in case of crashes. 
- Consider using a load balancer for distributing traffic across multiple server instances.