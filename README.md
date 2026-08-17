# Dylan Gallagher

**Construction robotics in Rust.** Simulation-first, no ROS. Dublin.

In structured environments the hardware is catalog. The cost moved to software —
perception, planning, control, fleets. I'm proving that software first, in public,
without a robot.

![UR5e pick-and-place in MuJoCo](https://github.com/Dylan-Gallagher/arm-lab/raw/main/docs/demo3.gif)

## Robotics stack

| Repo | Layer | What you can check |
|---|---|---|
| [arm-lab](https://github.com/Dylan-Gallagher/arm-lab) | Manipulation | UR5e from scratch; [predeclared 300-query simulation benchmark](https://github.com/Dylan-Gallagher/arm-lab/blob/main/docs/randomized_eval_results.md): RRT-Connect **46.0%** vs **27.7%** direct, velocity-FF **90/138** full passes |
| [synthscan](https://github.com/Dylan-Gallagher/synthscan) | Perception | Synthetic depth cameras and a point-cloud toolkit in Rust — no PCL |
| [girder](https://github.com/Dylan-Gallagher/girder) | Middleware | ROS-free typed pub/sub: **420 ns** p50 in-process, bit-exact `.gdr` replay in CI |
| [rust-robotics-toolbox](https://github.com/Dylan-Gallagher/rust-robotics-toolbox) | Foundations | MuJoCo, Bevy, ONNX Runtime, Burn on Vulkan — smoke-tested on AMD |
| [robotarium-weighted-coverage](https://github.com/Dylan-Gallagher/robotarium-weighted-coverage) | Multi-robot | Fixed-seed eight-robot density-weighted coverage with barrier certificates |

## Current challenge

[IROS 2026 Indoor Exploration Competition](https://frostlab.byu.edu/IIG-workshop/competition/) — CPU-only policy. On a released single-robot map: **65.17%** base-station coverage vs **35.02%** nearest-frontier baseline in matched local runs. Cross-map and hidden-start robustness testing is in progress.

CS, Trinity College Dublin.
