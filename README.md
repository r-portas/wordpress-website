# Wordpress Site

This repo contains the infrastructure required to build and deploy the wordpress server.

## Requirements
- [Docker](https://www.docker.com/get-started)

## Local Development

1. Install Docker
2. Clone down this repo
3. Run `docker-compose up`

The following ports are exposed when running:
- 8080: HTTP traffic to Wordpress
- 8443: HTTPS traffic to Wordpress

## Deployment

1. Create the server, on Vultr or DigitalOcean
2. Choose a Ubuntu image (they are easy to install Docker on)
3. Install Docker on the server [Tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04)
4. Clone down this repo
5. Change the passwords in the `.env` file
5. Run `docker-compose up -d` (The `-d` runs the stack in the background)
6. Setup Nginx to do the reverse proxy to the wordpress instance

## Maintenance Notes
- Stop the stack by running `docker-compose down`
- The MySQL data is stored in a docker volume named `wordpress_data`, don't delete the volume
    - To delete the volume, run `docker-compose down --volumes`