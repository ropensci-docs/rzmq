# create a message object.

Create a ZeroMQ message object that can be sent multiple times

## Usage

``` r
init.message(data, serialize=TRUE, xdr=.Platform$endian=="big")
```

## Arguments

- data:

  the R object to be sent

- serialize:

  whether to call serialize before sending the data

- xdr:

  passed directly to serialize command if serialize is requested

## Value

a ZeroMQ message object as external pointer

## References

http://www.zeromq.org http://api.zeromq.org
http://zguide.zeromq.org/page:all

## Author

ZMQ was written by Martin Sustrik \<sustrik@250bpm.com\> and Martin
Lucina \<mato@kotelna.sk\>. rzmq was written by Whit Armstrong.

## See also

[`send.message.object`](https://docs.ropensci.org/rzmq/reference/send.socket.md)

## Examples

``` r
if (FALSE) { # \dontrun{

## remote execution server in rzmq
library(rzmq)
data = list(x=5)
msg = init.message(data)
} # }
```
