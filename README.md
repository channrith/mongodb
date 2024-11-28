# MongoDB Docker Compose Setup
This repository contains a Docker Compose configuration to run a MongoDB instance in a containerized environment. The configuration ensures persistent storage, configurable environment variables, and seamless integration with other services via a custom network.

## Features
- MongoDB Version: Uses the official MongoDB 6.0 image.
- Persistent Data Storage: Ensures that data and configuration files persist even after container restarts.
- Customizable Configuration: Allows configuration of the database, root username, and password via environment variables.
- Predefined Network: Integrates with other services via the local_docker network.

## Setup
1. Clone this repository:

    ```
    git clone <repository_url>
    cd <repository_directory>
    ```

2. Create a .env file to configure environment variables:

    ```
    MONGO_INITDB_ROOT_USERNAME=root
    MONGO_INITDB_ROOT_PASSWORD=secret
    MONGO_INITDB_DATABASE=sample_db
    ```
    Replace values as needed.

3. Ensure the local_docker network exists. If not, create it:

    ```
    docker network create local_docker
    ```

4. Start the MongoDB container:

    ```
    docker-compose up -d
    ```

## Usage
### Connect with MongoDB Compass
1. Open MongoDB Compass.
2. Use the following connection string:
    ```
    mongodb://<username>:<password>@localhost:27017/<database>
    ```
    Replace `<username>`, `<password>`, and `<database>` with your configured values.