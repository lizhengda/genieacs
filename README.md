# GenieACS

GenieACS is a fast and lightweight TR-069 auto configuration server (ACS). This
is the core back end component. A GUI front end is available at
https://github.com/zaidka/genieacs-gui.

## Features

- **Battle-tested at scale**: Can scale to manage hundreds of thousands and
potentially millions of devices
- **Powerful provisioning system**: Scriptable configuration to handle complex
device provisioning scenarios and other automated operations such as firmware
upgrade
- **Extensive API**: A rich HTTP-based API allows easy integration with other
systems

## Quick Start

Install [Node.js](http://nodejs.org/), [Redis](http://redis.io/), and
[MongoDB](http://www.mongodb.org/). Refer to the corresponding documentation for
installation guides. Supported versions are:

- Node.js: 6.x and 7.x (7.x recommended)
- Redis: 2.4 through 3.2
- MongoDB: 2.6 through 3.4

Then install GenieACS using NPM:

    npm install -g genieacs

Alternatively, you can install from source by cloning the git repository:

    git clone https://github.com/zaidka/genieacs.git
    cd genieacs
    git checkout $(git tag -l v1.1.* --sort=-v:refname | head -n 1)
    npm install
    npm run compile

Finally, run the following (from bin directory if installing from source):

    genieacs-cwmp

This is the service that the CPEs will communicate with. It listens to port 7547
by default (see config/config.json). Configure the ACS URL of your devices
accordingly.

    genieacs-nbi

This is the northbound interface module. It exposes a REST API on port 7557 by
default. This must be running for the GUI front end to work.

    genieacs-fs

This is the file server from which the CPEs will download firmware images and
such.

Note: For production deployment make sure to run those as background services.

For further details about installation and configuration, refer to the
[wiki section](https://github.com/zaidka/genieacs/wiki).

## Support

The [Users mailing list](http://lists.genieacs.com) is a good place to get
guidance and help from the community. Head on over and join the conversation!
In addition, the [wiki](https://github.com/zaidka/genieacs/wiki) provides useful
documentation and tips from GenieACS users.

For commercial support options and professional services, please visit
[genieacs.com](https://genieacs.com).

## License

Copyright 2013-2017 Zaid Abdulla. GenieACS is released under the
[AGPLv3 license terms](https://raw.githubusercontent.com/zaidka/genieacs/master/LICENSE).
