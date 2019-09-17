# go-protobuf-marshalable-enums
## What's this?
This package's intention is to make enums marshalable, at least as far as JSON is concerned in the two primary protobuf implementations for go: [`golang/protobuf`][golang/protobuf] and [`gogo/protobuf`][gogo/protobuf].

## Why?
Protobufs make great generators for generic base types that are widely compatible. While enum types [do have a canonical mapping in json][proto3#json], jsonpb only accepts [`proto.Message` messages as marshalable JSON values.][golang/protobuf/jsonpb/jsonpb.go#Marshal].

## How?
The intention is to make changes as minimal as possible to the packages. By the looks of it, it should be as simple as implementing (EnumValue)[https://developers.google.com/protocol-buffers/docs/reference/google.protobuf#enumvalue] (as with the other types jsonpb allows)[https://github.com/golang/protobuf/blob/master/jsonpb/jsonpb.go#L210].

[golang/protobuf]: https://github.com/golang/protobuf
[gogo/protobuf]: https://github.com/golang/protobuf
[proto3#json]: https://developers.google.com/protocol-buffers/docs/proto3#json
[golang/protobuf/jsonpb/jsonpb.go#Marshal]: https://github.com/golang/protobuf/blob/master/jsonpb/jsonpb.go#L129