# neo4j Docker Image by scorpion.io

Neo4j Docker image by [scorpion.io](https://scorpion.io). This docker image is used by invoking an asterism for various [constellation](https://constellations.sh/) projects.

## Download and Starting the App

You will first need to pull the scorpion image of neo4j, then you can use the command below to run the app.

### Download the docker layers

```bash
docker pull scorpion/neo4j
```

### Start the app

```bash
docker run \
    --publish=7474:7474 --publish=7687:7687 \
    --volume=$HOME/neo4j/data:/data \
    scorpion/neo4j
```

which allows you to access neo4j through your browser at <http://localhost:7474>.

This binds two ports (`7474` and `7687`) for HTTP and Bolt access to the Neo4j API. A volume is bound to /data to allow the database to be persisted outside the container.

## Default User

    Username: neo4j
    Password: neo4j

> You can, for development purposes, disable authentication by passing --env=NEO4J_AUTH=none to docker run.

## Building the image

```bash
docker build -t scorpion/neo4j:<tag> .
```

## Uploading to hub.docker.com

```bash
docker push scorpion/neo4j:<tag>
```
