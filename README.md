# Dylan Gallagher

**Construction robotics in Rust.** Simulation-first, no ROS. Dublin.

In structured environments the hardware is catalog. The cost moved to software —
perception, planning, control, fleets. I'm proving that software first, in public,
without a robot.

![UR5e pick-and-place in MuJoCo](https://github.com/Dylan-Gallagher/arm-lab/raw/main/docs/demo3.gif)

## Robotics stack

| Repo | Layer | What you can check |
|---|---|---|
| [arm-lab v0.3.0](https://github.com/Dylan-Gallagher/arm-lab/releases/tag/v0.3.0) | Manipulation | UR5e from scratch; [corner-stop derivative audit](https://github.com/Dylan-Gallagher/arm-lab/blob/v0.3.0/docs/corner_stop_results.md): peak v/a/j **0.550/1.799/7.996** (rad/s, rad/s², rad/s³), within declared limits; [300-query benchmark](https://github.com/Dylan-Gallagher/arm-lab/blob/v0.3.0/docs/randomized_eval_results.md): RRT-Connect **46.0%** vs **27.7%** direct, velocity-FF **90/138** full passes |
| [synthscan](https://github.com/Dylan-Gallagher/synthscan) | Perception | Synthetic depth cameras and a point-cloud toolkit in Rust — no PCL |
| [girder](https://github.com/Dylan-Gallagher/girder) | Middleware | ROS-free typed pub/sub: **420 ns** p50 in-process, bit-exact `.gdr` replay in CI |
| [rust-robotics-toolbox](https://github.com/Dylan-Gallagher/rust-robotics-toolbox) | Foundations | MuJoCo, Bevy, ONNX Runtime, Burn on Vulkan — smoke-tested on AMD |
| [robotarium-weighted-coverage](https://github.com/Dylan-Gallagher/robotarium-weighted-coverage) | Multi-robot | Fixed-seed eight-robot density-weighted coverage with barrier certificates |

## Upstream robotics work

Accepted upstream:

| Project | Change | Verification |
|---|---|---|
| [ROS Controls #2567](https://github.com/ros-controls/ros2_controllers/pull/2567) | Adds closed-form bicycle, tricycle, and Ackermann integration tests | Maintainer-approved and merged; exact Rolling package passed 32/32 tests |

Selected patches currently under maintainer review:

| Project | Change | Verification |
|---|---|---|
| [Gazebo Sensors #640](https://github.com/gazebosim/gz-sensors/pull/640) | Bounds reused thermal and segmentation message headers instead of appending one entry per frame | Full local suite; Homebrew ARM64, Ubuntu, and Windows hosted builds green |
| [ros2-rust #669](https://github.com/ros2-rust/ros2_rust/pull/669) | Coalesces duplicate executor task wakes while preserving wake-during-poll | Nine hosted builds green across Humble, Jazzy, Kilted, and Rolling |
| [RViz #1837](https://github.com/ros2/rviz/pull/1837) | Surfaces incompatible QoS as a visible error and recovers after compatible traffic arrives | Fast DDS reproduction; exact core and downstream display checks pass locally |

## Current challenge

[IROS 2026 Indoor Exploration Competition](https://frostlab.byu.edu/IIG-workshop/competition/) — CPU-only policy. On a released single-robot map: **65.17%** base-station coverage vs **35.02%** nearest-frontier baseline in matched local runs. Cross-map and hidden-start robustness testing is in progress.

CS, Trinity College Dublin.
