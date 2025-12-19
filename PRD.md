# Product Requirements Document: The Nahual Engine

## 1. Executive Summary

**Project Name:** Nahual Engine  
**Version:** 1.0-Draft  
**Date:** December 19, 2025

### Vision

To build a deterministic "world creation engine" that transcends traditional Euclidean game mechanics by integrating bleeding-edge Neuro-Symbolic AI with relativistic and 4-dimensional physics. The engine will enable players to "embody" non-human consciousness (the Nagual) through rigorous computational phenomenology, challenging standard space-time limitations and enabling shared, hallucination-free generative experiences.

### Core Value Proposition

- **Embodied Otherness:** Moving beyond visual avatars to simulate the sensorium of non-human entities (echolocation, magnetoreception, electroreception).

- **Deterministic Generativity:** Solving the "hallucination" and "desync" problems of current GenAI by enforcing bit-exact determinism via a Neuro-Symbolic Grounding-Instructibility-Alignment (G-I-A) framework.

- **Non-Euclidean Exploration:** Native support for 4D spatial navigation and relativistic time dilation.

---

## 2. User Personas & Use Cases

### 2.1 The "Walker" (Player)

**Goal:** To escape human cognitive limitations and experience a "shamanic" shift in perspective.

**Pain Point:** Modern games are visually realistic but phenomenologically human (camera = eyes).

**Use Case:** A player shifts from "Tonal" form (human) to "Nagual" form (Jaguar). The screen goes dark (visual cortex suppression), and the world is revealed only through "Bio-Electric" pulses emitted by prey, visible through walls.

### 2.2 The "Dreamer" (Creator)

**Goal:** To build persistent, evolving worlds without writing low-level code.

**Pain Point:** Procedural generation is often random and messy; pure LLM generation is non-deterministic and breaks gameplay rules.

**Use Case:** The creator types a prompt: "A rainforest where time moves slower near the river." The engine uses the Neuro-Symbolic core to translate this into a deterministic PDDL rule set and a relativistic physics modifier, ensuring the river works identically for all visitors.

---

## 3. Functional Requirements

### 3.1 Core Systems: The Neuro-Symbolic Brain

To ensure the world is both creative (Nagual) and logical (Tonal), the engine must utilize a split-brain architecture.

#### FR 1.1: Dual-Process AI Architecture

- **System 1 (Neural/Nagual):** Utilizes quantized Small Language Models (SLMs) (e.g., Phi-3, MobileLLaMA) for texture, dialogue, and "vibes" generation.

- **System 2 (Symbolic/Tonal):** Utilizes a PDDL (Planning Domain Definition Language) based Goal-Oriented Action Planner (GOAP) for logic, physics, and causal consistency.

- **Requirement:** The Neural layer must never execute game actions directly. It must output a structured goal (e.g., JSON schema) which the Symbolic layer validates and executes.

#### FR 1.2: The G-I-A Framework Implementation

- **Grounding:** All AI inputs must be grounded in the Entity Component System (ECS) state, not just text prompts.

- **Instructibility:** The system must accept high-level constraints (e.g., "Gravity is inverted") that override neural generation weights.

- **Alignment:** The Symbolic planner must reject any Neural output that violates the "World Axioms" (e.g., creating a door in an unbreakable wall).

### 3.2 Determinism & World Generation

To support multiplayer "shared hallucinations," the engine must be bit-exact deterministic across different hardware.

#### FR 2.1: Quantized Determinism

- **Requirement:** All floating-point math for simulation-critical systems (Physics, AI Logic) must use fixed-point arithmetic libraries (e.g., in Rust/C++) to avoid floating-point non-associativity across different GPU architectures.

- **Inference:** Neural inference must use Temperature=0 (Greedy Decoding) and fixed-seed quantization for all logic-bearing tokens.

#### FR 2.2: Seed Hierarchy

- **Requirement:** The world must be generated from a hierarchical seed structure (Master Seed → Chunk Seed → Entity Seed). This allows a specific 4D sector to be regenerated identically on any client without transmitting the full geometry.

### 3.3 Computational Phenomenology (The Sensorium)

The engine must render non-visual senses as primary gameplay mechanics, not just UI overlays.

#### FR 3.1: Acoustic Ray Tracing (Echolocation)

- **Physics:** Implement real-time acoustic ray tracing using Vulkan Ray Queries. Rays must bounce based on surface acoustic impedance (hardness) rather than optical reflectivity.

- **Visualization:** Render a "Lidar-like" point cloud where point decay represents "echo memory." Doppler shift must be visualized via color spectrum (Red=Receding, Blue=Approaching).

#### FR 3.2: Magnetic Vector Fields (Magnetoreception)

- **Physics:** Simulate a volumetric 3D vector field representing the geomagnetic flux.

- **Visualization:** Render volumetric streamlines (particle flows) that orient based on the player's heading relative to "Magnetic North." In "Nagual" form, these lines must dip (inclination) to guide players to resources.

#### FR 3.3: Dielectric Shaders (Electroreception)

- **Physics:** Implement an Inverse-Cube Law (1/r³) detection radius for bio-electric fields.

- **Visualization:** A "Dielectric Pass" shader that ignores Z-buffering (wall hacks) to reveal the nervous systems of hidden entities. Intensity must pulse in sync with the target's "Heartbeat/Fear" state variable.

### 3.4 Non-Euclidean Physics

#### FR 4.1: Relativistic Rendering (OpenRelativity Integration)

- **Mechanic:** Allow the speed of light (c) to be a variable gameplay parameter.

- **Shaders:** Implement Lorentz Transformation vertex shaders to simulate Length Contraction and Time Dilation in real-time.

- **Spectrum:** Implement Doppler shifting of textures, where UV/IR textures shift into the visible spectrum at high velocities.

#### FR 4.2: 4-Dimensional Slicing

- **Geometry:** Store world data as 4D tetrahedral meshes.

- **Interaction:** Provide a "Slicing" mechanic where players rotate the 3D cross-section of the 4D world (moving along the w-axis) to bypass 3D obstacles (walls).

---

## 4. Technical Architecture Specifications

### 4.1 Technology Stack

- **Core Language:** Rust (for memory safety and enforced determinism in the simulation layer)
- **Graphics API:** Vulkan 1.3 (Required for VK_KHR_ray_query and compute shader control)
- **Physics Engine:** Jolt Physics (configured for Deterministic Mode) or a custom 4D solver
- **AI Inference:** ONNX Runtime with INT8 Quantization (for cross-platform deterministic SLM execution)

### 4.2 Networking Architecture

#### AR 1: Deterministic Lockstep Protocol

- **Method:** Transmit user inputs only, not world state. All clients run the simulation locally.

- **Justification:** Essential for maintaining synchronization in a procedurally generated, infinite 4D world where state size is prohibitive.

#### AR 2: Neural Rollback (GGRS)

- **Method:** Use a lightweight NeSy model to predict remote player inputs during latency spikes. If the prediction is wrong, the engine "rolls back" the simulation (and the AI seed state) and re-simulates.

---

## 5. Roadmap & Milestones

### Phase 1: The Tonal Foundation (Months 1-6)

**Goal:** Establish the deterministic physics and rendering core.

**Deliverables:**
- Vulkan renderer with OpenRelativity shaders (Lorentz boosts)
- Fixed-point math library integration for game state
- Basic 4D tetrahedral mesh slicing demo

### Phase 2: The Nagual Intelligence (Months 7-12)

**Goal:** Integrate the Neuro-Symbolic AI.

**Deliverables:**
- ECS integration with PDDL Planner (System 2)
- SLM (Phi-3/Llama-3) quantized inference engine (System 1)
- "Bridge" module converting LLM text → PDDL Goals → Game Actions

### Phase 3: The Sensorium (Months 13-18)

**Goal:** Implement non-human phenomenology.

**Deliverables:**
- Acoustic Ray Tracing pipeline (Echolocation)
- Vector Field visualization (Magnetoreception)
- "Shapeshifting" input mapping (swapping control schemes/sensoriums)

### Phase 4: Genesis (Months 19-24)

**Goal:** Multiplayer integration and World Creation tools.

**Deliverables:**
- Deterministic Lockstep networking with GGRS
- Natural Language World Builder (Text-to-World-State) using the G-I-A framework

---

## 6. Risks and Mitigation

**Risk:** Floating-point drift between GPU architectures (e.g., Nvidia vs. AMD).

**Mitigation:** Strict use of software-based fixed-point math for simulation logic; GPU float math used only for rendering (visuals), not gameplay state.

**Risk:** AI Inference Latency.

**Mitigation:** Use of "Small Language Models" (SLMs) and asynchronous "Thought Threads" where the AI plans 1-2 seconds ahead of the action.
