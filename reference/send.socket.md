# send a message.

Queue the message referenced by the msg argument to be sent to the
socket referenced by the socket argument.

A successful invocation of send.socket does not indicate that the
message has been transmitted to the network, only that it has been
queued on the socket and ZMQ has assumed responsibility for the message.

## Usage

``` r
send.socket(socket, data, send.more=FALSE, serialize=TRUE, xdr=.Platform$endian=="big")
send.null.msg(socket, send.more=FALSE)
send.raw.string(socket,data,send.more=FALSE)
```

## Arguments

- socket:

  a zmq socket object

- data:

  the R object to be sent

- send.more:

  whether this message has more frames to be sent

- serialize:

  whether to call serialize before sending the data

- xdr:

  passed directly to serialize command if serialize is requested

## Value

a boolean indicating success or failure of the operation.

## References

http://www.zeromq.org http://api.zeromq.org
http://zguide.zeromq.org/page:all

## Author

ZMQ was written by Martin Sustrik \<sustrik@250bpm.com\> and Martin
Lucina \<mato@kotelna.sk\>. rzmq was written by Whit Armstrong.

## See also

[`connect.socket`](https://docs.ropensci.org/rzmq/reference/connect.socket.md)`,`[`bind.socket`](https://docs.ropensci.org/rzmq/reference/bind.socket.md)`,`[`receive.socket`](https://docs.ropensci.org/rzmq/reference/receive.socket.md)`,send.socket,`[`poll.socket`](https://docs.ropensci.org/rzmq/reference/poll.socket.md)

## Examples

``` r
if (FALSE) { # \dontrun{

## remote execution server in rzmq
library(rzmq)
context = init.context()
in.socket = init.socket(context,"ZMQ_PULL")
bind.socket(in.socket,"tcp://*:5557")

out.socket = init.socket(context,"ZMQ_PUSH")
bind.socket(out.socket,"tcp://*:5558")

while(1) {
   msg = receive.socket(in.socket)
   fun <- msg$fun
   args <- msg$args
   print(args)
   ans <- do.call(fun,args)
   send.socket(out.socket,ans)
}
} # }
```
