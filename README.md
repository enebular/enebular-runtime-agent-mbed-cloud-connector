# Enebular Runtime Agent - Mbed Proxy

This is an Mbed Cloud client that works together with the main enebular runtime agent to provide enebular agent support for Mbed Cloud on Linux.

This client application acts as a proxy to the main enebular runtime agent by connecting to Mbed cloud and passing on data received through Mbed Cloud resource updates to the main enebular agent via a Unix socket.

This implementation is built directly on top of the Mbed Cloud client example project. More information on that is available [here](https://cloud.mbed.com/docs/v1.2/connecting/tutorial-connecting.html).

## Building

This is an Mbed project, so general knowledge of how Mbed projects are constructed and built is useful here.

The steps to prepare to build this project are as follows.

1. Install the `mbed` command-line tool.
1. Get a copy of the project by cloning it with git or by using the mbed command.
1. Move into the project directory (make it your current directory).
1. If you retrieved the project by cloning it with git, you'll need to then use the mbed command to add in the referenced libraries, with the `mbed deploy` command.

The project is now ready for you to set your Mbed cloud connection credentials and then build it. These two tasks can be done by following the Mbed Cloud client example Linux build instructions [here](https://cloud.mbed.com/docs/v1.2/connecting/tutorial-connect-linux.html).

Once built, you should end up with an executable binary called `mbedCloudClientExample.elf`.

## Running

As this application communicates with the main enebular runtime agent, that application must be started first. More specifically, you must run the **'local'** port of the enebular runtime agent. For information on how to configure and run the agent, refer to its project readme.

Once the the main agent application is running you can just run the `mbedCloudClientExample.elf` executable. Once it has connected to Mbed Cloud, it is available for use as an agent with enebular.
