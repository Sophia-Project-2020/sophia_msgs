# sophia_msgs
*sophia_msgs* is the shared ROS package for custom messages, services and actions of the [project SOPHIA 2020](https://www.project-sophia.eu/). This package is meant to provide a common interface between packages developed by the partners of the consortium.

## Table of Contents
- [Download](#download)
- [Message Types](#message-types)
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

  ### msg
  - [example_1.msg](path_to_documentation)
  
  ### srv
  - [example_2.srv](path_to_documentation)
  
  ### action

## How to use the messages
If you are using the sophia_msgs in your package, remember to add to **package.xml**:
```
<depend>sophia_msgs<depend>
```
and in the **CMakeList.txt**:

```bash
find_package(catkin REQUIRED COMPONENTS
  other_catkin_pkgs
  sophia_msgs
)
```

```
add_dependencies(your_program ${catkin_EXPORTED_TARGETS})
```

- ### C++ 
If you are building C++ nodes which use your new messages, you will also need to declare a dependency between your node and your message, as described in If you are building C++ nodes which use your new messages, you will also need to declare a dependency between your node and your message, as described in the [catkin documentation](http://docs.ros.org/kinetic/api/catkin/html/howto/format2/cpp_msg_dependencies.html).

Messages are put into a namespace that matches the name of the package. ie. 
```
#include <sophia_msgs/name-of-the-message.h>
```

- ### Python
For Python just remember to add the dependencies at the top of your code

```
from sophia_msgs.msg import name-of-the-message
```
## Acknowledgment
This package has been developed under the [SOPHIA 2020 project](https://www.project-sophia.eu/).
