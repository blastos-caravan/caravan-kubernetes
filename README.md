# Caravan Kubernetes
This is a set of K8s resources that will help standardize and expedite spinning up resources.

This is being tested in a minikube environment. It is also NOT production ready, and should only be used for development purposes.

## Use in Docker Desktop Kubernetes
 - Clone Repository
 - Within the repository directory, use kubectl apply -f . -R to apply all resources.
 - Use kubectl proxy to enable use of internal resources.
   - localhost:8081 - Mongo Express
   - localhost:3000 - SQLPad
   - localhost:27017 - MongoDB
   - localhost:6379 - Redis
   - localhost:5672 - RabbitMQ
   - localhost:4200 - Jenkins

## Included Resources
### MongoDB
- NoSQL DB for Document storage.
- Included resource is a single node cluster with hard coded URLs until solution that allows dynamic scaling is discovered.
- Due to the nature of how this is set up, scaling up the StatefulSet causes it to be externally unavailable (the internal reference for URLs is what is retrieved by external tools, and it fails due to not being able to find the other replicas)

### MongoExpress
- UI for MongoDB.
- Requires a Secret named `mongodb-secret`. This contains 2 keys.
  - `mongo-root-password` - The root password for your MongoDB instance that you configure yourself.
  - `mongo-root-username` - The root username for your MongoDB instance that you configure yourself.

### PostgreSQL
- SQL DB For Record Storage.
- Requires a Secret named `postgres-secret`. This contains 2 keys.
  - `postgres-root-password` - The root password for your PostgreSQL server
  - `postgres-root-email` - The admin email for your PostgreSQL server

### MariaDB
- High Performance SQL DB for High Speed Record Storage needs.
- Requires a Secret named `mariadb-secret`. This contains 1 key.
  - `mariadb-root-password` - The root password for your MariaDB server.

### SQLPad
- A UI for PostgreSQL and MariaDB.
- Requires a Secret named `sqlpad-secret`. This contains 2 keys.
  - `sqlpad-root-password` - Default user password
  - `sqlpad-root-email` - Default user email

### Redis
- An in-memory data store and message broker.

### RabbitMQ
- A message queue service.

### Jenkins
- An automation server.

