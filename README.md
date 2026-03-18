# GopherLB

A minimal Go HTTP load balancer using round-robin routing and reverse proxying.

## What it does
- Listens on `localhost:8000`
- Forwards incoming requests to configured upstream servers
- Rotates targets in round-robin order

Current upstreams in [src/main.go](src/main.go):
- `http://httpbin.org`
- `https://postman-echo.com`
- `http://httpbin.org`

## Run
```bash
cd src
go run main.go
```

Then open:
- `http://localhost:8000/`

## Notes
- `IsAlive()` currently always returns `true` (no real health checks yet)
- Upstream list and port are hardcoded in [src/main.go](src/main.go)
