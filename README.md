# Multi-Threaded Caching Proxy Server
- A high-performance multi-threaded proxy server in C that supports HTTP GET requests and implements caching using the Least Recently Used (LRU) eviction policy.

# Features
- Multi-threaded: Handles multiple clients concurrently using POSIX threads.
- Caching: Speeds up repeated requests with an in-memory LRU cache.
- GET Request Forwarding: Forwards HTTP GET requests to remote servers.
- Concurrency Safe: Uses semaphores and mutexes to manage access to shared resources.
- Error Handling: Returns HTTP error codes like 400, 403, 404, 500, etc.

# Technologies Used
- C (POSIX Sockets & Threads)
- TCP/IP Networking
- LRU Cache via Linked List
- Semaphores (<semaphore.h>)
- Pthread mutex for synchronization

# Project Structure
- MultiThreaded_Proxy_Server_Client/
  ├── proxy_server_with_cache.c     # Main proxy server source code
  ├── proxy_parse.h / proxy_parse.c # Request parsing utilities
  ├── Makefile                      # Build file
  └── README.md                     # Project documentation

#  How to Build and Run
- in bash: make
- in bash: ./proxy 8080

# How It Works
- Client sends an HTTP GET request to the proxy.
- Proxy checks if the response is already in cache.
- If cached → returns the stored response.
- If not cached → forwards the request to remote server, receives the response, caches it, and sends it back to the client.
- Cache uses LRU policy to evict old items when space is full.

# Limitations
- Only supports HTTP GET requests.
- Does not support HTTPS.
- No persistent (disk-based) caching — in-memory only.

# Author
- [Harshit Jasuja](https://github.com/Harshitjasuja) 
- Computer Science Engineering Student
