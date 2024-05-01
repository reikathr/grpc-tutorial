#### Nama: Athira Reika
#### NPM: 2206031422
#### Kelas: Adpro B
---
### Refleksi
<ol>
<li>What are the key differences between unary, server streaming, and bi-directional streaming RPC (Remote Procedure Call) methods, and in what scenarios would each be most suitable?</li>
<p>Answer: Unary RPC involves a single request from the client and a single response from the server, it's suitable for simple interactions. Server Streaming RPC is where the client sends a single request and receives a stream of responses from the server, good for when you have to do large or continuous data transfers. Bi-directional Streaming RPC is when client and server establish a persistent connection and exchange streams of messages at the same time, which is good for when you need real-time interactions and concurrent data exchange.
<li>What are the potential security considerations involved in implementing a gRPC service in Rust, particularly regarding authentication, authorization, and data encryption?</li>
<p>Answer: It's important to implement authentication, authorization, and data encryption when using gRPC to make sure that only authenticated services get to make a connection (which can be done with authentication mechanisms like OAuth2 or JWT), that different services have access to different resources through authorization (using role-based access control), and that the data is protected when it's on its way with data encryption.
<li>What are the potential challenges or issues that may arise when handling bidirectional streaming in Rust gRPC, especially in scenarios like chat applications?</li>
<p>Answer: Some potential challenges include ensuring thread safety and managing concurrent access to shared resources, managing connections between clients and the server (including handling establishment, termination, and network failures), scalability and performance, error-handling, and ensuring data safety. In the case of chat applications, it might be difficult to maintain concurrency and prevent race conditions. When a connection is on for too long, it might burden the server. Also, encryption needs to be implemented well because nobody wants their chats leaked or the data they're sending over be tampered with before it gets to the recipient.
<li>What are the advantages and disadvantages of using the tokio_stream::wrappers::ReceiverStream for streaming responses in Rust gRPC services?</li>
<p>Answer: The advantages involve its compatibility with Tokio as well as its asynchronous processing which speeds things up and utilizes resources well. It's also flexible and can handle different types of data streams. The disadvantages are the complexity in concurrency and error-handling and the fact that it's dependent on Tokio means it's less portable.
<li>In what ways could the Rust gRPC code be structured to facilitate code reuse and modularity, promoting maintainability and extensibility over time?</li>
<p>Answer: Separating business logic and different modules will make the app easier to maintain and add to in the future. You can also use traits for reusable behaviors.
<li>In the MyPaymentService implementation, what additional steps might be necessary to handle more complex payment processing logic?</li>
<p>Answer: Adding data validation will increase the safety of the whole process. The current implementation is an implementation of the unary RPC, but a server-streaming RPC might be better if we want the client to constantly receive updates and progress on the payment status.
<li>What impact does the adoption of gRPC as a communication protocol have on the overall architecture and design of distributed systems, particularly in terms of interoperability with other technologies and platforms?</li>
<p>Answer: There's benefits and challenges that come with the impact. On one hand, benefits include language-agnostic service contracts with Protocol Buffers, efficient communication via HTTP/2, and support for polyglot microservices. On the other hand, the challenges include integrating with non-gRPC systems and investing in new tooling. 
<li>What are the advantages and disadvantages of using HTTP/2, the underlying protocol for gRPC, compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs?</li>
<p>Answer: 
Advantages include the fact that concurrency improves performance, header compression reduces overhead, server push enhances efficiency by pushing resources to clients, and that binary framing simplifies parsing and processing. Disadvantages include the fact that it requires TLS, adding complexity and overhead, it may require updated infrastructure and tooling, and it may not be fully supported by all clients and servers. In short, it has better potential in performance but may need additional tooling.
<li>How does the request-response model of REST APIs contrast with the bidirectional streaming capabilities of gRPC in terms of real-time communication and responsiveness?</li>
<p>Answer: REST APIs rely on the request-response model, which can introduce latency and decrease responsiveness for real-time communication, while gRPC's bidirectional streaming capabilities enable low-latency, real-time communication between clients and servers, which makes it more suitable for real-time applications that require immediate feedback and synchronized updates.
<li>What are the implications of the schema-based approach of gRPC, using Protocol Buffers, compared to the more flexible, schema-less nature of JSON in REST API payloads?</li>
<p>Answer: Protocol buffers are more strict and require predefined message types and fields which ensures consistency and type-safety, unlike JSON. Protocol buffers also use binary serialization which typically results in smaller payload sizes and faster serialization/deserialization compared to JSON. It also  provides strong tooling support, including code generation for client and server stubs in various programming languages. 
</ol>