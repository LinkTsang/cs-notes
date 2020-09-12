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

### See Also

- [知乎：既然有 HTTP 请求，为什么还要用 RPC 调用？](https://www.zhihu.com/question/41609070)

## Data Serialization Formats

- Protobuf
- XML
- JSON

### See Also

- [Wikipedia: Comparison of data-serialization formats](https://en.wikipedia.org/wiki/Comparison_of_data-serialization_formats)
