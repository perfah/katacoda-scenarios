You have now achieved support for one or more platforms with the versatile and easily extendible docker container created. To add more platforms you simply repeat step 4 to 6 (assuming you are on the right platform to build the os-specific image). You may now run the game with the following platform-independent command:

```docker run -it localhost:5000/<GAME>:latest```

**Example** `docker run -it localhost:5000/tetris:latest`{{execute}}


