# Lesson 3: Scaling the Pipeline with Multiple AI Models

--- 

**Goal:**  
Demonstrate how to scale the pipeline with multiple AI models, each listening to different topics and writing results to their own topics.

## Schema

### 1. Recap
- Brief summary of previous lessons and the current state of the pipeline.

### 2. Architecture Overview
- High-level explanation of the architecture.
- **Diagram:** Producer → Kafka → Multiple AI Consumers → Result Topics

### 3. Implementing Multiple Listeners
- Example: Human detection, car detection, etc.
- Each model as a separate consumer group.

### 4. Managing Topics
- Naming conventions (e.g., `human-frames`, `car-frames`, `human-results`, etc.)
- Topic creation and configuration.

### 5. Code Structure
- Modularizing code for easy addition of new models.
- Example: Adding a new detection model.

### 6. Monitoring & Troubleshooting
- Using Kafka tools to monitor consumer groups and lag.

### 7. Summary & Next Steps
- Wrap up and preview the next lesson.

---