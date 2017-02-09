# log

a logger extend standard log package for baa.

* more log level, Info/Warn/Error/Debug
* more log method
* optimize log write
* used for configless

## Install

* dependent [setting](github.com/go-baa/setting) package
* optional config file: `conf/app.ini`

```
go get -u github.com/go-baa/setting
go get -u github.com/go-baa/log
```

## Usage

```
package main

import (
    "github.com/go-baa/log"
)

func main() {
    log.Println("xx")
    log.Debugln("xx")
}
```

## Config

config depend config file of `setting` ，you need add follow lines to config file：

```
// conf/app.ini
[default]
# output log to os.Stderr or filepath
log.file = os.Stderr
# 0 off, 1 fatal, 2 panic, 5 error, 6 warn, 10 info, 11 debug
log.level = 11
```

`log.file` setting log to file, it is be a file path, also can be `os.Stderr` or `os.Stdout`.
`log.level` setting log level, default is `5`, The greater the level of output error the more detailed.
 