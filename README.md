
---

````markdown
# 🐢 Turtlesim PD Controller with ROS 2

This project demonstrates a **PD (Proportional-Derivative) controller** in a ROS 2 environment using `turtlesim`. A second turtle is spawned at a specified location and follows the first turtle in real-time using a smooth PD-controlled velocity system.

---

## 🧠 Features

- Spawns a second turtle (`turtle2`) using the `/spawn` service.
- Implements a **PD controller** to make `turtle2` follow `turtle1`.
- Uses ROS 2 nodes and services.
- Real-time velocity publishing with feedback from pose topics.

---

## 📦 Dependencies

- ROS 2 (Humble, Foxy, or newer)
- Python 3
- `turtlesim` package

---

## 🛠 Installation

1. **Source your ROS 2 environment**:
   ```bash
   source /opt/ros/humble/setup.bash  # replace 'humble' with your version
````

2. **Clone the repository into your ROS 2 workspace**:

   ```bash
   cd ~/ros2_ws/src
   git clone https://github.com/your-username/turtlesim_pd_controller.git
   ```

3. **Build the workspace**:

   ```bash
   cd ~/ros2_ws
   colcon build
   source install/setup.bash
   ```

---

## 🚀 Running the Project

### 1. Launch `turtlesim_node`

```bash
ros2 run turtlesim turtlesim_node
```

### 2. Run the PD controller node

```bash
ros2 run turtlesim_pd_controller pd_controller
```

The second turtle (`turtle2`) will be spawned and will begin following the original turtle (`turtle1`).

---

## 📁 Project Structure

```
turtlesim_pd_controller/
├── src/
│   └── pd_controller.py        # Main PD controller + spawner node
├── package.xml
├── setup.py
└── README.md
```

---

## 🧮 PD Control Logic

The PD controller computes:

* **Linear velocity**:

  $$
  v = K_p \cdot e_{dist} + K_d \cdot \frac{de_{dist}}{dt}
  $$
* **Angular velocity**:
$$
\omega = K_p \cdot e_{angle} + K_d \cdot \frac{de_{angle}}{dt}
$$
 
​


Where:

* $e_{dist}$ is the distance error between `turtle1` and `turtle2`.
* $e_{angle}$ is the angular difference between turtle heading and target direction.

---

## 🛑 To-Do / Enhancements

* Add GUI or CLI to select turtle spawn location.
* Dynamic goal selection via mouse click or terminal input.
* Extend to PID controller (add Integral term).

---

## 🧑‍💻 Author

Niyas 
[GitHub](https://github.com/niyassaleem)

