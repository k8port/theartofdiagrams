# API Demo

## Nav Bar

- [HTTP Calls](/#http-calls)
- [Graph](/#graph)
- [Sequence](/#sequence)

## HTTP Calls

```mermaid
sequenceDiagram
    participant Client
    participant Server

   plain Client->>Server: HTTP GET /api/items
    alt Request successful
        Server-->>Client: 200 OK \n { "items": [...] }
    else Request failed
        Server-->>Client: 404 Not Found \n { "error": "Items not found" }
    end
```

## Graph

```mermaid
flowchart LR
    accTitle: API Flow
    accDescr: API Gateway is a single entry point for all API requests. It routes requests to the appropriate API server based on the request path. The API server is responsible for handling the request and returning the response. The database is responsible for storing the data.
    A@{ shape: stadium, label: "Client"}
    B@{ shape: delay, label: "API Gateway" }
    C@{ shape: st-rect, label: "Server"}
    D@{ shape: cyl, label: "Database"}
    A --> | Request | B
    B --> C
    C --> D
    D --> C
    C --> B
    B --> | Response | A
```

## Sequence

```mermaid
sequenceDiagram
    participant Client
    participant Server

    Client->>Server: HTTP GET /api/items
    Server-->>Client: 200 OK \n { "items": [...] }
```
