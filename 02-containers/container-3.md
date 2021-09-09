<link rel='stylesheet' href='../assets/css/main.css'/>

# Lab : Container 3

## Overview

Attach to running containers

## Runtime

10 mins

## Step-1: Start a long running container

In previous examples, our containers exited as soon as the task is done.  In this lab, let's run a container that will keep running

Run a container in background

```bash
$    docker run -d alpine /bin/sh -c "while true; do sleep 3; date; done"
```

Here `-d` flag puts the container in the background

## Step-2: Inspect the Running Containers

```bash
$   docker ps
```

## Step-3: See the output of background container

```bash
# replace container_id with the actual id
$   docker logs   CONTAINER_ID
```

To follow the logs

```bash
$   docker  logs  -f   CONTAINER_ID
```

## Step-4: Attach to a background container

```bash
$   docker container attach CONTAINER_ID
```
