# Docker Dialogs Toolkit
This project offers the opportunity to manage docker containers from a standard bash shell using text based dialogs.
The toolkit consists of two scripts:

 + `ddt` - Which manages docker containers using the dialog boxes
 + `ddk` - A small set of low level functions simplifying docker container management
 
Both scripts need to be sourced before their usage, preferably during the shell initialization phases (.bashrc or .profile)
Please pay attention that for a correct usage of the commands defined by the `ddt` script, the [Dialogs package](http://invisible-island.net/dialog/dialog.html) have to be installed in the hosting system. Please refer to your OS support for this package.
Some commands are also requesting the 'jq' utilty.

## `ddt`
This is the main component of the ToolKit which collects all functions that manage docker containers using Dialog Boxes.
Below the list of possible commands:

 + `ddt_sel` Select a docker container from the list of all available containers. This command can be used in conjunction with `dtk` defined functions
 + `ddt_con` Open a bash terminal against the selected docker container
 + `ddt_restart` Restart  a selected container
 + `ddt_stop` Stop the selected container
 + `ddt_start` Start the selected container
 + `ddt_start` Show logs of the selected container
 + `ddt_rm` Remove the selected container, (it asks for confirmation)
 + `ddt_net` Select one of the defined docker networks (`ddt_net*` commands are still under development)
 + `ddt_inspect` Inspect the selected container

## `dtk`
This script defines the core functions for `ddt` commands. These functions can be used directly by the user offering a very productive set of shortcuts for the most popular commands used during docker container managermaent.
All functions defined in `dtk` script are referring to the target docker container using the container id as parameter or inside the environment variable `$CNT`.\
Below the list of possible commands:

 + `dattach` Opens a bash terminal against the specified container
 + `dstart` Start the specified container
 + `dstop` Stop the specified container
 + `drm` Remove the specified container (Eventually it stops running containers)
 + `dlogs` Show container logs
 + `dps` Show the list of contaners
 + `dexe`  Execute a command on top of the specified container
 + `dkill` Stop and then remove the specified container
 + `dip` Show IP address of the selected container
 + `dinspect` Inspects the selected container

