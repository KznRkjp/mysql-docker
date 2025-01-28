# MySQL Docker Setup

This repository contains a `docker-compose` configuration to set up a MySQL database.

## Prerequisites

- Docker
- Docker Compose

## Getting Started

1. Clone the repository:
    ```sh
    git clone https://github.com/KznRkjp/mysql-docker.git
    cd mysql-docker
    ```

2. Create a `.env` file to configure MySQL environment variables:
    ```sh
    cp .env.example .env
    ```

3. Update the `.env` file with your desired MySQL configuration:
    ```env
    MYSQL_ROOT_PASSWORD=your_root_password
    MYSQL_DATABASE=your_database
    MYSQL_USER=your_user
    MYSQL_PASSWORD=your_password
    ```

4. Start the MySQL container:
    ```sh
    docker-compose up -d
    ```

5. Verify that the container is running:
    ```sh
    docker-compose ps
    ```

## Services

- **MySQL**: Accessible on port `3906`.
  Why `3906`?  - Beacause I kept getting error `Access denied for user 'root'@'localhost' (using password: YES)' for all users in .env file. 
  Inspected my WSL and Windows to see if port is in use, but found nothing.
  Perhaps whis will help someone.

## Stopping the Containers

To stop the running containers:
```sh
docker-compose down
```

## Volumes

The MySQL data is stored in a Docker volume to persist data across container restarts.

## Troubleshooting

- Check the logs for any errors:
    ```sh
    docker-compose logs
    ```

## License

This project is licensed under the MIT License.

## Contributing

Feel free to open issues or submit pull requests for any improvements or bug fixes.

## Acknowledgements

- [Docker](https://www.docker.com/)
- [MySQL](https://www.mysql.com/)
