**Introduction**

"Dockerizing your Favorite Game" is a tutorial presenting a general approach to placing a game within a self-contained environment playable on multiple platforms. Aspects of both cross-platform distribution as well as dependency management will hence be presented. We will show you how to create a versatile "Docker container" that theoretically can run on a wide array of systems. Note that the focus is on the general approach to such, rather than to actually create a katacoda-session supporting multiple platforms. However, by following the examples you will ultimately be able to play a game of Tetris at the end.

**Background**

"Docker" is a suite of "platform as a service" (PaaS) products that offer "containers" to work with. A finalized container is an isolated environment that is capable of delivering the experience it was created for without involving the user in unnecessary details (e.g. software setup, dependencies, configuration files and even the platform used). Yes, Docker in fact offers (some experimental) features that will allow you to abstract away from an impressive set of otherwise concerning factors.

**Prerequisites**

We will assume you already have the following:

- a recent version of Docker installed on your system
- access to a computer running each platform you want to be able to play the game on
- a game binary for each of those platforms

**Recommendations**

To be able to to get through the tutorial successfully you should note the following:

- a black box with a command inside means that you should run the command by clicking the box
- a black box with other text inside means that you should copy some of this text into a file by clicking the box
- you are expected to click continue only after executing every command of each step

**Limitations of this tutorial**

- The tutorial won't show examples on how to to add another platform (since that would make the katacoda environment insufficient - you can't build a Windows image on Linux 4.4)
- It could be harder to get the container to work on your platform of choice (if this is not Linux)
- The tutorial doesn't show you how to transfer the container and manifest files to another operating system / platform
