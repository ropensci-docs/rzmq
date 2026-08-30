# initailize zmq context and zmq socket

initialize zmq context and zmq socket for to be used for further zmq
operations.

## Usage

``` r
init.context(threads=1L)
init.socket(context, socket.type)
```

## Arguments

- threads:

  number of threads for the context to use

- context:

  a zmq context object.

- socket.type:

  The ZMQ socket type requested e.g. ZMQ_REQ,ZMQ_REP,ZMQ_PULL,ZMQ_PUSH,
  etc.

## Value

`init.context` returns a zmq context object. `init.socket` returns a zmq
socket object.

## References

http://www.zeromq.org http://api.zeromq.org
http://zguide.zeromq.org/page:all

## Author

ZMQ was written by Martin Sustrik \<sustrik@250bpm.com\> and Martin
Lucina \<mato@kotelna.sk\>. rzmq was written by Whit Armstrong.

## See also

[`connect.socket`](https://docs.ropensci.org/rzmq/reference/connect.socket.md)`,`[`bind.socket`](https://docs.ropensci.org/rzmq/reference/bind.socket.md)`,`[`receive.socket`](https://docs.ropensci.org/rzmq/reference/receive.socket.md)`,`[`send.socket`](https://docs.ropensci.org/rzmq/reference/send.socket.md)`,`[`poll.socket`](https://docs.ropensci.org/rzmq/reference/poll.socket.md)

## Examples

``` r
if (FALSE) { # \dontrun{

library(rzmq)
context = init.context()
in.socket = init.socket(context,"ZMQ_PULL")
} # }
```
