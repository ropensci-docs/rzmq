# Receive a message from the socket referenced by the socket argument.

The zmq_recv() function shall receive a message from the socket
referenced by the socket argument. If there are no messages available on
the specified socket, by default the function shall block until the
request can be satisfied. A non-blocking receive can be obtained by
setting dont.wait to TRUE If there are no messages available on the
specified socket, the receive.socket() call will return NULL
immediately.

## Usage

``` r
receive.socket(socket, unserialize=TRUE, dont.wait=FALSE)
receive.null.msg(socket)
receive.string(socket)
receive.int(socket)
receive.double(socket)
```

## Arguments

- socket:

  a zmq socket object

- unserialize:

  whether to call unserialize on the received data

- dont.wait:

  defaults to false, for blocking receive. Set to TRUE for non-blocking
  receive.

## Value

the value sent from the remote server or NULL on failure. If dont.wait
was TRUE and a message was not immediately available for receipt, NULL
is returned and get.zmq.errno() is set to 11 or get.zmq.strerror() is
set to EAGAIN.

## References

http://www.zeromq.org http://api.zeromq.org
http://zguide.zeromq.org/page:all

## Author

ZMQ was written by Martin Sustrik \<sustrik@250bpm.com\> and Martin
Lucina \<mato@kotelna.sk\>. rzmq was written by Whit Armstrong.

## See also

[`connect.socket`](https://docs.ropensci.org/rzmq/reference/connect.socket.md)`,`[`bind.socket`](https://docs.ropensci.org/rzmq/reference/bind.socket.md)`,receive.socket,`[`send.socket`](https://docs.ropensci.org/rzmq/reference/send.socket.md)`,`[`poll.socket`](https://docs.ropensci.org/rzmq/reference/poll.socket.md)

## Examples

``` r
if (FALSE) { # \dontrun{
library(rzmq)

remote.exec <- function(out.socket,in.socket,fun,...) {
    send.socket(out.socket,data=list(fun=fun,args=list(...)))
    receive.socket(in.socket)
}

context = init.context()
out.socket = init.socket(context,"ZMQ_PUSH")
bind.socket(out.socket,"tcp://*:5557")

in.socket = init.socket(context,"ZMQ_PULL")
bind.socket(in.socket,"tcp://*:5558")


myfun <- function(x) {
    sum(abs(x))
}

remote.exec(out.socket,in.socket,myfun,rnorm(1e3))

} # }
```
