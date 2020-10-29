<p style="background: white; padding: 25px 0px 0px 0px" align="center">
    <a href="https://disk.yandex.com/" target="_blank" rel="noopener">
        <img src="https://yastatic.net/s3/auth2/_/logo-red_en.1d255bcb.svg" alt="Yandex.Disk" width="400" height="200"/> 
    </a>
     <a href="https://disk.yandex.com/" target="_blank" rel="noopener">
            <img src="https://golang.org/doc/gopher/run.png" alt="Yandex.Disk" width="194" height="180"/> 
    </a>
</p>

Yandex Disk SDK on GoLand

It is a fast, safe and efficient tool that works immediately after installation.

[![Build Status](https://travis-ci.com/nikitaksv/yandex-disk-sdk-go.svg?branch=master)](https://travis-ci.com/nikitaksv/yandex-disk-sdk-go)
[![Coverage Status](https://coveralls.io/repos/github/nikitaksv/yandex-disk-sdk-go/badge.svg)](https://coveralls.io/github/nikitaksv/yandex-disk-sdk-go)
[![CodeFactor](https://www.codefactor.io/repository/github/nikitaksv/yandex-disk-sdk-go/badge)](https://www.codefactor.io/repository/github/nikitaksv/yandex-disk-sdk-go)
-

Installation
------------

Use module (recommended)
```go
import "github.com/shamilsun/yandex-disk-sdk-go"
```

Use vendor
```sh
go get github.com/shamilsun/yandex-disk-sdk-go
```

Documentation
-------------

**Useful links on official docs:**

* [Rest API Disk](https://tech.yandex.com/disk/rest/)
* [API Documentation](https://tech.yandex.com/disk/api/concepts/about-docpage/)
* [Try API](https://tech.yandex.com/disk/poligon/)
* [Get Token](https://tech.yandex.com/oauth/) 


Create new instance Yandex.Disk

```go
yaDiskWithOAuthAuth,err := yadisk.NewYaDisk(ctx.Background(),http.DefaultClient, &yadisk.Token{
    AccessToken: "YOUR_TOKEN",
	AuthType: EAuthType.OAuthToken
})

yaDiskWithBasicAuth,err := yadisk.NewYaDisk(ctx.Background(),http.DefaultClient, &yadisk.Token{
	AuthType: EAuthType.BasicHttpsAuth
    Login: "login",
    Password: "Password"
})


if err != nil {
    panic(err.Error())
}
disk,err := yaDisk.GetDisk([]string{})
if err != nil {
    // If response get error
    e, ok := err.(*yadisk.Error)
    if !ok {
        panic(err.Error())
    }
    // e.ErrorID
    // e.Message
}
```
