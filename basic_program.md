
---
# ROS 2 Jazzy Example

After installing `ros-jazzy-desktop`, you can try out some basic examples to verify that your installation is working correctly. These examples demonstrate the communication between a C++ talker node and a Python listener node.

## Running the Examples

### 1. C++ Talker

1. **Open a terminal**.
2. Source the ROS 2 setup file:

   ```bash
   source /opt/ros/jazzy/setup.bash
   ```

3. Run the C++ talker node:

   ```bash
   ros2 run demo_nodes_cpp talker
   ```

### 2. Python Listener

1. **Open another terminal**.
2. Source the ROS 2 setup file:

   ```bash
   source /opt/ros/jazzy/setup.bash
   ```

3. Run the Python listener node:

   ```bash
   ros2 run demo_nodes_py listener
   ```

## Expected Output

- In the terminal running the **C++ talker**, you should see output indicating that it is publishing messages, such as:

  ```
  Publishing: 'Hello, world! [n]'
  ```

- In the terminal running the **Python listener**, you should see output indicating that it has received those messages, such as:

  ```
  I heard: 'Hello, world! [n]'
  ```

Where `[n]` is a number that increments with each message published.

## Conclusion

This simple example verifies that both the C++ and Python APIs in ROS 2 Jazzy are functioning correctly. You can now explore more complex examples and start building your own robotic applications!

---
