# Nahual Engine

**A Deterministic Neuro-Symbolic Engine for Non-Euclidean Embodied Phenomenology**

The **Nahual Engine** is a next-generation "world creation engine" designed to simulate non-human consciousness and break traditional space-time limitations. By integrating **Neuro-Symbolic AI** with **Relativistic** and **4-Dimensional** physics, it enables players to shift between the "Tonal" (Human/Rational) and "Nahual" (Animal/Magical) states, experiencing the world through radically different sensoriums.

---

## 🔮 Core Philosophy

The engine is built on the Mesoamerican concept of the **Nahual**, representing a dual existence:

* **The Tonal (System 2):** The ordered, causal, deterministic world of physics and logic.
* **The Nagual (System 1):** The chaotic, intuitive, generative world of sensory flow and transformation.

We implement this via a **Grounding-Instructibility-Alignment (G-I-A)** framework, ensuring that the generative imagination of AI never breaks the deterministic laws of the game world.

---

## 🚀 Key Features

### 🧠 Neuro-Symbolic "Split-Brain" AI

We solve the hallucination problem by decoupling intent from execution:

* **Neural Layer (System 1):** Quantized Small Language Models (SLMs like Phi-3/MobileLLaMA) generate narrative intent, dialogue, and atmospheric "vibes."


* **Symbolic Layer (System 2):** A GOAP (Goal-Oriented Action Planning) system validates all neural outputs against a PDDL (Planning Domain Definition Language) rule set. The AI can *want* to do anything, but can only *do* what is physically possible.



### 🔒 Quantized Determinism

To allow for procedurally generated multiplayer worlds, the engine enforces bit-exact reproducibility across all clients:

* **Fixed-Point Math:** Simulation logic uses software-based fixed-point arithmetic to prevent floating-point drift between different GPU architectures (e.g., NVIDIA vs. AMD).
* **Seed Hierarchy:** World generation is driven by a `Master Seed` -> `Chunk Seed` -> `Entity Seed` cascade, allowing local regeneration without global desynchronization.



### 🦇 Computational Phenomenology (The Sensorium)

We replace standard cameras with physics-based rendering of non-visual senses:

* **Acoustic Ray Tracing:** Visualizes Echolocation using LIDAR-style point clouds and Doppler-shift coloring (Red=Receding, Blue=Approaching).
* **Magnetoreception:** Renders the geomagnetic field as 3D volumetric streamlines that dip and curve based on inclination, allowing navigation without landmarks.


* **Electroreception:** Uses "Dielectric Shaders" to reveal bio-electric fields of hidden entities through walls, pulsating with their heartbeat/fear state.



### ⏳ Non-Euclidean Physics

* **Relativistic Rendering:** Players can lower the speed of light (), causing real-time Lorentz contraction, time dilation, and searchlight effects.


* **4D Slicing:** Native support for 4-Dimensional tetrahedral meshes. Players navigate the -axis to bypass 3D obstacles (walking "through" walls via the 4th dimension).

---

## 🛠️ Technology Stack

| Component | Technology | Reasoning |
| --- | --- | --- |
| **Language** | **Rust** | Memory safety and strict control over data types for deterministic fixed-point math.

 |
| **Graphics** | **Vulkan 1.3** | Access to `VK_KHR_ray_query` for acoustic simulation and compute shaders for 4D slicing.

 |
| **Physics** | **Jolt Physics** | Deterministic rigid body simulation compatible with snapshot rollback. |
| **AI Runtime** | **ONNX / TensorRT** | Optimized execution of INT8 quantized SLMs on consumer hardware.

 |
| **Networking** | **GGRS** | Rust implementation of GGPO for rollback networking in generative environments.

 |

---

## 🕸️ Networking Architecture

The engine uses **Deterministic Lockstep** with **Neural Rollback**:

1. **Input-Only Sync:** Clients send inputs, not positions. The deterministic simulation ensures the world evolves identically on all machines.


2. **Predictive Rollback:** During latency, the local client predicts remote inputs. If the prediction is wrong, the engine "rewinds" the simulation—including the RNG state of the generative AI—and replays it with the correct input.



---

## 📦 Installation

### Prerequisites

* **Vulkan SDK 1.3.2+** 


* **Rust (latest stable)**
* **Python 3.10+** (for AI model conversion/quantization)

### Build Instructions

```bash
# Clone the repo
git clone https://github.com/your-org/nahual-engine.git
cd nahual-engine

# Download Quantized Models (Phi-3 / MobileLLaMA)
./scripts/download_models.sh

# Build the Engine (Release mode required for performance)
cargo build --release

# Run the "Jaguar" Demo
./target/release/nahual_engine --profile=jaguar --seed=12345

```

---

## 🔮 Roadmap

* **Phase 1:** Vulkan 4D Renderer & OpenRelativity integration.
* **Phase 2:** Neuro-Symbolic Bridge (LLM -> PDDL).
* **Phase 3:** Acoustic & Magnetic sensorium shaders.
* **Phase 4:** Multiplayer Rollback & World Builder tools.

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

*“To become the Nahual is not to change your shape, but to change your perception.”*
