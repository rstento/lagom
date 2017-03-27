#Internal and external communication

Lagom promotes use of asynchronous communication without preventing use of synchronous communication where necessary. For example, as mentioned in [[Polyglot systems with Lagom|PolyglotSystems]], legacy application components might use synchronous communication that cannot be changed. Within your system, services might communicate with other services in the same node and services in other nodes.  

<!---For example, in the following diagram (see slide 5), notice the microservices running in a cluster on separate nodes (JVMs). The microservices in the cluster communicate with each other. Outside the cluster, a Service Gateway, a message broker, and other services also exchange messages. You can choose the type of communication appropriate for each service, whether that is: WebSockets, Akka pub-sub, or the Kafka message broker, and for services that need persistence, event streams. In the example, where all communication is asynchronous, failures or latency will not prevent any individual service from doing its job. -->

 