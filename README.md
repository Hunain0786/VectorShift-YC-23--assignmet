# LLM Pipeline Builder

## Overview
The **LLM Pipeline Builder** is a modern, full-stack web application designed to help developers and data scientists visually construct, configuration, and validate processing pipelines for Large Language Model (LLM) applications.

As LLM workflows become more complex—involving multiple inputs, text transformations, conditional logic, and model calls—managing them purely in code can become difficult. This tool solves that problem by providing a intuitive **drag-and-drop interface** to design these workflows as directed graphs.

## Features
- **Visual Editor**: Drag and drop nodes to build your pipeline using a powerful node-based editor (powered by ReactFlow).
- **Diverse Node Types**: Support for various pipeline components:
  - **Input/Output**: Define entry and exit points for data.
  - **LLM Node**: specific nodes to represent valid LLM calls.
  - **Text & Transform**: Utilities for text manipulation.
  - **Logic & Control Flow**: `Conditional`, `Merge`, `Filter`, and `Delay` nodes for complex workflows.
- **Real-time DAG Validation**: The backend instantly checks if your constructed pipeline forms a valid Directed Acyclic Graph (DAG), ensuring there are no infinite loops before execution.
- **Modern UI**: Clean, responsive aesthetic built with Tailwind CSS.

## Tech Stack

### Frontend
- **React**: Core UI library.
- **ReactFlow**: For rendering the interactive node graph.
- **Tailwind CSS**: For styling and layout.
- **Axios/Fetch**: For communicating with the backend API.

### Backend
- **Python**: Primary programming language.
- **FastAPI**: High-performance web framework for handling API requests.
- **NetworkX / Algorithmic Logic**: efficient graph algorithms to validate pipeline structure (DAG detection).

## Project Structure
```
/
├── backend/            # Python FastAPI server
│   └── main.py         # API endpoints and validation logic
├── frontend/           # React application
│   ├── public/
│   ├── src/
│   │   ├── nodes/      # Component definitions for each node type (LLM, Input, etc.)
│   │   └── ...
│   └── package.json
└── README.md
```

## Getting Started

### Prerequisites
- **Node.js** (v16 or higher)
- **Python** (v3.8 or higher)

### 1. Backend Setup
The backend runs on port `8000` by default.

1. Navigate to the backend directory:
   ```sh
   cd backend
   ```

2. (Optional) Create a virtual environment:
   ```sh
   python -m venv venv
   # Windows
   .\venv\Scripts\activate
   # macOS/Linux
   source venv/bin/activate
   ```

3. Install dependencies:
   ```sh
   pip install fastapi uvicorn
   ```

4. Start the server:
   ```sh
   uvicorn main:app --reload
   ```
   The backend is now running at `http://localhost:8000`.

### 2. Frontend Setup
The frontend runs on port `3000` by default.

1. Open a new terminal and navigate to the frontend directory:
   ```sh
   cd frontend
   ```

2. Install dependencies:
   ```sh
   npm install
   ```

3. Start the development server:
   ```sh
   npm start
   ```
   The application should automatically open in your browser at `http://localhost:3000`.

## Usage
1. Open the application in your browser.
2. Use the toolbar/sidebar to drag nodes onto the canvas.
3. Connect nodes by dragging lines between their handles.
4. Configure individual nodes by clicking on them (if configurable).
5. Click the **Submit** or **Validate** button to send the pipeline to the backend.
6. The system will alert you if the pipeline is a valid DAG (Directed Acyclic Graph) and provide stats like the number of nodes and edges.
