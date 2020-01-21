# sophia_msgs
*sophia_msgs* is the shared ROS package for custom messages, services and actions of the [project SOPHIA 2020](https://www.project-sophia.eu/). This package is meant to provide a common interface between packages developed by the partners of the consortium.

## Table of Contents
- [Download](#download)
- [Message Types](#message-types)
    - [msg](#msg)
    - [srv](#srv)
    - [action](#action)
- [How to use the messages](#how-to-use-the-messages)
    - [C++](#c)
    - [Python](#python)
- [Acknowledgment](#acknowledgment)

## Download
Open terminal and navigate to **src** folder in your catkin workspace:

``` bash
Username@Hostname:~$ cd ~/your_catkin_ws/src
```
Clone the repository using:

``` bash
Username@Hostname:~$ git clone https://github.com/Sophia-Project-2020/sophia_msgs.git
```
Then compile
``` bash
Username@Hostname:~$ cd ~/catkin_ws 
Username@Hostname:~$ catkin_make
```

## Message Types
Document the new msgs, srvs and actions, by adding it in its own list:

  - ### msg
    - [example_1.msg](msg/example_1.msg)
  
  - ### srv
    - [example_2.srv](srv/example_2.srv)
  
  - ### action
    - [example_3.action](action/example_3.action)

## How to use the messages
If you are using the sophia_msgs in your package, remember to add to **package.xml**:
- if [format 2 of package.xml](http://wiki.ros.org/catkin/package.xml#Format_2_.28Recommended.29)
```
<depend>sophia_msgs</depend>
```
- otherwise
```
<build_depend>sophia_msgs</build_depend>
<exec_depend>sophia_msgs</exec_depend>
```
and in the **CMakeList.txt**:

```
find_package(catkin REQUIRED COMPONENTS
  other_catkin_pkgs
  sophia_msgs
)
```

```
add_dependencies(your_program ${catkin_EXPORTED_TARGETS})
```

- ### C++ 
If you are deploying ROS nodes in C++ which use sophia_msgs, you will need to declare a dependency between your node and your message, as described in the [catkin documentation](http://docs.ros.org/kinetic/api/catkin/html/howto/format2/cpp_msg_dependencies.html).

In your C++ node or library, add

```code
#include <sophia_msgs/name_of_the_message.h>
#e.g. #include <sophia_msgs/example_1.h>
```

- ### Python
For Python just remember to add the dependencies at the top of your code

```
from sophia_msgs.msg import name-of-the-message
```
## Acknowledgment
This package has been developed under the [SOPHIA 2020 project](https://www.project-sophia.eu/).

