# About.
protobuf-net is a long-standing .NET implementation of Google's "protocol buffers" (ProtoBuf) binary serialization format.

Traditionally, ProtoBuf uses a DSL ("proto2" or "proto3") to define document schemas. Breaking with tradition, protobuf-net doesn't force you to use schemas - being perfectly happy to work with POCO objects. However, if you use schemas, tools should be available to help you generate suitable POCOs from your schema.

protobuf-net has had tools to do this, but they have always been a hack - behind the scenes, "protogen" used Google's "protoc" tool to parse the model and compile it as a protobuf object, then deserialized the binary, then re-serialized it as xml, then ran the xml through xslt stylesheets. It worked, but... damn. This was very bad for cross-platform work: "protoc" is an OS-specific binary executable, and xslt has poor support in .NET cross-platform. Additionally, the tooling had lapsed and "proto3" had neven been implemented. Finally, the generated code has not been updated to use language improvements from multiple C# releases.

As part of protobuf-net 2.3.0, I'm dusting off the DSL tools; aims:

100% managed - no executables
modern C# output
full proto2 & proto3 support
… and just … better in every way than what I had before
It is far from complete, but: I'm getting there!

External tools
This site optionally makes use of "protoc", Google's protocol buffers compiler; the protoc tool is licensed by Google as part of protocol buffers, with full terms available here.
