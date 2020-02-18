# Creating my First Cotainer

This project was my first experience with docker, whereby I created a dockerfile which would create a virtual environment that has nginx and python installed.

## Notes

### Commands
- docker pull
- docker build
- docker run

- docker ps
- docker images

- docker stop
- docker start

- docker rm
- docker rmi

### docker build .
flags:
- `-t` or `--tag` to name the image

### docker run <image_name>
- use colon like so `<image_name>:` to specify version of image (this is called a tag)

flags:
- `-it` for interactive terminal
- `-p num1:num2` for port mapping (eg -p 80:3000 where num1 is for local host and num2 is from container)
- `-v /path/to/dir/on_host:/path/in_the_container` for volume mapping (like syncing files)
- `--name` to name the container
- `-d` detach to run in the background
- `attach`

### docker instructions for Dockerfile

- `RUN` The RUN instruction will execute any commands in a new layer on top of the current image and commit the results. The resulting committed image will be used for the next step in the Dockerfile .
- `FROM` creates a layer from an already made Docker image
- `WORKDIR` The WORKDIR instruction sets the working directory for any RUN , CMD , ENTRYPOINT , COPY and ADD instructions that follow it in the Dockerfile. If the WORKDIR doesn't exist, it will be created even if it's not used in any subsequent Dockerfile instruction.
- `EXPOSE` The EXPOSE instruction informs Docker that the container listens on the specified network ports at runtime.
- `CMD` specifies what command to run within the container.
  - instruction allows you to set a default command, which will be executed only when you run container without specifying a command. If Docker container runs with a command, the default command will be ignored. If Dockerfile has more than one CMD instruction, all but last CMD instructions are ignored.
- `COPY <src> <dest>` The COPY instruction will copy new files from <src> and add them to the container's filesystem at path <dest>
- `ADD <src> <dest>` The ADD instruction will copy new files from <src> and add them to the container's filesystem at path <dest>.
  - the major difference is that ADD can do more than COPY:
  - eg ADD allows <src> to be a URL
