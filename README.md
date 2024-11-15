# Docker template for [Leconfe](https://leconfe.com)
This is a docker template for [Leconfe](https://leconfe.com) that allows you to run the application in a docker container easily.


## How to use

- Download this repository.
- Extract the downloaded file and navigate to the extracted folder.
- Run the following command to change the ownership of the `volumes` folder
```bash
sudo chown -R 82:82 volumes
```
- Run the following command to start the docker container
```bash
docker-compose up -d
```

By default configuration, the container will expose the application on port `8080` for http and `8443` for https. You can change the port by editing the `docker-compose.yml` file.

## FAQ
> Why do I need to change the ownership of the `volumes` folder?

To increase security we're using the `www-data` user and group that is built into the official PHP images. Because of that, the mounted `volumes` will need to match the ID of the `www-data` user and groups. For Alpine image that we use, this is `82:82`.