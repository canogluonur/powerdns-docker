# powerdns-docker
Docker-based PowerDNS setup and management tools. Offers quick deployment and easy customization for efficient DNS operations


## Quick Start

1. Clone this repository:
   ```
   git clone https://github.com/canogluonur/powerdns-docker.git
   cd powerdns-docker
   ```

2. (Optional) Modify the `.env` file to customize environment variables.

3. Start the services:
   ```
   docker-compose up -d
   ```

## Components

This setup includes the following components:

- PowerDNS Recursor
- PowerDNS Server (Master)
- PowerDNS Server (Slave)
- MariaDB (MySQL)
- PowerDNS Admin
- phpMyAdmin

## Configuration

The `docker-compose.yml` file defines the following services:

1. `pdns-recursor-mysql`: PowerDNS Recursor
2. `mariadb`: MySQL database
3. `phpmyadmin`: Web interface for MySQL management
4. `pdns-mysql-master`: PowerDNS master server
5. `pdns-mysql-slave`: PowerDNS slave server
6. `pdns-admin-mysql`: PowerDNS Admin interface

### Customization

You can customize the setup by modifying the environment variables in the `docker-compose.yml` file or by creating a `.env` file with the following variables:

- `RECURSOR_TAG`: Tag for the PowerDNS Recursor image
- `PDNS_MYSQL_TAG`: Tag for the PowerDNS MySQL image
- `MYSQL_ROOT_PASSWORD`: Root password for MariaDB
- `PDNS_gmysql_password`: MySQL password for PowerDNS
- `PDNS_api_key`: API key for PowerDNS
- `PDNS_ADMIN_SQLA_DB_PASSWORD`: Database password for PowerDNS Admin


## Ports

- PowerDNS: 53 (TCP/UDP)
- phpMyAdmin: 8989
- PowerDNS Admin: 8080

## Usage

After starting the services, you can:

1. Access PowerDNS Admin at `http://localhost:8080`
2. Manage the database using phpMyAdmin at `http://localhost:8989`
3. Configure your DNS clients to use the PowerDNS server at the host's IP address

## Security Notes

- Remember to change default passwords in a production environment.
- The API key and other sensitive information should be stored securely, not in the Docker Compose file.

## Troubleshooting

If you encounter any issues:

1. Check the logs of the individual services:
   ```
   docker compose logs [service_name]
   ```
2. Ensure all services are running:
   ```
   docker compose ps
   ```
3. Verify network connectivity between containers.

