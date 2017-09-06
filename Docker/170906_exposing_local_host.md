### recently I had to create a docker image for a colleague because he was having difficulties installing a project and all of its dependencies on his local machine (Mac OSX)

`https://hub.docker.com/r/jochoi0707/waggle_backoffice/`

```shell
# pull my docker image from docker hub
docker pull jochoi0707/waggle_backoffice
# see all locally available docker images
docker images
# spin up a new docker container based on the waggle backoffice image
docker run -itd -p 8100:8100 INSERT_IMAGE_ID_HERE /bin/bash
# see all locally available containers and pick the most recent one
docker ps -a
# attach to that container and have fun! (may need to press a key to see the command line)
docker attach INSERT_CONTAINER_ID_HERE
# navigate to the waggle_backoffice ionic project
cd ionic/waggle_backoffice
# start ionic server with the following command
ionic serve --nobrowser
# visit localhost:8100 to see the backoffice in action
```
