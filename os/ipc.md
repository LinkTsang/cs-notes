# Inter-Process Communication

```
IPC := {LPC, RPC, ...}
IPC := Inter-Process Communication
LPC := Local Procedure Call
RPC := Remote Procedure Call
```

## RPC Framework

### Overview

- [Apache Avro](https://avro.apache.org/)
- [Apache Thrift](https://thrift.apache.org)
- [gRPC](https://grpc.io/docs/)
- [ICE: Internet Communications Engine](https://github.com/zeroc-ice/ice)
- [JSON-RPC](https://www.jsonrpc.org/specification)
- [Mojo](https://chromium.googlesource.com/chromium/src/+/master/mojo/README.md)
- [WCF: Windows Communication Foundation](https://docs.microsoft.com/en-us/dotnet/framework/wcf/whats-wcf)
- [XML-RPC](http://xmlrpc.com/)

### 需求

- 面向服务的封装
  - 服务发现
  - 负载均衡
  - 熔断降级
  - 等等
- 针对服务的可用性和效率等进行优化

### 对比

- HTTP/TCP/UDP/WebSocket/Socket/...

  - 缺点
    - HTTP/2 之前的协议开销大
    - 需要自己实现数据封装
    - 需要自己实现客户端、服务端
    - 关注底层协议、状态

- XML-RPC/JSON-RPC/SOAP/RESTful

- gRPC

  - 基于 HTTP/2

- Apache Thrift

### See Also

- [知乎：既然有 HTTP 请求，为什么还要用 RPC 调用？](https://www.zhihu.com/question/41609070)

## Data Serialization Formats

- Protobuf
- XML
- JSON

### See Also

- [Wikipedia: Comparison of data-serialization formats](https://en.wikipedia.org/wiki/Comparison_of_data-serialization_formats)
