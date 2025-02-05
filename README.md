# LLM Pricer

## Overview
LLM Pricer is an autonomous agent framework that utilizes a fine-tuned large language model (LLM) and retrieval-augmented generation (RAG) to identify online deals. The system consists of multiple intelligent agents that collaborate to find and evaluate product deals, leveraging vector databases and machine learning models.

## Goal
The goal is to correctly estimate the price of an item based on its description from Amazon using GPT models, open-source models, RAG, and Random Forest with ChromaDB vectors.

## Features
- **Autonomous Agents**: Specialized agents for scanning, planning, and messaging.
- **Machine Learning Models**: Ensemble and random forest models for pricing predictions.
- **ChromaDB Integration**: Persistent vector database for storing product embeddings.
- **Visualization Tools**: 2D and 3D visualization of pricing data.
- **Web Interface**: Gradio-based frontend for monitoring deals in real-time.
- **Modal API for Hosting**: Deploy and serve the model efficiently on the cloud.

## Key Components
### 1. **Deal Agent Framework (`deal_agent_framework.py`)**
This module acts as the central coordination system, handling agent initialization, memory management, and ChromaDB integration. It:
- Initializes the **PlanningAgent** for deal analysis.
- Loads past deal opportunities from `memory.json`.
- Uses **ChromaDB** for persistent vector storage.
- Generates embeddings and plots for deal distribution.

### 2. **Web Interface (`price_is_right_final.py`)**
A Gradio-based interactive application that provides:
- A real-time dashboard for deal tracking.
- A log panel for agent activities.
- A 3D visualization of product embeddings.

### 3. **Modal API Integration**
To deploy the LLM Pricer using Modal API for scalable hosting:
- **Serverless execution**: Reduce infrastructure overhead.
- **Auto-scaling**: Handle high traffic efficiently.
- **Deployment process**:
  1. Install `modal-client` and set up an API key.
  2. Create a Modal function for model inference.
  3. Deploy the API endpoint for real-time price estimation.
  4. Integrate the API with the web interface.

## Installation
### Prerequisites
Ensure you have Python 3.8+ and install dependencies:
```sh
pip install -r requirements.txt
```

### Running the Framework
To run the deal agent framework:
```sh
python deal_agent_framework.py
```

To launch the web interface:
```sh
python price_is_right_final.py
```

### Deploying with Modal API
To deploy on Modal, follow these steps:
```sh
pip install modal-client
modal deploy api_server.py
```

## Future Enhancements
- Improve deal prediction accuracy using advanced deep learning models.
- Expand the product database with more categories.
- Enhance real-time notifications for detected deals.
- Optimize API inference time and response rate.
