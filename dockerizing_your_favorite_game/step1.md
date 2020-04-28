First of all, we will need experimental features of Docker to complete this tutorial. Since Docker uses the kernel of the host operating system rather than emulating a virtual machine, programs exclusive to any given operating system may need their own unique Docker-containers. Ideally, users wouldn't need to actively differentiate between many different OS-specific containers upon running the contained program. Conveniently, Docker is now experimenting with a new manifest-feature that will fetch the correct container for the platform at hand. 

Run the following command to enable experimental feature:

`export DOCKER_CLI_EXPERIMENTAL=enabled`{{execute}}
