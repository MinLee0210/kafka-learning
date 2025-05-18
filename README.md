<div style="text-align: center;">

<h1>Kafka Learning</h1>
<img src="assets/static/kafka.png" alt="Lesson 1" width="50%">
</div>

This project is focused on learning and implementing Apache Kafka for real-time data processing. The main components of the project include a Kafka producer, a set of AI models acting as Kafka listeners, and a Kafka client. Additionally, the project will use logging stacks to monitor the data flow and performance of the system. I also use multiple programming languages, such as Python, Rust, and Go to implement the different components of the project to show that the Kafka ecosystem is not limited to a single programming language and as the project is built to be extensible and scalable.

## Project Components

1. **Kafka Producer**
   - Responsible for writing frames into Kafka clusters.
   - Acts as the data source for the Kafka ecosystem in this project.

2. **Kafka Listeners (AI Models)**
   - A set of AI models designed to read from specific Kafka topics.
   - These models perform object detection tasks such as human detection, car detection, etc.
   - The results of these detections are written to other Kafka topics for further processing or analysis.

3. **Kafka Client**
   - Designed to choose relevant topics and read data from them.
   - Provides an interface for accessing processed data from the Kafka ecosystem.

## Getting Started

To get started with this project, you will need to have Apache Kafka installed and configured. Follow the official [Kafka documentation](https://kafka.apache.org/documentation/) for installation instructions.

## Architecture

```mermaid
graph TD
    A[Kafka Producer] --> B[Kafka Cluster]

    B --> C[AI Model: Human Detection]
    B --> D[AI Model: Car Detection]
    B --> E[Other AI Models...]

    C --> F[Kafka Topic: Human Results]
    D --> G[Kafka Topic: Car Results]
    E --> H[Kafka Topic: Other Results]

    F --> I[Kafka Client]
    G --> I
    H --> I

    subgraph Components
        A
        C
        D
        E
        I
    end

    subgraph Kafka Topics
        B
        F
        G
        H
    end
```

## Usage

### Init submodules
```bash
git submodule update --init --recursive
```

### Run Kafka

Run Kafka using docker-compose

```bash
docker-compose -f docker-compose.kafka.yml up -d
```

Turn it off using:

```bash
docker-compose -f docker-compose.kafka.yml down
```

_Remember:_ the terminal must point to the root directory of the project to run the above commands.

### Run Kafka Producer

```bash
python kafka-producer/main.py --video_name rtsp://admin:admin@192.168.1.64:554/Streaming/Channel/101
```

_Remember:_ the terminal must point to the root directory of the project to run the above commands.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue for any improvements or suggestions.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.