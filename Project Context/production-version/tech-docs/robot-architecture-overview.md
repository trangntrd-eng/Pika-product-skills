# PikaRobot — High Level Technical Architecture (Product Team)

> **Loại tài liệu:** Technical Overview for Product Team
> **Ngôn ngữ:** English (tài liệu gốc)
> **Trạng thái:** Active
>
> **Context:** This is a 3-team project: **Tech** (robot + backend software), **AI** (AI components), **Product** (experiences + learning). This document is scoped to **Product Team** — not a technical/hardware spec. Focus: capabilities, limitations, and operating mechanisms that affect UX, content, and feature design.

---

## 1. Introduction & Document Objectives

- **Purpose:** Help the Product team properly understand the **capabilities – limitations – operating mechanisms** of the robot, in order to design appropriate features and experiences.
- This is a "technical document for Product", focusing only on what affects UX, content, and feature design.

---

## 2. PikaRobot — Robot Brief (High-Level Overview)

### 2.1. Objectives & Role

PikaRobot is an educational robot for young children, focusing on personalized learning, natural interaction, and daily motivation. The robot plays two roles:

- **Companion**
- **Learning guide**

**Core Values**
- Engaging learning that matches each child's pace
- Natural interaction like a friend
- Maintaining sustainable learning habits
- Accompanying parents in their child's development journey

---

## 3. System Architecture (High-Level)

The system is divided into 3 major layers.

### 3.1. PikaRobot (On-device)

**Physical device**, approximately 20 cm tall, where all direct interactions take place.

**Main Hardware**

| Component | Spec | Product Impact |
|---|---|---|
| **MCU A** (ESP32-S3 N16R8) | Servo + LCD + LED + sensors + buttons | Controls physical expressions and interaction |
| **MCU B** (ESP32-S3 N16R8) | Audio, speaker, streaming, buffering | Controls voice I/O |
| **4-inch TFT LCD screen** | 480×320, ST7796 driver, 8-bit parallel | Displays GIFs + overlay image/text (≤20% for stable FPS) |
| **I2S omnidirectional microphone** | — | Captures child's voice |
| **5W speaker** | — | Plays Pika's voice |
| **8GB SD Card** | GIF, UI assets, offline audio | Stores offline content |
| **MG90S Servo (3×)** | Neck rotation, base rotation, arm raise/lower | Physical gestures (nodding, greeting, waving) |
| **Vibration touch sensors** | Forehead, left tickle, right tickle, back | Touch-triggered reactions |
| **IR lift sensor** | — | Detects when robot is picked up |
| **Chest LED** | 4 states: listening, network error, connected, processing | Status indicator |
| **5 buttons** | Power, left, enter, right, menu | Direct navigation |

### 3.2. On-device Operating Mechanism

- **Local state machine** → instant response (GIF, LED, servo) even when backend has latency.
- **Multi-layer expressions:**
  - Background GIF (main emotion)
  - Text/image overlay ≤20%
  - All run from SD for smooth and fast performance
- **Tactile & motion sensors:**
  - Touch → immediate reaction
  - Lift up → change expression
- **Motion control:**
  - Neck rotation → create eye contact
  - Base rotation → turn direction/greet
  - Arm raise–lower → wave, reward
- **Cloud connection:** Continuously sends audio + state + sensor events → backend calculates behavior.

---

### 3.3. Backend & AI Services

PikaRobot's backend is a multi-tiered AI platform responsible for conversation processing, behavior coordination, personalized learning path, and continuous connection with the robot.

> **For full detail:** See [ai-platform-architecture.md](./ai-platform-architecture.md)

#### 3.3.1. Conversational AI Agent Layer

The layer responsible for understanding and responding to all conversational interactions from children.

| Component | Function |
|---|---|
| **ASR – Speech Recognition** | Converts audio from robot into text, optimized for children's voices |
| **LLM Engine** | Understands speech, determines intent, generates responses, applies "Pika" personality via dynamic System Prompt |
| **TTS – Robot Voice** | Creates expressive Pika voice with low latency |
| **Behavior Suggestion Module** | Converts LLM reasoning into specific behaviors: GIF, servo pose, LED, sound effects, text overlay |

#### 3.3.2. Dialogue Management & Agent Routing

Coordinates conversations so the robot responds intelligently, seamlessly, and purposefully.

**a) In-session Routing**
- Analyzes intent of each utterance.
- Selects appropriate Agent (greeting, teaching vocabulary, explaining, storytelling…).
- Ensures natural transitions between tasks within the same session.

**b) Out-of-session Routing (ADM – Adaptive Dialogue Management)**
- Allows the robot to autonomously initiate new conversation sessions based on events or conditions (lesson completion, habit maintenance reminders, practice suggestions).
- Determines which Agent should be activated based on context.

#### 3.3.3. Memory Module (Mem0)

The robot's long-term memory center, used to increase personalization.

**Structured memory storage includes:**
- personal information (name, preferences, favorite topics)
- recurring mistakes
- concentration level
- learning progress
- most recent interactions

**Operating Mechanism:** Detects valuable information from conversations → saves in schema format → extracts and includes in Prompt whenever Agent processes conversation.

**Impact on robot experience:**
- Robot remembers what the child has learned → selects appropriate lessons.
- Remembers preferences → personalized expressions and dialogue.
- Remembers last learning day → friendly schedule reminders.

#### 3.3.4. Learning Path Engine (LPE)

The engine that builds and adjusts the child's learning path.

| Component | Function |
|---|---|
| **Path Registry** | Repository of all topics, lessons, and skills |
| **Progress Tracker** | Tracks the child's current position in the path |
| **Next Lesson Selector** | Decides the next lesson based on progress, mistakes, concentration state, and child's memory |

**Impact on robot:** Sends appropriate learning guidance; coordinates rewards, mini-missions, motivational overlays; selects animations or poses when encouragement is needed.

#### 3.3.5. Communication Layer (Robot ↔ Cloud)

| Direction | Data |
|---|---|
| **Robot → Backend** | Audio captured from child; sensor events (touch, lift, button press); system state (listening, speaking, network loss); learning progress information |
| **Backend → Robot** | Response audio (streaming); servo/LED/GIF commands; text/emoji overlay; state control ("thinking", "waiting", "scene transition") |

#### 3.3.6. Overall Backend Role in Robot Experience

**Backend handles all the "intelligence":**
- Understanding what the child says
- Thinking of how to respond
- Selecting appropriate expressive behaviors
- Personalizing based on memory
- Guiding lessons according to long-term path

**On-device handles:**
- Immediate response (eyes, GIF, LED, servo)
- Screen content display
- Emotion expression
- Playing audio from backend
- Local state management

---

### 3.4. Parent Companion App

- Track progress, reports
- Configuration, duration management
- Habit tracking

---

## 4. Core Functional System

_(Coordinated by AI backend and designed by product team)_

| System | Function |
|---|---|
| **Navigation System** | Coordinates states: awake – greet – learn – break – rest |
| **Buddy System** | Provides "Pika" personality: emotions, responses, voice |
| **Adaptive Learning Path** | Adjusts difficulty, suggests practice or rest |
| **Retention System (Hook Model)** | Micro (XP, stars) / Meso (daily/weekly goals) / Macro (monthly reports, content unlock) |
