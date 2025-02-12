# (google) Remote Procedure Calls1​ 

Open source system that works over HTTP/2 and Protobufs [link](https://github.com/grpc/grpc).

A remote producedure call (rcp) allows a program, call a function in a diferent program. It beeing in a different machine (reacheable via the network) or in the same machine but different processes. 

This resutl in low latency and high performance communication.

## Http/2

Improvments from Http/1:

- Request and responses are now in binary format
- Request and reponsed can be multiplexed on a single connection
- Headers are commpressed

in gRPC request and responses are transmited as Http/2 frames

## Protobuf

This is an opensource project to selerialize structured data. You can think of it as xml or json but faster, smaller and simplier.
The Protobufs supports an interface definition language (IDL) to define the contract between the client and the server. This contract includes functions exposed, structres and reponses. The protobuf IDL is strongly typed and suports forwards and backwards compatibility.


## Types

There are 4 types of rpcs:

- **Unary:** tipicall rest call
- **Server streaming:** one client call, and server responds with multiple messages
- **Client streaming:** multiple client calls, server responds with one msg
- **Bi-directional straming:** multiple calls by client and service

