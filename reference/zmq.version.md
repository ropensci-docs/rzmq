# get version of libzmq

return the version string of the system zmq library

## Usage

``` r
zmq.version()
```

## Value

a string of the following format: major.minor.patch

## References

http://www.zeromq.org http://api.zeromq.org
http://zguide.zeromq.org/page:all

## Author

ZMQ was written by Martin Sustrik \<sustrik@250bpm.com\> and Martin
Lucina \<mato@kotelna.sk\>. rzmq was written by Whit Armstrong.

## See also

[`connect.socket`](https://docs.ropensci.org/rzmq/reference/connect.socket.md)`,`[`bind.socket`](https://docs.ropensci.org/rzmq/reference/bind.socket.md)`,`[`receive.socket`](https://docs.ropensci.org/rzmq/reference/receive.socket.md)`,`[`send.socket`](https://docs.ropensci.org/rzmq/reference/send.socket.md)

## Examples

``` r
if (FALSE) { # \dontrun{

library(rzmq)
zmq.version()
} # }
```
