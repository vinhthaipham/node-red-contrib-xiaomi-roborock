# NodeRED Xiaomi Roborock Node

This module provides an universal node to send commands to a Xioamo vacuum using the miIO module.
A full list of commands can be found here: [XiaomiRobotVacuumProtocol](https://github.com/marcelrv/XiaomiRobotVacuumProtocol)

## Installation

`npm install node-red-contrib-xiaomi-roborock`

## Usage

Create a new roborock node and provide connection parameters (hostname, token).
Command defaults to find_me and can be changed in node properties or by sending payload.command to this node.
Args are passed through.

### Example for zoned cleanup:
    {
    "command": "app_zoned_clean",
    "args": [
        [
            18000,
            20000,
            22000,
            25000,
            1
        ]
    ],
    "jobid": "105"
    }


## Implemented Nodes

 * miIO Node

## Known Issues

### Array cannot be passed via node properties ui editor

If a command needs an array or object to be passed as argument, this cannot be done via the node properties ui editor.
A JSON payload needs to be send to the node instead in order to work (see example for zoned cleanup above).

### Updating firmware requires restart of NodeRED

After a firmware update the following error occur: "Could not connect to device, token might be wrong".
Restarting NodeRED usually solves this issue.
Thanks to @readeral
