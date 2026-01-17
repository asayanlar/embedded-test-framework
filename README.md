# Embedded Test Framework

**A multithreaded C++ simulation framework for embedded system pipelines.**

This project simulates an embedded data processing pipeline with multiple producers and consumers using thread-safe queues. It is designed as a **testing framework** to allow engineers to safely validate concurrency, timing, and system behavior **before deploying to real hardware**.

---

## Planned Features

- **Multithreaded Producers & Consumers**: Simulate sensors and data processors.
- **Thread-Safe Queues**: Safe communication between threads using mutexes and condition variables.
- **Deterministic Execution**: Configurable task intervals to mimic real-time behavior.
- **Logging & Monitoring**: Tracks queue size, processing times, and alerts.
- **Graceful Shutdown**: Ensures threads complete work and clean up safely.
- **Optional Fault Injection**: Simulate delays or dropped data for testing recovery.

---

## Planned Project Structure

```
embedded-test-framework/
├── LICENSE                   # MIT License
├── README.md                 # Project description and instructions
│
├── src/                      # Source files
│   ├── main.cpp              # Entry point: starts simulation, threads, and logger
│   ├── sensor_data.h         # Defines SensorSample struct (id, values, timestamp)
│   ├── thread_safe_queue.h   # Thread-safe queue template class
│   ├── thread_safe_queue.cpp # Optional: separate implementation
│   ├── producer.h            # Producer thread class (generates SensorSample)
│   ├── producer.cpp
│   ├── consumer.h            # Consumer thread class (processes SensorSample)
│   ├── consumer.cpp
│   ├── logger.h              # Logger/monitoring class
│   ├── logger.cpp
│   └── utils.h               # Optional helpers (timing, random faults, etc.)
│
├── include/                  # Optional: header-only files
└── build/                    # Optional: compiled binaries output folder
```

---

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/asayanlar/embedded-test-framework.git
Build the project (using g++ or your preferred C++ compiler):

g++ -std=c++17 src/*.cpp -o embedded-test-framework -lpthread
Run the simulation:

./embedded-test-framework
Observe logs showing data flow, queue size, and processing statistics.
