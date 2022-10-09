# G6 CAN Messages
This repo contains a platform agnostic header file which outlines the data portion of CAN messages sent in the G6 Pod. This repository should be designed as a single header file. It should not contain
any hardware specific code for interacting with a canbus, only the formats for the messages. Inside the file, one should find a host of comments that explain the specialized macros used to define messages. Each message should be generated using the `CAN_MESSAGE` macro as it has a built in type check which will ensure that the message can fit on the can bus.

# Including this file in projects
## Git submodules
To ensure that changes to this file can be passed into downstream projects, it is best practice to add this repo as a git submodule to the project that is using it. To do this, go to that project and type in the terminal:

- `git submodule add git@github.com:waterloop/G6-CAN-Messages.git`

- `git submodule update`

## Adding to make file
After you added the repo as a submodule, add the path to the header file to the list of includes in the make file. Each project makefile should already have an ongoing list so adding this to it should be as easy as following the pattern laid out. If it's not, reach out to someone for help. You will likely be adding it with a `-I` flag to notify the compiler that it should be added to the include path.
