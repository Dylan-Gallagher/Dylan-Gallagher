# Dylan Gallagher

Robotics founder in Dublin, building lean, inspectable robot software from first
principles. My current work spans manipulation, robot middleware, synthetic
perception, and multi-robot exploration—with deterministic tests and raw
benchmark results alongside the demos.

## Selected robotics work

| Project | What it demonstrates | Evidence |
|---|---|---|
| [arm-lab](https://github.com/Dylan-Gallagher/arm-lab) | A serial-manipulator stack in Rust: model-consistent FK/Jacobians, damped least-squares IK, collision-aware RRT planning, trajectory generation, and MuJoCo control | [Multi-scene report](https://github.com/Dylan-Gallagher/arm-lab/blob/main/docs/multi_query_results.md) · Attached payload: [protocol](https://github.com/Dylan-Gallagher/arm-lab/blob/main/docs/attached_payload_protocol.md) / [results](https://github.com/Dylan-Gallagher/arm-lab/blob/main/docs/attached_payload_results.md) · [CI](https://github.com/Dylan-Gallagher/arm-lab/actions/workflows/ci.yml) · [Citation](https://github.com/Dylan-Gallagher/arm-lab/blob/main/CITATION.cff) |
| [robotarium-weighted-coverage](https://github.com/Dylan-Gallagher/robotarium-weighted-coverage) | Simulator-only, fixed-seed eight-robot density-weighted coverage using the official Robotarium transform and barrier-certificate API | [v0.1.0](https://github.com/Dylan-Gallagher/robotarium-weighted-coverage/releases/tag/v0.1.0) · [Frozen evidence](https://github.com/Dylan-Gallagher/robotarium-weighted-coverage/tree/main/evidence/simulator-3072698) · [CI](https://github.com/Dylan-Gallagher/robotarium-weighted-coverage/actions/workflows/ci.yml) |
| [girder](https://github.com/Dylan-Gallagher/girder) | Minimal ROS-free robotics runtime with typed pub/sub, deterministic simulation time, record/replay, shared memory, and TCP | [Source](https://github.com/Dylan-Gallagher/girder) · [CI](https://github.com/Dylan-Gallagher/girder/actions/workflows/ci.yml) |
| [synthscan](https://github.com/Dylan-Gallagher/synthscan) | Synthetic depth cameras and a point-cloud perception toolkit in Rust, without ROS or PCL | [Source](https://github.com/Dylan-Gallagher/synthscan) · [CI](https://github.com/Dylan-Gallagher/synthscan/actions/workflows/ci.yml) |

## Current challenge

I am developing a CPU-only policy for the [IROS 2026 Indoor Exploration
Competition](https://frostlab.byu.edu/IIG-workshop/competition/). On a released
single-robot map, the current policy reached **65.17% base-station coverage**
against **35.02%** for the shipped nearest-frontier baseline in matched local
runs. Cross-map and hidden-start robustness testing is in progress ahead of the
preliminary round.

## Engineering interests

Robot learning grounded by classical control · motion planning · robot
middleware · simulation and reproducibility · Rust for robotics · efficient
multi-agent autonomy
