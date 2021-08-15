# Caravan Kubernetes
This is a set of K8s resources that will help standardize and expedite spinning up resources.

This is being tested in a minikube environment.

## Included Resources
### MongoDB
- NoSQL DB for Document storage
- Included resource is a single node cluster with hard coded URLs until solution that allows dynamic scaling is discovered.
- Due to the nature of how this is set up, scaling up the StatefulSet causes it to be externally unavailable (the internal reference for URLs is what is retrieved by external tools, and it fails due to not being able to find the other replicas)

### MongoExpress 
- UI for MongoDB

### PostgreSQL
- SQL DB For Record Storage

### MariaDB
- High Performance SQL DB for High Speed Record Storage needs

### SQLPad
- A UI for PostgreSQL and MariaDB

Redis
- An in-memory data store and message broker

RabbitMQ
- A message queue service

Jenkins
- An automation server

