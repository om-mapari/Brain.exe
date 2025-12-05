# 🙇 Docker Commands Reference

## 🎯 Basic Commands

| Command                                              | Description                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| `docker build -t [tagName] .`                        | Building the Docker Image 📦 from Dockerfile               |
| `docker run [ImageName]`                             | Pulls the image (if not present) and runs the container    |
| `docker ps`                                          | Lists all running containers (process status)              |
| `docker stop [containerID/containerName]`            | Stops a running container                                  |
| `docker ps -a`                                       | Lists all containers, including stopped ones               |
| `docker rm [containerID/containerName]`              | Removes a container permanently                            |
| `docker images`                                      | Lists all downloaded images with size and Image ID         |
| `docker image inspect kodekloud/simple-webapp-mysql` | Shows detailed information about an image                  |
| `docker rmi [imageName/imageID]`                     | Removes an image (Note: Remove dependent containers first) |
| `docker pull [image:version]`                        | Pulls the specified image from Docker Hub                  |

## ⚡ Advanced Commands

| Command | Description |
|---------|-------------|
| `docker stop $(docker ps -a -q)` | Stops all containers |
| `docker rm $(docker ps -a -q)` | Removes all containers |
| `docker stop sd pr ms` | Stops multiple containers (e.g., sd, pr, and ms) |
| `docker rmi $(docker images -q)` | Removes all images |

## 🛠️ Accessing the Container Terminal

| Command | Description |
|---------|-------------|
| `docker run -it centos bash` | Launches a CentOS container and opens the Bash shell (-it stands for interactive mode) |
| `cat /etc/*release*` | Shows the OS version inside the container |

## 💡 Command Tips

- Use `-it` for interactive mode when you need to access the container's shell
- Use `-d` to run containers in detached mode (background)
- Use `-p` to map ports from container to host
- Use `-v` to mount volumes for persistent data
- Use `--name` to assign custom names to containers for easier management