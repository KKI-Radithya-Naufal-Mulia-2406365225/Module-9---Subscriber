1. AMQP (Advanced Message Queuing Protocol) is an open standard protocol for message-oriented middleware that allows for the exchange of messages between applications regardless of the platform or language used.
2. First guest: The username needed to enter. Second guest: The password needed to enter. localhost: Tells the program that the post office is running on your own computer. 5672: The port number.
---
![Slow Subscriber](images/slowexample1.0.png)
What Happened: When the publisher was run multiple times in quick succession, it sent a total of 15 events to the broker almost instantly.
---
![Real Slow Subscriber](images/rabbitmq2.0.png)
![First Console VSCode](images/firstconsole.png)
![Second and Third Console Terminal](images/secondandthirdconsole.png)
What Happened: When I run three subscriber terminals, I'm basically implementing the Competing Consumers pattern. Instead of one subscriber struggling to process every message with a 1-second delay, RabbitMQ distributes the events across all active consumers. So, that's why in each console the name of the user aren't properly ordered.