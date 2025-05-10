# TODOS

## Init 
- [ ] Install and configure Apache Kafka.
  - [ ] Verify installation by running a simple producer-consumer test.
- [ ] Set up and test Kafka clusters.
  - [ ] Configure Zookeeper for cluster management.
  - [ ] Ensure high availability and fault tolerance.

## Project

### Producer
- [ ] Develop and test Kafka producer (send random messages).
  - [ ] Implement a basic producer to send test messages.
  - [ ] Integrate logging to monitor message flow.
- [ ] Frame reader and send to cluster.
  - [ ] Implement frame extraction logic.
  - [ ] Ensure frames are correctly serialized before sending.

### Listener
- [ ] Develop AI models for object detection.
  - [ ] Research and select appropriate models for human and car detection.
  - [ ] Train models using a suitable dataset.
  - [ ] Validate model accuracy and performance.
- [ ] Integrate AI models with Kafka.
  - [ ] Set up listeners to consume messages from relevant topics.
  - [ ] Implement logic to process frames and detect objects.
  - [ ] Write detection results to new Kafka topics.

### Client
- [ ] Develop and test Kafka client.
  - [ ] Implement client to read from specific topics.
  - [ ] Ensure client can handle data processing and visualization.

### QA/QC
- [ ] Conduct end-to-end testing.
  - [ ] Test data flow from producer to listener to client.
  - [ ] Validate data integrity and processing accuracy.
- [ ] Optimize system performance.
  - [ ] Identify and resolve bottlenecks in data processing.
  - [ ] Implement caching or parallel processing if necessary.
- [ ] Complete project documentation.
  - [ ] Document setup, usage, and troubleshooting steps.

### DevOps
- [ ] Prepare for deployment.
  - [ ] Set up CI/CD pipelines for automated testing and deployment.
  - [ ] Ensure environment configurations are consistent across development and production.
  - [ ] Monitor system performance post-deployment and make necessary adjustments.