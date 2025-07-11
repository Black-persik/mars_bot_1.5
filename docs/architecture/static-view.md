![UML Diagram](photo_2025-07-06_21-20-50.jpg)

**Cohesion**

- Telegram Bot is responsible only for receiving and sending messages to the user.

- Middleware handles the processing and routing of requests between components.

- The Database Connector implements all the logic of accessing the database.

- LLM is solely responsible for generating responses based on the received data.

- The database stores all the necessary information and query history.


**Coupling**

- Telegram Bot does not interact directly with either the LLM or the database — it only works with Middleware.

- Middleware acts as the central link, receiving requests from the bot, accessing the database through the Database Connector and interacting with the LLM to receive a response.


**Maintainability of our product**

1) Using a separate connector for working with the database and weak component interdependence (low coupling) make it easy to update or replace the database without significant changes to the rest of the system.

2) The Telegram Bot component can be removed, and the same business logic can be embedded directly into the customer's existing application without significant rework.
