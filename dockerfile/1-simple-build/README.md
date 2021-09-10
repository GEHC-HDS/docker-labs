<link rel='stylesheet' href='../../assets/css/main.css'/>

# Lab : Build a Simple Docker Image

## Step-1: Inspect the Dockerfile

[Dockerfile is here](Dockerfile)

## Step-2: Build

```bash
$   time docker build . -t my-ubuntu
```

## Step-3: Run the newly created image

```bash
$   docker run -it  my-ubuntu
```

This will drop you into / directory

Examine file `README.md`

```bash
# inside the container
$   cat  README.md
```

## Step-4: Install more packages

We are going to install `atop` package

- Edit the [Dockerfile](Dockerfile)

- Around line number 15, add another packge `atop`, so the final line looks like this

```text
RUN apt install -y \
        atop \
        iputils-ping \
        tree
```

- Build again

```bash
$   time docker build . -t my-ubuntu
```

**ACTION: Note which steps are cached and which steps are executed**

## Step-5: Run the newly built container

```bash
$   docker run -it  my-ubuntu

# run atop
$   atop
```

Exit by typing `exit` or `Ctrl+d`

## Step-6: Install another package

- Edit [Dockerfile](Dockerfile)

- In the last step, we modified an existing RUN command

- Here we will try to add a new RUN command, like this

```text
RUN apt install -y less
```

- Save the file and build again

- Observe the behaviour
