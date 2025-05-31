# ctxkey

[![Go Reference](https://pkg.go.dev/badge/github.com/jackielii/ctxkey.svg)](https://pkg.go.dev/github.com/jackielii/ctxkey)

This package provides type safe context key. Forked from [tailscale.com/util/ctxkey](https://pkg.go.dev/tailscale.com/util/ctxkey)

## Install

```bash
go get github.com/jackielii/ctxkey
```

## Example usage:

```go
// Create a context key.
var timeoutCtx = ctxkey.New("timeout", 5*time.Second)

// Store a context value.
ctx = timeoutCtx.WithValue(ctx, 10*time.Second)

// Load a context value.
timeout := timeoutCtx.Value(ctx)
... // use timeout of type time.Duration
```

This is inspired by https://go.dev/issue/49189.
