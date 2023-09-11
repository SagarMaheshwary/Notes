# RABBITMQ

### NOTES

- ##### Supported protocols:
  - AMQP (Advanced Messaging Queue Protocol)
  - MQTT (Message Queue Telemetry Transport)
  - STOMP (Simple (or Streaming) Text Orientated Messaging Protocol)
  - RabbitMQ Stream Protocol
  - Note: all RabbitMQ protocols are TCP based
- Channels: AMQP provides a way for connections to multiplex over a single TCP connection. That means an application can open multiple "lightweight connections" called sessions (channels) on a single connection.
- Max number of channels a single connection can create is 100 and it's controlled on the server by `channel_max = 100` configuration. Client libraries can also be configured to set the channel limit.
- A client that's sending a message is called **Producer/Publisher**.
- A client that's receiving a message is called **Consumer/Subscriber**.
- A **queue** is a buffer that stores messages.
- When you publish a message as "**persistent**", you are indicating that the message should survive server restarts or crashes. In other words, a persistent message will not be lost even if the message broker (e.g., RabbitMQ) goes down and then comes back up. This is achieved by setting the deliveryMode property of the message to 2.
- **Durable** queues are useful when you want to ensure that the queue itself is not lost, along with all the messages it contains. For example, if you have a queue that stores tasks that need to be processed, you would declare it as durable to avoid losing those tasks in case of a broker failure.
- The key difference between **persistent** and **durable** option is that "persistent" applies to individual messages, ensuring that they survive, while "durable" applies to queues, ensuring that the queues themselves survive. You can combine both properties to have a durable queue that stores persistent messages, ensuring both the durability of the queue and its messages. This combination provides a higher level of message reliability.
- ##### Queues:
  - Queues are a basic way of sending/receiving messages in RabbitMQ.
  - Each message from a queue is sent to only one client connected to that specific queue.
  - RabbitMQ also does load balancing in a round-robin fashion when sending messages from a single queue to multiple consumers connected to the same queue.
- ##### Work Queues (Task Queue)
  - Queues that have manual acknowledgement from consumers.
- ##### Exchanges (Pub/Sub)
  - An exchange is like a routing agent, a producer sends a message to an exchange rather than a queue and the exchanage routes the message to all the consumers connected to that exchange.
- ##### Exchange types: direct, topic, fanout, headers
  - **Fanout** is the most simple type. It is used for broadcasting messages to all the queues connected to the exchange.
  - **Direct**
  - **Topic**
  - **Headers**
