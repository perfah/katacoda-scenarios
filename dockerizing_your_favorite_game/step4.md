A "dockerfile" contains all the information that Docker needs to create an image. Dockerfiles are responsible for installing all necessary dependencies as well as contain the information about what the image is supposed to do. FROM specifies a base container that is used for the image. ADD copies files from the host operating system to the container. RUN executes a command within the container (which we here use to fix permissions with ```chmod``` and add dependencies with ```apt-get update && ...``` in the example). CMD specifies which command to run in the container upon starting the container.

Create a dockerfile ```dockerfile_<OS>``` with the following content: 

``` 
FROM <BASE_CONTAINER>
ADD <GAME_BINARY> /
RUN chmod +x /<GAME_BINARY>
RUN <COMMAND FOR INSTALLING DEPENDENCIES>
CMD /<GAME_BINARY>
```

**Example**:

```
cat << EOF > dockerfile_linux
FROM ubuntu
ADD tetris /
RUN chmod +x /tetris
RUN apt-get update && apt-get -y install libncurses5-dev libncursesw5-dev
CMD /tetris
EOF
```{{execute}}


