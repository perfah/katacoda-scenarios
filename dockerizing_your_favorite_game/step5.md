1. Build an image from the dockerfile. The ```docker image build``` command builds a new docker image. The ```-t``` flag gives the image a tag which will play a part when referencing the image with ```<repo>:<tag>``` later (in the example below the repository would be ```localhost:5000/tetris-<ARCHITECTURE>-<OS>``` and the tag would be ```v1```. 
   
   ```docker image build -t localhost:5000/<GAME>-<ARCHITECTURE>-<OS>:v1 -f <dockerfile name> <working directory>```
   
   **Example:** `docker image build -t localhost:5000/tetris-amd64-linux:v1 -f dockerfile_linux .`{{execute}}

2. Run to verify that an image has been created (will list all local images):
   
   `docker images`{{execute}}

3. Push the local image to our registry:
   
   ```docker push localhost:5000/tetris-<ARCHITECTURE>-<OS>:v1```

   **Example:** `docker push localhost:5000/tetris-amd64-linux:v1`{{execute}}


