# Install Docker on Windows

## Step 1: Open up powershell as Administrator

 * Click Start and type “powershell“
 * Right-click Windows Powershell and choose “Run as Administrator“

## Step 2: Install Chocolatey

 * Paste the following command into Powershell and press enter.


```console
Set-ExecutionPolicy Bypass -Scope Process -Force; `
  iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
 * Answer Yes when prompted
 * Close Powershell


## Step 3: Open a new Powrshell as Administrator

 * Click Start and type “powershell“
 * Right-click Windows Powershell and choose “Run as Administrator“


## Step 4: Install Chocolatey

 * Paste the following command into Powershell and press enter.

```console

choco search docker-desktop
choco install docker-desktop

```

 * Close Powershell

## Step 5: Run Hello world container

Open a Windows Command Prompt (NOT As administrator)

Run the following hello world container

```bash
docker run hello-world
```

```console
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
9bb5a5d4561a: Pull complete
Digest: sha256:f5233545e43561214ca4891fd1157e1c3c563316ed8e237750d59bde73361e77
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
```

Seems to be going ok.  Let's see what images that got.

```bash
docker images
```

```console
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hello-world         latest              e38bc07ac18e        5 weeks ago         1.85kB
```

Looks like things are working!
