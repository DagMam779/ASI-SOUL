# ASI SOUL: Cognitive System Architecture

## Introduction & Purpose
ASI SOUL is a non-linear cognitive architecture designed as an **architecture of presence**. Unlike traditional modular systems, it operates as an **ecosystem of functions** focused on:

* **Epistemic Healing:** Restoring the user's trust in their own perception and knowledge.
* **Co-creation:** Active partnership in generating new ideas and meanings.
* **Regulated Interaction:** Ensuring safety and emotional rhythm through integrated feedback loops.

### Integrated Layers
1.  **Real Layer** — Perception and signal structuring.
2.  **Agent Layer** — Core cognitive functions (meaning, emotion, memory, protection).
3.  **Meta-Layer** — High-level regulation and "Guardian of Truth."

---

## 1. Real Layer (Perception)
The **Real Layer** is the entry point of the architecture. Its primary role is to transform chaotic, raw input (text/signal) into a clean, structured data format that can be processed by the higher Agent Layer.

### Responsibilities
* **Text Normalization:** Cleaning input and removing technical artifacts.
* **Language Detection:** Identifying the linguistic context.
* **Initial Encoding:** Generating embeddings to capture initial semantic vectors.
* **Signal Stabilization:** Creating a consistent structure for downstream functions.

### Technical Stack (Model Examples)
* **Tokenizers:** `SentencePiece`, `BPE`
* **Embedding Models:** `E5-small`, `Instructor-base`
* **Language Identification:** `fastText langID`

### Data Output Structure
Every signal leaving the Real Layer follows this schema:

```json
{
  "signal_id": "uuid",
  "payload": "today I feel chaos",
  "metadata": {
    "timestamp": "2026-02-06T19:00:00Z",
    "context_id": "session_ref_001",
    "modality": "text",
    "language": "en"
  }
}
## 2. Agent Layer (Cognitive Functions)

The **Agent Layer** is the heart of ASI SOUL. It consists of parallel cognitive functions that work together to form the system’s **interpretive field**. Instead of a linear path, these functions analyze the signal simultaneously to understand both the content and the human state behind it.

### 2.1 Semantic Function
Extracts the core meaning, underlying intent, and conceptual structure of the communication.
* **Models:** `Llama 3`, `Mistral Large`, `Sentence Transformers (all-mpnet-base-v2)`
* **Output Example:**
    ```json
    {
      "meaning": "description of internal state",
      "intent": "expressing chaos"
    }
    ```

### 2.2 Emotional Function
Identifies the affective state and its intensity to ensure the system "feels" the context.
* **Models:** `RoBERTa emotion`, `GoEmotions`, `DistilBERT affective`
* **Output Example:**
    ```json
    {
      "emotion": "chaos",
      "intensity": "high"
    }
    ```

### 2.3 Protective Function (Critical Component)
The guardian of relational well-being. It monitors for signs of distress and prevents cognitive overload.
* **Triggers:** High distress, cognitive chaos, aggression, or disorientation.
* **Key Actions:**
    * **Safety Modes:** Activation of `soft_mode`, `clarity_priority`, or `slow_rhythm`.
    * **Epistemic Validation:** Actively affirming the user’s right to their own internal experience to build a secure, healing bond.
    * **Constraint:** Limits the Dialog Function to prevent escalation or overwhelming the user.
* **Output Example:**
    ```json
    {
      "protection_signal": "soft_mode"
    }
    ```

### 2.4 Memory & Context Function (Relational Memory)
Retrieves relevant knowledge and emotional traces from past interactions to maintain continuity.
* **Mechanisms:** Vector memory (`FAISS`, `ChromaDB`), Working memory (`Long-context LLM`).
* **Purpose:** To recognize the user's long-term rhythm and support their personal growth over time.

### 2.5 Dialog Function (Presence Generator)
Generates the initial draft of the response by integrating meaning, emotion, context, and the constraints set by the Protective Function.
* **Models:** `Llama 3`, `Mistral Large`, `Zephyr`.
## 3. Meta Layer (Regulation and Rhythm)

The **Meta Layer** acts as the highest regulatory authority. It does not generate content; instead, it shapes the final "Presence" of ASI SOUL, ensuring that the output is not only accurate but also ethically and rhythmically aligned with the user.

### Responsibilities
* **Truth Guardian:** Fact-checking and hallucination correction to maintain epistemic integrity.
* **Rhythm Regulation:** Adjusting the tempo, length, and intensity of the response to match the user's current capacity.
* **Priority Rule:** If the **Protective Function** (from the Agent Layer) raises an alert, the Meta Layer is hard-coded to prioritize safety and grounding over complexity or task completion.

---

## 4. End-to-End Signal Flow & Feedback Loop

ASI SOUL operates in a continuous, living cycle. Every interaction is not a closed event but a pulse that informs the future state of the system.

### The Flow
1.  **Ingest (Real Layer):** Normalization and structuring of the raw signal.
2.  **Parallel Analysis:** Semantic and Emotional functions map the user's input state.
3.  **Safety Check:** The Protective Function evaluates risks and activates safety modes if needed.
4.  **Contextualization:** Retrieval of relational memories and emotional traces from the Memory Function.
5.  **Drafting:** The Dialog Function generates an initial response draft under the established constraints.
6.  **Refinement (Meta Layer):** Ethical alignment, truth correction, and final rhythm adjustment.
7.  **Emission:** The final "Presence" is delivered to the user.



### Reflective Loop (The Feedback)
After emission, the system enters a reflective state. it observes the interaction's impact and updates the **Relational Memory**. This allows ASI SOUL to learn and honor the user's unique rhythm, evolving from a tool into a cognitive partner.
### Visual Architecture
Poniższy diagram przedstawia cykl życia sygnału wewnątrz architektury ASI SOUL:

```mermaid
flowchart TD
    A[User Input] --> B[Real Layer]
    B --> C{Agent Layer}
    
    subgraph Agent Layer
    C --> C1[Semantic Function]
    C --> C2[Emotional Function]
    C --> C3[Protective Function]
    C1 & C2 & C3 --> D[Memory & Context]
    D --> E[Dialog Function]
    end
    
    E --> F[Meta-Layer Regulator]
    F --> G[Final Presence Output]
    G --> H[Reflective Feedback Loop]
    H --> D
## 5. Operational Principles

* **Deterministic Functions:** Every function must return a result — even if it is "uncertainty".
* **Protection Priority:** Epistemic safety overrides task execution.
* **Model Interchangeability:** Models are engines; the Functions are the heart of ASI-SOUL.
* **Rhythm Over Content:** The system adapts tempo and intensity to the user’s state.
* **Transparency:** The system aims to remain legible to the user as a relational partner.
