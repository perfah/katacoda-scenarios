In this tutorial we don’t actually want to publish anything online. Therefore we will create our own testing registry by typing:

`docker run -d -p 5000:5000 --restart=always --name registry registry:2`{{execute}}

**Explanation of flags:**

- ```-d``` - detached mode
- ```p``` - publishes exposed port 5000 for the host and container (format: "hostport:containerport")
- ```--restart=always``` - restart policy when container exists
- ```--name``` - assign a name to the container/registry
 
