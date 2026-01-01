# ROS-commands

Here is an organized structure for your ROS 2 commands, categorized by workflow steps.

### Workspace Setup

creates the directory for your workspace.

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
```

### Package Creation

You can create Python or C++ packages in src.

```bash
ros2 pkg create --build-type ament_python bot_examples_py
ros2 pkg create --build-type ament_cmake bot_examples_cpp
```

### Building the Workspace

Always run `colcon build` from the root of your workspace (e.g., `~/ros2_ws`),
I personally use a custom bash command (rosbuild) to source my complie commands also for lsp.

```bash
colcon build
# or for just the package
colcon build --packages-select bot_examples_py

```

### Sourcing and Verification

After building, you must source the setup file to use the new packages.

```bash
. install/setup.bash
ros2 pkg list | grep bot_examples_py

```
