# get libzmq error numbers and error strings

return the error number or error description after a zmq call

## Usage

``` r
zmq.errno()
zmq.strerror()
```

## Value

an integer for zmq.errno or a string for zmq.strerror

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
zmq.errno()
zmq.strerror()
} # }
```
