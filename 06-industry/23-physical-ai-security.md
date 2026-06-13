# Bài 23: Physical AI Security — Autonomous Vehicles & IoT

## The Shift

> "As AI systems begin to act in the physical world, cyber failures become physical failures that can directly affect human safety." — WEF 2026

## Attack Vectors

### Text-Based Command Hijacking
- UC Santa Cruz research: Misleading text in physical environment **hijacks** embodied AI decisions
- Self-driving cars, autonomous robots, drones vulnerable
- **No software hacking needed** — just text in the environment

### Electromagnetic Signal Injection
- Distort images captured by cameras
- Lead to incorrect AI decisions
- Compromise safety of autonomous vehicles

### LiDAR Adversarial Attacks
- Physical adversarial objects fool 3D perception
- Object detection/classification misled
- Multiple real-world feasible attacks documented

## Autonomous Vehicle Threats

OWASP Agentic AI framework **not designed** for safety-critical cyber-physical platforms:
- Perception layer attacks
- Communication layer attacks
- Control layer attacks
- Cross-layer threats

## Physical Adversarial Examples

- Subtle stickers/patches fool image classifiers
- Work in real-world conditions (different angles, lighting)
- RL-based agents improve attack success by **13.2%**

## Key Insight

> "We are scaling autonomy and capability faster than scaling the safety foundations they rest on." — WEF

## References

- [WEF: Physical AI Cybersecurity](https://www.weforum.org/stories/2026/04/physical-ai-cybersecurity/)
- [UC Santa Cruz: Misleading Text Hijacks AI Robots](https://news.ucsc.edu/2026/01/misleading-text-can-hijack-ai-enabled-robots/)
- [Arxiv: Command Hijacking against Embodied AI](https://arxiv.org/html/2510.00181)
- [Arxiv: Physical Adversarial Attacks on LiDAR](https://arxiv.org/abs/2409.20426)
- [Arxiv: Systematic Analysis of Cognitive and Cross-Layer Threats](https://arxiv.org/html/2512.17041)
