# Dylan Gallagher

**Concurrent systems — Java backends, Rust/C++ robotics, video and edge.** Dublin.

In structured environments the hardware is catalog. The cost moved to software —
perception, planning, control, fleets. I'm proving that software first, in public,
without a robot.

## Backend

| Repo | Focus | What you can check |
|---|---|---|
| [Boundaryd](https://github.com/Dylan-Gallagher/boundaryd) | Rust policy gateway | Offline-capable decide API with PostGIS geofences, hash-chained audit, transactional outbox; **2.53M evals/s** in-process; cached HTTP **15.3k rps** / p50 **0.99 ms** on a Ryzen 5 3600 |
| [Staylock](https://github.com/Dylan-Gallagher/staylock) | Java 21 inventory | Hotel reservation ledger with a last-room oracle: **200 concurrent guests → 1 hold / 199 sold out / 0 remaining**, asserted in CI; explainable ranking; hold-then-confirm API and public demo UI |

![UR5e pick-and-place in MuJoCo](https://github.com/Dylan-Gallagher/arm-lab/raw/main/docs/demo3.gif)

## Video and edge systems

| Repo | Focus | What you can check |
|---|---|---|
| [FieldCast](https://github.com/Dylan-Gallagher/fieldcast) | Rust + GStreamer | Real-time two-camera composition and H.264/MP4 output; custom zero-copy continuity element, structured timestamp diagnostics, clean-EOS drain, real media smoke test in CI |
| [FrameForge VK](https://github.com/Dylan-Gallagher/frameforge-vk) | C++20 + Vulkan compute | Chained grayscale/Sobel shaders with explicit barriers and timestamp queries; **1.67 ms** at 1080p on RX 5600 XT vs **3.76 ms** CPU (**2.25x**), max error below **3e-7** |
| [TrailVision](https://github.com/Dylan-Gallagher/trailvision) | Multimodal sports video | Auditable voice/IMU/vision event fusion, SQLite replay, FastAPI, and responsive review UI; deterministic demo fuses **17 candidates → 6 events → 3 runs** |

## Robotics stack

| Repo | Layer | What you can check |
|---|---|---|
| [arm-lab](https://github.com/Dylan-Gallagher/arm-lab) | Manipulation | Rust UR5e stack; [predeclared 300-query simulation study](https://github.com/Dylan-Gallagher/arm-lab/blob/v0.3.0/docs/randomized_eval_results.md): RRT-Connect **46.0%** vs **27.7%** direct, velocity-FF **90/138** full passes; [independent IK comparison](https://github.com/Dylan-Gallagher/arm-lab/blob/4e36ab5940a0d9a3552544135c273a6a7e8e5d07/docs/ik_baseline_results.md): arm-lab **978/1,000** vs `k` **718/1,000** with the same eight restart starts |
| [synthscan](https://github.com/Dylan-Gallagher/synthscan) | Perception | Synthetic depth cameras and a point-cloud toolkit in Rust — no PCL |
| [girder](https://github.com/Dylan-Gallagher/girder) | Middleware | ROS-free typed pub/sub: **420 ns** p50 in-process, bit-exact `.gdr` replay in CI |
| [rust-robotics-toolbox](https://github.com/Dylan-Gallagher/rust-robotics-toolbox) | Foundations | MuJoCo, Bevy, ONNX Runtime, Burn on Vulkan — smoke-tested on AMD |
| [robotarium-weighted-coverage](https://github.com/Dylan-Gallagher/robotarium-weighted-coverage) | Multi-robot | Fixed-seed eight-robot density-weighted coverage with barrier certificates |
| [earth-rover-urban-pilot](https://github.com/Dylan-Gallagher/earth-rover-urban-pilot/releases/tag/v0.1.0) | Rover readiness | SDK-shaped controller; [100-seed fault matrix](https://github.com/Dylan-Gallagher/earth-rover-urban-pilot/blob/v0.1.0/evidence/REPORT.md) cuts commanded outage motion **63.0%**; [5,408-frame real-rover-footage replay](https://github.com/Dylan-Gallagher/earth-rover-urban-pilot/blob/v0.1.0/evidence/VISION_REPORT.md) exercises gross camera-health faults; **no hardware run** |

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
