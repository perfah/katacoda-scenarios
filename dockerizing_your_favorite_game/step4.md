A "dockerfile" contains all the information that Docker needs to create an image. Dockerfiles are responsible for installing all necessary dependencies as well as contain the information about what the image is supposed to do. ```FROM``` specifies a base container that is used for the image. ```ADD``` copies files from the host operating system to the container. ```RUN``` executes a command within the container (which we here use to fix permissions with ```chmod``` and add dependencies with ```apt-get update && ...``` in the example). ```CMD``` specifies which command runs in the container upon start.

1. Create a dockerfile named ```dockerfile_<OS>``` with the following content (and replace the variables with ): 
   
   ``` 
   FROM <BASE_CONTAINER>
   ADD <GAME_BINARY> /
   RUN chmod +x /<GAME_BINARY>
   RUN <COMMAND FOR INSTALLING DEPENDENCIES>
   CMD /<GAME_BINARY>
   ```
   
   **Explanation of variable**:
   
   - ```<BASE_CONTAINER>``` refers to the name of a suitable Docker container/environment for the game (e.g. ```ubuntu``` if the platform is Linux). You can search for one at [Docker Hub](https://hub.docker.com/) and grab the image name.
   - ```<GAME_BINARY>``` refers the executable binary of the game (e.g. ```.exe``` on Windows)
   - ```<COMMAND FOR INSTALLING DEPENDENCIES>``` used to install dependencies for the game if the base container does not already provide them. The decision of base container will also affect what command needs to be run here - due to differing package managers.  
   
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
   
2. Then press continue.

