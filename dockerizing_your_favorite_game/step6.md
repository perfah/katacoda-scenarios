A 'manifest list' is a chain of (usually multiple) Docker image layers, that all may be linked to their own dockerfiles, as well as specify information such as the intended architecture and operating system. Practically, this means that we will have a list of platforms supported when running the final container. In the sense of execution, you can namely handle a manifest in the same way you handle any single docker container. One can therefore make a strong case for manifest lists in the context of cross-platform container distribution.

1. The ```docker manifest create``` command is used to create or amend manifest. 

   - If this is the first platform you are adding, start with a new manifest list referencing only your first image:

      ```docker manifest create --insecure localhost:5000/<GAME>:latest localhost:5000/<GAME>-<architecture>-<OS>:<tag>```

      **Example:** `docker manifest create --insecure localhost:5000/tetris:latest localhost:5000/tetris-amd64-linux:v1`{{execute}}

   - Otherwise if you already have a manifest list, you can add support for another platform by adding the next image:

      ```docker manifest create --insecure localhost:5000/<GAME>:latest -a localhost:5000/<GAME>-<the other architecture>-<the other OS>:<tag>```

2. Assign an architecture and operating system to the image (now contained in the manifest list):
   
   ```docker manifest annotate localhost:5000/<GAME>:latest localhost:5000/<GAME>-<ARCHITECTURE>-<OS>:<tag> --arch <ARCHITECTURE> --os <OS>```

   **Example:** `docker manifest annotate localhost:5000/tetris:latest localhost:5000/tetris-amd64-linux:v1 --arch amd64 --os linux`{{execute}}

3. Inspect the newly created manifest list (you should see manifests corresponding to the platforms you have added):

   ```docker manifest inspect localhost:5000/<GAME>:latest```
   
   **Example:** `docker manifest inspect localhost:5000/tetris:latest`{{execute}}

4. Push to our registry:

   ```docker manifest push localhost:5000/<GAME>:latest```

   **Example:** `docker manifest push localhost:5000/tetris:latest`{{execute}}

5. Then press continue.
