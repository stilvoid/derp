# Derp

> "Docker made Easy for Real People"

Derp is a command line helper tool for Docker to take away some of the muscle strain of typing out the some old docker command invocations again and again during the develop-test-build cycle.

## Usage

    derp <command> [options...]

### Commands

* `alias <alias>[<run arguments>] <image> [-- <command>]`

    Set default arguments for a given image.
    The arguments are the same as those given to `docker run`.
    Any `--name` argument will be overriden by the provided alias.

    Examples:

        derp alias db:mysql -d -e MYSQL_ROOT_PASSWORD=root
        derp alias shell:ubuntu -ti -- /bin/bash

* `up [<run arguments>] <alias> [-- <command>]`

    Start a docker container as per configuration
    previously given to the alias command.
    If there is a stopped container named `<alias>`,
    derp will attempt to start it.

    Any run arguments will be *appended* to any set on the alias.
    If a command is provided, it will *replace* any set on the alias.

    Examples:

        derp up db
        derp up -d shell -- tail -f /var/log/dmesg

* `down <alias>`

    Stop the container named `<alias>`.

* `status`

    Lists all containers along with some information.

* `graph [<container>]`

    Draw a graph of all containers showing links between them.

* `info [<container>]`

    Display details information about all containers.
