# metronero-go
[![GoDoc](https://godoc.org/gitlab.com/metronero/metronero-go?status.svg)](https://godoc.org/gitlab.com/metronero/metronero-go)

Metronero API library. `api` subpackage exposes a client interface and error variables. `models` contains definitions of API requests, responses and error structs

## Usage

```go
package main

import (
    "net/http"
    "log"

    "gitlab.com/metronero/metronero-go/api"
)

func main() {
    cli = &api.ApiClient{
        Client:  http.DefaultClient,

        // Your Metronero backend instance
        BaseUrl: "https://mnero-1.digilol.net",
    }

    // Obtain an API token
    token, err := cli.PostLogin("cool_merchant", "1337password")
    if err != nil {
        log.Fatal(err)
    }

    // Get brief information about a merchant account
    merchant, err := cli.GetMerchant(token.Token)
    if err != nil {
        log.Fatal(err)
    }
}
```
