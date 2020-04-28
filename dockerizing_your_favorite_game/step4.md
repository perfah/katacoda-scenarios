A "dockerfile" contains all the information that Docker needs to create an image. Dockerfiles are responsible for installing all necessary dependencies as well as contain the information about what the image is supposed to do. FROM specifies a base container that is used for the image. ADD copies files from the host operating system to the container. RUN executes a command within the container. CMD specifies which command to run in the container upon starting the container.

Create a dockerfile ``` dockerfile_<OS>``` with the following content: 

``` 
FROM <BASE_CONTAINER>
ADD <GAME_BINARY> /
RUN chmod +x /<GAME_BINARY>
CMD /<GAME_BINARY>
```

**Example**:

```
cat << EOF > dockerfile_linux
FROM ubuntu
ADD tetris /
RUN chmod +x /tetris
CMD /tetris
EOF
```{{execute}}


