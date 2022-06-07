# gickup

A docker-compose file for my gickup environment.

## Usage 

### Starting

```bash
cd ~/gickup          # change to the gitea_docker-compose directory
docker-compose pull  # pulls the latest images
```

Copy `example-conf.yml` to `conf.yml` and edit as needed.  Start the container as shown below, this will run once then exit.

```bash
docker-compose up  # starts container
```

Once it is confirmed that the container is running and syncing data as required then it is possible to modify the `docker-compose.yml` to always restart the container if it stops, and the `conf.yml` to run gick on a schedule.

To do this uncomment the `cron: 40 03 * * *` line in the `conf.yml` file to schedule gickup to run at 03:40 every day.  Also edit the `docker-compose.yml` file and uncomment the `restart: always` line.

You can then restart the container in detached mode.

```bash
docker-compose up -d  # starts container in detached mode
```

### Stopping

```bash
cd ~/gickup          # change to the gitea_docker-compose directory
docker-compose down  # stops the container
```

### Updating

```bash
cd ~/gickup             # change to the gitea_docker-compose directory
docker-compose pull     # pulls the latest images
docker-compose up -d    # restarts the containers with the newer images
docker system prune -a  # deletes any unused images
```

### Uninstall

```bash
cd ~/gickup             # change to the gitea_docker-compose directory
docker-compose down -v  # stops the containers and deletes the data volumes
docker system prune -a  # deletes any unused container images
```

## License

MIT

## Author Information

This project was created in 2022 by Graham Lillico.
