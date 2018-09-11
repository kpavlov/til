[Home](../README.md)

Object Serialization 
====================

Schema formats:

| Data Format | Type | Schema formats (contracts) | Comments |
| ----------- | ---- | --------------------------- | ------- |
| JSON        | Text | JSON Schema | |
| XML         | Text |XSM Schema (XSD) | |
| Protobuf    | Binary |Protobuf | Forward/Backward compatibility, very compact |
| [Thrift][thrift] | Binary ?| [Thrift][thrift] | |
| SOAP |Text | WSDL & XSD |
| Java serialization |Binary| POJO | Not secure, do not consider | 

Frameworks:

| Framework | Protocols | Features |
| --------- | --------- | -------- |
| Jackson   | JSON      | 
| Apache Avro | JSON   | * Schemas
| gRPC        | Protobuf | * Forward/Backward compatibility * Schemas |
| Protobuf     | Protobuf | * Forward/Backward compatibility * Schemas |
| 

[thrift]: http://thrift.apache.org "Apache Thrift"
