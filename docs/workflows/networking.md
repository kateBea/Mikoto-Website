# Networking

Mikoto provides a lightweight networking layer on top of [Asio](https://github.com/chriskohlhoff/asio). The current scope includes TCP, HTTP, and HTTPS connections.

## Transport support

| Transport | Notes |
| --- | --- |
| TCP | Direct socket-based communication |
| HTTP | Available without OpenSSL |
| HTTPS | Requires OpenSSL on the target system |

When OpenSSL is unavailable, Mikoto falls back to HTTP-only support. Treat that fallback as a deployment decision: it is useful for local development but should not silently replace encrypted transport for production traffic.

## Integration mindset

Keep networking work off the render thread and make connection state explicit to the rest of the engine. The renderer should consume already-prepared game state rather than waiting on I/O.
