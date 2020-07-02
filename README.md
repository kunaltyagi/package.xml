## package.xml

### What is it
Each `<package-name>.xml` file can be symlinked to one of the following:
* The directory containing `CMakeLists.txt`
* The directory containting `setup.py` for pure Python projects

This allows catkin (and possibly ament and colcon) to build them.

### Why is it
While working on multiple projects, a need to have separate dependencies might arise.
A simple scenario would be project C using Gazebo 9 and project D using Gazebo 11.

catkin workspaces enable separating out the dependencies much like virtualenv does for
Python. We can utilize that to have different versions built in separate workspaces
and make out lives much easier.

### Where can I use it
This can't be used with `catkin_build`, and needs command `catkin` from python package
`catkin-tools`. The difference between the two isn't major, with the latter being a
much needed improvement over the former.

### How to use it
Simply clone a dependency in the `src` folder (or any other convenient place) of the
workspace. Then symlink (or copy) the relevant xml file and name it as `package.xml`.

Sit back and watch the build succeed. `catkin` also allows you to pass extra CMake
arguments to further customize your build (if needed).
