filefrog/linode
===============

This image provides the Linode CLI in Docker form.

[See it on Docker Hub!][1]

Running it on Docker
--------------------

To run this in your local Docker daemon:

    docker run --rm -it filefrog/linode --help

This is meant to _replace_ a local binary, so you can either alias
it, or put it in a shell script:

    #!/bin/sh
    exec docker run --rm -it filefrog/linode "$@"

(The `linode` script in the root of this code repository is
 intended for that exact purpose.)


Building (and Publishing) to Docker Hub
---------------------------------------

The Makefile handles building pushing.  For jhunt's:

    make push

Is all that's needed for release.  If you want to build it
locally, you can instead use:

    make build

If you want to tag it to your own Dockerhub username:

    IMAGE=you-at-dockerhub/linode make build push

By default, the image is tagged `latest`.  You can supply your own
tag via the `TAG` environment variable:

   IMAGE=... TAG=$(date +%Y%m%d%H%M%S) make build push

Happy Hacking!


[1]: https://hub.docker.com/r/filefrog/linode
