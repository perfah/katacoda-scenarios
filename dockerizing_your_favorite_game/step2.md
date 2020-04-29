1. In this tutorial we don’t actually want to publish anything online. Therefore we will create our own testing registry by typing:

   `docker run -d -p 5000:5000 --restart=always --name registry registry:2`{{execute}}

   **Explanation of flags:**

   - ```-d``` - detached/background mode (will allow us to continue working while the process is running)
   - ```-p 5000:5000``` - publishes exposed ports ```host:container``` respectively (will allow us the access the process later at port 5000)
   - ```--restart=always``` - a restart policy run when container exists (restart the process automatically if it goes down)
   - ```--name <name>``` - assign a name to the container/registry (we will call it ```registry```)
 
2. Then press continue.
