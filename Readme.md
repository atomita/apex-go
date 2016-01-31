
# Apex Golang

Golang runtime support for Apex/Lambda – providing handlers for Lambda sources, and runtime requirements such as interacting with the Node.js shim, and implementing environment variables.

```go
package main

import (
	"encoding/json"

	"github.com/apex/go-apex"
)

type message struct {
	Value string `json:"value"`
}

func main() {
	apex.HandleFunc(func(event json.RawMessage, ctx *apex.Context) (interface{}, error) {
		return &message{"Hello World"}, nil
	})
}
```

## Features

Currently supports:

- Node.js shim
- Environment variable population
- Arbitrary JSON
- CloudWatch Logs
- Cognito
- Kinesis
- Dynamo
- S3
- SNS
- SES

## Contributors

- [TJ Holowaychuk](https://github.com/tj)

## Badges

[![Build Status](https://semaphoreci.com/api/v1/projects/66c27cb2-5e00-469e-bfa0-b577cac48053/675168/badge.svg)](https://semaphoreci.com/tj/go-apex)
[![GoDoc](https://godoc.org/github.com/apex/go-apex?status.svg)](https://godoc.org/github.com/apex/go-apex)
![](https://img.shields.io/badge/license-MIT-blue.svg)
![](https://img.shields.io/badge/status-stable-green.svg)

---

> [tjholowaychuk.com](http://tjholowaychuk.com) &nbsp;&middot;&nbsp;
> GitHub [@tj](https://github.com/tj) &nbsp;&middot;&nbsp;
> Twitter [@tjholowaychuk](https://twitter.com/tjholowaychuk)
