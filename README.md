<div align="center">
  <h1 style="border-bottom: none;">
    Wormhole
  </h1>
</div>
<p align="center" width="100%">
  <img src="assets/logo.png" alt="Wormhole Logo" width="200"/>
</p>

# 🚀 Google A2A Toolkit & Agents
[![Python 3.9+](https://img.shields.io/badge/python-3.9%20|%203.10%20|%203.11-blue?logo=python)](https://www.python.org)
[![License](https://img.shields.io/github/license/wormholeportal/Wormhole)](https://www.apache.org/licenses/LICENSE-2.0)

**Wormhole** wraps Google's official [A2A](https://github.com/google/A2A) repository with a developer-friendly layer that:

📦 Minimal code to spin up an **A2A Agent**  
⚡ keeps in lock-step with upstream **Google A2A** releases  
🌱 adds plug-ins for **Google ADK**, **OpenAI Agents SDK**, **MCP** and more on the way!

## 🛠 Installation

```bash
# Clone the repository
git clone https://github.com/wormholeportal/Wormhole.git
cd Wormhole

# Create a virtual environment and install development dependencies
uv venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
uv pip install -e ".[dev]"  # editable install + dev extras
```

UV is a modern Python package management tool that's faster and more reliable than pip. To install with UV:
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
# Verify installation
uv --version
```

## ⚡ A2A Agents 

The ```wormhole.a2a``` library allows you to build and run agents using various frameworks, including the Google Agent Development Kit (ADK) and OpenAI Agents SDK. We aim to support more agent frameworks in the future—community contributions are welcome!

### Prerequisites

•	Python 3.9+

•	UV Package Manager

•	Access to a compatible LLM and a valid API key (e.g., Google API key)

### Quick Start

Step 1: Navigate to the agent sample directory

```bash
# For example, the adk agent
cd wormhole/agent/adk
```

Step 2: Set up your environment

```bash
# Create a .env file to store your API credentials:
echo "GOOGLE_API_KEY=your_api_key_here" > .env
```
You can also add other environment variables if required by your agent.

Step 3: Launch the agent server

```bash
# Default host and port
uv run .

# Or specify a custom host and port
uv run . --host localhost --port 11011
```

Make sure to note the port if you override it—it will be needed by the A2A client.


Step 4: Start the A2A CLI client in a new terminal

```bash
cd wormhole/cli

# Replace YOUR_PORT with the correct agent server port
uv run . --agent http://localhost:YOUR_PORT

# Example:
# uv run . --agent http://localhost:11011
```
Make sure the port matches the agent server port you started above.


## 📦 Project Structure

```
wormhole/
├── a2a/
│   ├── server/     # Google A2A server
│   ├── client/     # Google A2A client
│   ├── utils/
├── agent/
│   ├── adk/        # Google ADK agent 
│   ├── oai/        # Openai agent 
├── cli/            # A2A-compatible CLI client
└── ...
```

## 🤝 Contributing

We're actively expanding support for other agent frameworks. If you're interested in contributing or adding custom tools, feel free to open a PR or discussion!


## 📝 License

The Wormhole is an open-source project, under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0), and is open to contributions from the community.