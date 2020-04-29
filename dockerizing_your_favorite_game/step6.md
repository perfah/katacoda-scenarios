A manifest list is a chain of (usually multiple) docker image layers that may specify information such as available architecture and operating system support. In the sense of execution, you can handle a manifest in the same way you handle any single docker image. This makes manifest lists a strong candidate for cross-platform container distribution.

1. The ```docker manifest create``` command is used to create or amend manifest. 

   - If this is the first platform you are adding, start with a new manifest list referencing only your first image:

      ```docker manifest create --insecure localhost:5000/<GAME>:latest localhost:5000/<GAME>-<architecture>-<OS>:<tag>```

      **Example:** `docker manifest create --insecure localhost:5000/tetris:latest localhost:5000/tetris-amd64-linux:v1`{{execute}}

   - Otherwise if you already have a manifest list, you can add support for another platform by adding the next image:

      ```docker manifest create --insecure localhost:5000/<GAME>:latest -a localhost:5000/<GAME>-<the other architecture>-<the other OS>:<tag>```

2. Assign an architecture and operating system to the image (now contained in the manifest list):
   
   ```docker manifest annotate localhost:5000/<GAME>:latest localhost:5000/<GAME>-<ARCHITECTURE>-<OS>:<tag> --arch <ARCHITECTURE> --os <OS>```

   **Example:** `docker manifest annotate localhost:5000/tetris:latest localhost:5000/tetris-amd64-linux:v1 --arch amd64 --os linux`{{execute}}

3. Push to repo:

   ```docker manifest push localhost:5000/<GAME>:latest```

   **Example:** `docker manifest push localhost:5000/tetris:latest`{{execute}}

4. Inspect the newly created manifest list:

   ```docker manifest inspect localhost:5000/<GAME>:latest```
   
   **Example:** `docker manifest inspect localhost:5000/tetris:latest`{{execute}}

5. Then press continue.
