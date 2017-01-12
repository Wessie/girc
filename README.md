## girc is a flexible IRC library for Go

[![Build Status](https://travis-ci.org/lrstanley/girc.svg?branch=master)](https://travis-ci.org/lrstanley/girc)
[![GoDoc](https://godoc.org/github.com/lrstanley/girc?status.png)](https://godoc.org/github.com/lrstanley/girc)
[![Go Report Card](https://goreportcard.com/badge/github.com/lrstanley/girc)](https://goreportcard.com/report/github.com/lrstanley/girc)
[![IRC Chat](https://img.shields.io/badge/ByteIRC-%23L-blue.svg)](http://byteirc.org/channel/L)
[![GitHub Issues](https://img.shields.io/github/issues/lrstanley/girc.svg)](https://github.com/lrstanley/girc/issues)
[![license](https://img.shields.io/github/license/lrstanley/girc.svg)](https://raw.githubusercontent.com/lrstanley/girc/master/LICENSE)

## Features

- Focuses on simplicity, yet tries to still be flexible
- Only requires standard packages
- Event based triggering/responses
- Documentation is mostly on par
- At this time, **expect breaking changes to occur frequently**.

## TODO

- [ ] IRCv3 spec -- [details](http://ircv3.net):
  - [ ] [account-tag](http://ircv3.net/specs/extensions/account-tag-3.2.html)
  - [ ] [multi-prefix](http://ircv3.net/specs/extensions/multi-prefix-3.1.html)
  - [ ] [sasl](http://ircv3.net/specs/extensions/sasl-3.2.html)
  - [ ] [userhost-in-names](http://ircv3.net/specs/extensions/userhost-in-names-3.2.html)
  - [ ] [batches?](http://ircv3.net/specs/extensions/batch-3.2.html)
  - [ ] [extended-join](http://ircv3.net/specs/extensions/extended-join-3.1.html)
  - [ ] [cap-notify](http://ircv3.net/specs/extensions/cap-notify-3.2.html)
- [ ] ensure types `User` and `Channel` don't have any unexported fields, and that when they are given publically, it's not a pointer to internal state
- [ ] track with `NAMES` as well? would require rewrite of user existance logic, could also help track user modes
- [ ] write more function-specific examples as the api becomes much more stable
- [ ] client should support ping tracking (sending `PING`'s to the server)
  - [ ] with this, we can potentially find lag. `Client.Lag()` would be useful
  - [ ] allow support for changing the frequency of this?
- [ ] users need to be exposed in state somehow (other than `GetChannels()`)
- [ ] `MODE` tracking on a per-channel basis
- [ ] `Client.AddTmpCallback()` for one time use callbacks?
- [ ] add option to enable PRIVMSG/NOTICE text wrapping (and maybe per-default?) (`Config.DisableResponseWrap`?)
- [ ] optional flood toggle which uses `EventLimiter` so the user doesn't have to implement it themselves?
- [ ] allow support for proxy URLs (passing to `golang.org/x/net/proxy`?)
- [ ] allow users to specify a local/bind address using `net.Dialer{}.LocalAddr`
- [ ] add more generic helpers: `Away()`, `Invite()`, `Kick()`, `Oper()`, generic `Ping()` and `Pong()`, `VHost()`, `Whois()` and `Who()`

## Installing

    $ go get -u github.com/lrstanley/girc

## Examples

See [the examples](https://godoc.org/github.com/lrstanley/girc#example-package) within the documentation for real-world usecases.

## Contributing

Below are a few guidelines if you would like to contribute. Keep the code clean, standardized, and much of the quality should match Golang's standard library and common idioms.

   * Always test using the latest Go version.
   * Always use `gofmt` before committing anything.
   * Always have proper documentation before committing.
   * Keep the same whitespacing, documentation, and newline format as the rest of the project.
   * Only use 3rd party libraries if necessary. If only a small portion of the library is needed, simply rewrite it within the library to prevent useless imports.
   * Also see [golang/go/wiki/CodeReviewComments](https://github.com/golang/go/wiki/CodeReviewComments)

## License

```
The MIT License (MIT); Copyright (c) Liam Stanley <me@liamstanley.io>
```
