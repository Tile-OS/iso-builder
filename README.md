## ISO Builder

This ISO builder is fork of the good work from the elementary crew.  Many thanks to the devs there https://github.com/elementary/os

## Building Locally

The following example uses Docker and assumes you have Docker correctly installed and set up:

Clone this project & cd into it:

    git clone https://github.com/Tile-OS/iso-builder && cd iso-builder

Configure the channel in the etc/terraform.conf (dev, stable).
Configue desktop in the /etc/terraform.conf (sway, river).

Run the build:

    docker run --privileged -i -v /proc:/proc \
        -v ${PWD}:/working_dir \
        -w /working_dir \
        debian:latest \
        /bin/bash -s etc/terraform.conf < build.sh

When done, your image will be in the builds folder.



## Further Information

More information about the concepts behind `live-build` and the technical decisions made to arrive at this set of tools to build an .iso can be found [on the wiki](https://github.com/elementary/os/wiki/Building-iso-Images).
