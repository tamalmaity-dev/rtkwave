# RTKWave 🌊

![License: Apache 2.0](https://shields.io)
![Go Version](https://shields.io)
![Platform](https://shields.io)

> A modern, lightweight, and high-performance RTK management software designed to orchestrate live NTRIP streams, manage base station corrections, and monitor rover telemetry seamlessly.

RTKWave acts as the central control plane for your Real-Time Kinematic operations, eliminating the friction of data-stream routing, log management, and connection drift monitoring.

---

## ✨ Features

*   **Stream Orchestration:** Seamlessly route NTRIP/RTCM data packets between bases, casters, and rovers.
*   **Real-Time Monitoring:** Live telemetry dashboard tracking stream health, latency, and satellite carrier wave stabilization.
*   **Log Management:** Highly optimized logging system for storing, splitting, and exporting raw geospatial logs.
*   **Developer Friendly:** Minimal dependencies with an optional, intuitive Command-Line Interface (CLI) and clean API endpoints.
*   **Connection Resilience:** Automatic fallback and reconnection logic to handle sudden cellular or network drops smoothly.

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following environments installed on your machine:
*   **Go** >= 1.20
*   An active network connection to your NTRIP caster or GNSS hardware receiver.

### Installation

Clone the repository and compile the binary:

```bash
git clone https://github.com
cd rtkwave
go build -o rtkwave main.go
```

### Quick Start Configuration

1. Create a copy of the sample environment file:
   ```bash
   cp .env.example .env
   ```
2. Open the `.env` file and configure your primary RTK Base Station or NTRIP Caster credentials:
   ```env
   NTRIP_CASTER_URL=caster.example.com
   NTRIP_PORT=2101
   MOUNTPOINT=BASE01
   USERNAME=your_username
   PASSWORD=your_password
   ```
3. Run the manager application:
   ```bash
   ./rtkwave
   ```

---

## 🛠️ Usage Example

You can trigger and check active stream pipes directly via the module or CLI interface:

```bash
./rtkwave connect --mount BASE01 --rover ROVER_A
```

*Expected Terminal Output:*
```text
[RTKWave] [INFO] Initializing carrier-wave tracking engine...
[RTKWave] [INFO] Successfully established link with caster.example.com:2101
[RTKWave] [INFO] Streaming RTCM3 corrections -> ROVER_A [Latency: 42ms]
```

---

## 📂 Project Structure

```text
rtkwave/
├── src/                  # Main source files
│   ├── core/             # Stream routing and processing engine
│   ├── config/           # Environment and network profiles
│   └── utils/            # Data loggers and parsing scripts
├── tests/                # Unit tests and stream simulation profiles
├── .env.example          # Template configuration file
├── LICENSE               # Open-source license file
└── README.md             # This structural documentation file
```

---

## 🤝 Contributing

Contributions make the open-source community an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the Apache 2.0 License. See `LICENSE` for more information.

---
