## Overview

The Hello World API is a single, stateless backend service exposed publicly
on the internet. It serves one purpose: respond to a request with a fixed
"Hello, World!" greeting, giving callers a trivially simple, always-available
endpoint to verify connectivity to a new environment or integration pipeline.
It requires no authentication, holds no data, and calls no other system.

## Context (C1)

```mermaid
graph TB
    caller["Caller<br/>(developer, script, monitoring probe)"]
    system["Hello World API"]

    caller -->|HTTP GET| system
```

## Domain model (ER)

No persistent entities exist in this system — the API is stateless and holds
no data.

## Key flows

```mermaid
sequenceDiagram
    participant Caller
    participant HelloAPI as Hello World API

    Caller->>HelloAPI: GET /hello
    HelloAPI-->>Caller: 200 OK { message: "Hello, World!" }
```