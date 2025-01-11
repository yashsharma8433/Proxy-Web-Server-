Key Features:
Multithreading:

Each client connection is handled by a separate thread.
Threads are managed with a semaphore to control the number of concurrent connections (MAX_CLIENTS).
Caching:

HTTP responses are cached in a linked list (cache_element structure) to improve performance.
An LRU (Least Recently Used) mechanism ensures that older entries are replaced when the cache exceeds MAX_SIZE.
HTTP Error Handling:

Proper error messages (e.g., 400, 403, 404, 500) are sent to the client based on the type of request or response errors.
Socket Management:

The proxy server listens for connections on a specified port (default: 8080).
Handles HTTP communication with remote servers on behalf of clients.
Request Parsing:

Uses a helper library (proxy_parse.h) to parse HTTP requests.
Dynamic Memory Management:

The proxy allocates memory dynamically to handle incoming requests and responses.
Concurrency Safety:

A mutex lock (pthread_mutex_t lock) is used to ensure thread-safe access to shared resources like the cache.
