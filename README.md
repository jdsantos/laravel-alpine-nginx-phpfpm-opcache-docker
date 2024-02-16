
![LANPOD](https://raw.githubusercontent.com/jdsantos/laravel-alpine-nginx-phpfpm-opcache-docker/docs/banner.png)
============

## LANPOD - Deployment recipe featuring: Laravel + Alpine + NGINX + PHP-FPM + OPCache + Docker

This repository provides a recipe for deploying your Laravel 10 applications using Docker. The Docker setup includes Laravel 10, Alpine, Nginx, PHP-FPM, Supervisor and OPCache for optimized performance.

### Getting Started

If you clone this repo, only Docker is required to be installed on your machine! Feel free to use and change in any way possible this template. Follow the steps below to set this up in your local environment and give it a try!

### Prerequisites

Make sure you have Docker installed on your machine. You can download it from [Docker's official website](https://www.docker.com/get-started).

### Installation

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/jdsantos/laravel-alpine-nginx-phpfpm-opcache-docker.git
    ```

2. Navigate to the project directory:

    ```bash
    cd laravel-alpine-nginx-phpfpm-opcache-docker
    ```

3. Build and run the Docker containers:

    ```bash
    docker-compose up -d --build
    ```

4. Access your Laravel application at [http://localhost:8080](http://localhost:8080).

### What's in the box?

The Docker setup includes the following components:

- **Alpine Linux**: Lightweight Linux distribution for the base image.
- **Supervisor**: Process control system to manage multiple processes.
- **Nginx**: Web server for serving the Laravel application.
- **PHP-FPM**: PHP FastCGI Process Manager for handling PHP requests.
- **OPCache**: PHP Opcode caching for improved performance.

---

### Customization

After cloning this repo, you should paste in your Laravel app code inside the "laravel" directory. If you prefer, copy only the following onto your project:

 - Dockerfile
 - entrypoint.sh
 - conf.d

It should work just fine!

### Contributing

Any contributions to this project are more than welcome. Feel free to reach me and I will gladly include any improvements or ideas that you may have.
Please, fork this repository, make any changes and submit a PR and let's get in touch!

### Contributors

| <a href="http://jdsantos.github.io" target="_blank">**Jorge Santos**</a>
|:---:|
| [![jdsantos](https://avatars1.githubusercontent.com/u/1708961?v=3&s=50)](http://jdsantos.github.io)    | 
| <a href="https://github.com/jdsantos" target="_blank">`github.com/jdsantos`</a>

### License

This project is open-source software licensed under the [MIT license](LICENSE).
