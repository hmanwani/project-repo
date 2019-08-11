# Installation and Configuration

This section describes the installation process for ownCloud with Docker. To install ownCloud manually, please refer [Manual Installation Link](https://doc.owncloud.org/server/10.2/admin_manual/installation/manual_installation.html).

## System Requirements

Before starting the installation, ensure that you have a system with the recommended environment as follows:

Platform         | Option
---------------- | ---------------------------------------
Operating System | Ubuntu 18.04 LTS
Database         | MariaDB 10+
Web Server       | Apache 2.4 with `prefork` and `mod_php`
PHP Runtime      | 7.2

For more information, please refer [System Requirements for ownCloud](https://doc.owncloud.org/server/10.2/admin_manual/installation/system_requirements.html).

## Installing ownCloud with Docker

You can install ownCloud with Docker, using the official ownCloud Docker image, which accesses the data volume in the host filesystem with separate _MariaDB_ and _Redis_ containers.

### Installing ownCloud on a Local Machine

Perform the following steps to start the installation on your local machine.

1. Create a new project directory.

  ```
  mkdir owncloud-docker-server

  cd owncloud-docker-server
  ```

2. Copy `docker-compose.yml` from the GitHub repository.

  ```
  wget https://raw.githubusercontent.com/owncloud/docs/master/modules/admin_manual/examples/installation/docker/docker-compose.yml
  ```

3. Create the environment configuration file.

  ```
  cat << EOF > .env
  OWNCLOUD_VERSION=10.0
  OWNCLOUD_DOMAIN=localhost
  ADMIN_USERNAME=admin
  ADMIN_PASSWORD=admin
  HTTP_PORT=8080
  EOF
  ```

  Also, you can enable the users to connect to the ownCloud server using its IP address with port 8080\. For example, if ownCloud server's IP address is 192.168.1.50, then add `192.168.1.50` as `OWNCLOUD_DOMAIN` value.

  ```
  cat << EOF > .env
  OWNCLOUD_VERSION=10.0
  OWNCLOUD_DOMAIN=192.168.1.50
  ADMIN_USERNAME=admin
  ADMIN_PASSWORD=admin
  HTTP_PORT=8080
  EOF
  ```

4. Build and start the container.

  ```
  docker-compose up -d
  ```

5. Verify that the containers are running successfully. To verify run `docker-compose ps`.

  **NOTE:** When all containers are running successfully, the ownCloud takes some time to be completely functional. If you run `docker-compose logs --follow owncloud` and see a significant amount of information logging to the console, then wait until it slows down to attempting the access of web UI.

## Logging In to the Web UI

To log in to the ownCloud UI:

1. Go to <http://localhost:8080>.

  **NOTE:** In case the server's IP address is added as the value of `OWNCLOUD_DOMAIN` in the `.env` file, then go to <http://IP_Address:8080>. For example, <http://192.168.1.50:8080>.

  The standard ownCloud login screen appears.

  ![ownCloud UI](/images/2019/08/owncloud-ui-login.png)

2. Enter the admin username and password, which you stored in `.env` file, and press Enter.
