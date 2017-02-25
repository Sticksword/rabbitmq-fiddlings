## Explorations with RabbitMQ

##### Different use cases include:
* Work queues (directed work commands)
* Pub/Sub model (Publisher and Subscribers)
* RPC model (Client and Server, where each play both consumer and producer roles)

##### Idea is common across all use cases:
* establish connection to rabbitmq (on `localhost` or elsewhere)
* make a channel
* declare an exchange if you plan on using specific type of exchange
* declare a queue if you plan on using specific named queue, else can use temporary queues
* to send to a queue/channel, use `channel.basic_publish()`
* to receive from a queue/channel, use `channel.basic_consume()`

Special thanks to Pivotal and the team at RabbitMQ for the great tutorials and docs

See more: https://www.rabbitmq.com/

##### Associated files and data flow:
* send.py --> receive.py
* new_task.py --> worker.py
* emit_log.py --> receive_logs.py
* emit_log_direct.py --> receive_logs_direct.py
* emit_log_topic.py --> receive_logs_topic.py
* rpc_client.py <--> rpc_server.py
