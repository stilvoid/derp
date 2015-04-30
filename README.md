# Derp

> "Docker made Easy for Real People"

Derp is a command line helper tool for Docker to take away some of the muscle strain of typing out the some old docker command invocations again and again during the develop-test-build cycle.

## Usage

    derp <command> [options...]

### Commands

* `alias <alias> [<arguments>] <image>`

    Set default arguments for a given image.
    The arguments are the same as those given to `docker run`.
    Any `--name` argument will be overriden by the provided alias.

* `up <alias>`

    Start a docker container as per configuration
    previously given to the alias command.

* `down <alias>`

    Stop the container named `<alias>`.

* `status`

    Lists all containers along with some information.

* `graph [<container>]`

    Draw a graph of all containers showing links between them.

* `info [<container>]`

    Display details information about all containers.
