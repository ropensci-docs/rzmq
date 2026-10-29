# set a socket option.

The zmq_setsockopt() function shall set the option specified by the
option_name argument to the value pointed to by the option_value
argument for the ZMQ socket pointed to by the socket argument.

## Usage

``` r
set.hwm(socket, option.value)
set.swap(socket, option.value)
set.affinity(socket, option.value)
set.identity(socket, option.value)
subscribe(socket, option.value)
unsubscribe(socket, option.value)
set.rate(socket, option.value)
set.recovery.ivl(socket, option.value)
set.recovery.ivl.msec(socket, option.value)
set.mcast.loop(socket, option.value)
set.sndbuf(socket, option.value)
set.rcvbuf(socket, option.value)
set.linger(socket, option.value)
set.reconnect.ivl(socket, option.value)
set.zmq.backlog(socket, option.value)
set.reconnect.ivl.max(socket, option.value)
get.rcvmore(socket)
get.last.endpoint(socket)
get.send.timeout(socket)
set.send.timeout(socket, option.value)
get.rcv.timeout(socket)
set.rcv.timeout(socket, option.value)
```

## Arguments

- socket:

  a zmq socket object

- option.value:

  the new option value to bet set

## Value

a boolean indicating success or failure of the operation or in the case
of getsocketoptions, the value of the requsted option.

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
socket = init.socket(context,"ZMQ_REQ")

set.hwm(socket, 1L)
set.swap(socket, 100L)
set.identity(socket, "big.ass.socket")
} # }
```
