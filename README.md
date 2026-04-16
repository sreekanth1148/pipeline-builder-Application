#  Pipeline Builder Application

A node-based visual pipeline editor built using **ReactFlow (Frontend)** and **FastAPI (Backend)**.

This application enables users to visually construct pipelines by connecting different node types and validates whether the pipeline forms a valid Directed Acyclic Graph (DAG) through backend integration.

---

## ✨ Features

- Reusable **BaseNode abstraction** for scalable node creation
- Custom node types:
  - Input
  - LLM
  - Text
  - Output
- Dynamic Text node with variable detection using `{{variable}}`
- Auto-arrange functionality (Left → Right layout)
- Animated edges for better visual clarity
- Backend integration for pipeline validation
- DAG detection using DFS-based cycle detection
- Clean and responsive UI

---

## 🏗 Architecture Overview

### Frontend
- Built with React and ReactFlow
- Centralized state management using Zustand
- Modular node structure for extensibility
- Visual edge-based data flow representation

### Backend
- Built using FastAPI
- Receives pipeline structure (nodes + edges)
- Constructs adjacency list representation
- Performs cycle detection to validate DAG
- Returns structured response with pipeline metadata

---

## 🛠 Tech Stack

### Frontend
- React
- ReactFlow
- Zustand

### Backend
- Python
- FastAPI

---

## ▶️ How to Run

### Frontend

cd frontend
npm install
npm start

###Backend


cd backend
uvicorn main:app --reload
Backend will run at:


http://127.0.0.1:8000

🔌 Backend Endpoint

POST /pipelines/parse

Returns:

Json


{
  "num_nodes": int,
  
  "num_edges": int,
  
  "is_dag": bool
  
}

👤 Author

Avula Sreekanth
