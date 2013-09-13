# mkvhost for Ubuntu

Create a new virtualhost on your Ubuntu system.

Uses a simple default template to get a virtualhost up and running. The template to use is configurable to allow your own way of working.

## Note About File Location

This script defaults the location of any virtualhost file paths to `/data/sites/*`. This is a personal preference to allow an easily accessible location to store sites on the server. This is done to also allow easy mounting of a filestore into the server to hold the sites.

If this isn't to your tastes, you can override it with the `-s` or `--sites` option below, or modify the script.

## Installation

Clone the repo to a suitable location on your server like `/opt/mkvhost`

    git clone git://github.com/designermonkey/mkvhost-ubuntu.git /opt/mkvhost

Run the `install` script to create the correct links on your filesystem. This will make sure the script is callable from your command prompt without having to specify the path.

    /opt/mkvhost/install

## Usage

Once installed, usage couldn't be simpler.

    mkvhost [<options>] <vhostname>

## Options
- `-h`, `--help` - Shows this help screen.
- `-u`, `--user` - Configure the username to give ownership of the virtualhost.
- `-g`, `--group` - Configure the group to give ownership of the virtualhost.
- `-V`, `--vhosts` - Configure the location of your virtualhost configuration files.
- `-s`, `--sites` - Configure the location of your folder to contain the virtualhost http root.
- `-i`, `-ipv4` - Change the local IP address.
- `-l`, `--loopback` - Add a record in the hosts file to loopback on this machine.
- `-vv`, `--verbose` - Output messages during processing.
- `-v`, `--version` - Shows the version number for this script.
- `-t`, `--template` - Specify a template file to use for the virtualhost


## Template
A custom template can be specified to use instead of the bundled simple template. There are specific values that are needed in the template to be replaced with values from the script.

- `VHOSTNAME` Wherever you want the supplied virtualhost name to be placed inside the template.
- `USERNAME` Wherever you want the supplied or default user name to be placed inside the template.
- `SITES` Wherever you want the supplied or default sites path to be placed inside the template.

## Vhostname
The name for a virtualhost can be anything you want in a normal url format

- `www.example.com`
- `local.example.com`

When setting a name that has no global DNS record, you will need to specify the `-l`, `--loopback` option to ensure your machine finds the host locally.

## License

The MIT License (MIT)

Copyright (c) 2013 John Porter

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
