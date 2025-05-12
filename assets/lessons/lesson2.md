# Lesson 2: Building AI Models with Kafka

---

**Goal:**  
Show how to build Kafka consumers that run AI models (e.g., object detection) on incoming data.

## Schema

### 1. Recap of Previous Post
- Briefly summarize what was covered in Lesson 1.

### 2. Kafka Consumer Basics
- What is a consumer?
- How does it subscribe to topics?

### 3. Integrating AI Models
- Example: Human detection using a pre-trained model (e.g., YOLO, OpenCV).
- Consume frames from Kafka, run inference, and structure results.

### 4. Writing Results to Kafka
- Produce detection results to a new Kafka topic (e.g., `human-results`).

### 5. Code Example
- Full script: Consumer + AI inference + result producer.

### 6. Testing & Debugging
- Check result topics for output.

### 7. Summary & Next Steps
- Wrap up and preview the next lesson.

---
