# periph - Peripherals I/O in Go

[![mascot](https://raw.githubusercontent.com/periph/website/master/site/static/img/periph-mascot-280.png)](https://periph.io/)

Documentation is at https://periph.io

[![PkgGoDev](https://pkg.go.dev/badge/periph.io/x/conn)](https://pkg.go.dev/periph.io/x/conn)
[![Coverage
Status](https://codecov.io/gh/periph/conn/graph/badge.svg)](https://codecov.io/gh/periph/conn)

Join us for a chat on
[gophers.slack.com/messages/periph](https://gophers.slack.com/messages/periph),
get an [invite here](https://invite.slack.golangbridge.org/).


## Example

Blink a LED:

~~~go
package main

import (
    "time"
    "periph.io/x/conn/gpio"
    "periph.io/x/host"
    "periph.io/x/host/rpi"
)

func main() {
    host.Init()
    t := time.NewTicker(500 * time.Millisecond)
    for l := gpio.Low; ; l = !l {
        rpi.P1_33.Out(l)
        <-t.C
    }
}
~~~

Curious? Look at [supported devices](https://periph.io/device/) for more
examples!


## Authors

`periph` was initiated with ❤️️ and passion by [Marc-Antoine
Ruel](https://github.com/maruel). The full list of contributors is in
[AUTHORS](https://github.com/periph/conn/blob/main/AUTHORS) and
[CONTRIBUTORS](https://github.com/periph/conn/blob/main/CONTRIBUTORS).


## Disclaimer

This is not an official Google product (experimental or otherwise), it
is just code that happens to be owned by Google.

This project is not affiliated with the Go project.
