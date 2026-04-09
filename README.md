AI Community Operation Guide

This project is an AI-based HR operations agent that assists employees during the joining process and also supports recruitment by verifying documents.

The system can:

Answer user questions using Retrieval-Augmented Generation (RAG)
Evaluate new member applications using AI scoring
Provide an interactive chat interface using Gradio

All parts of this project are built and tested in a Kaggle notebook environment.

What This System Does

Smart Question Answering
The assistant uses ChromaDB to search and retrieve relevant information from internal PDF documents. It uses Gemini embeddings and LangChain to generate accurate answers.

Application Evaluation
The system reads responses from Google Forms stored in Google Sheets. It evaluates each application using an AI model and provides:

A score
A final decision (approve, review, reject)
A clear explanation

Agent-Based Design
The system is built using LangGraph. It works like a state machine that can decide whether to answer directly or use tools like RAG or scoring.

Interactive Chat Interface
A user-friendly chat interface is created using Gradio. Users can ask questions, trigger tools automatically, and view responses in real time.

Technologies Used

LangGraph
Used to define the workflow and decision-making logic of the AI agent

LangChain and Gemini
Used for handling AI conversations and application evaluation

ChromaDB
Used as a vector database for semantic search

Python Requests
Used to fetch data from Google Sheets

Gradio
Used to build the interactive user interface

PyMuPDF and Unstructured
Used to extract and process content from PDF files

How the System Works

RAG (Retrieval-Augmented Generation)
PDF documents related to the community are divided into smaller parts using different methods:

Fixed-size chunking with overlap
One chunk per document
Semantic chunking using unstructured

These chunks are converted into embeddings using Gemini and stored in ChromaDB.
The tool get_info(query) retrieves relevant information based on user queries.

Application Scoring
The system uses two main tools:

score_application()
check_new_applications()

These tools:

Evaluate single or multiple applications
Generate structured results with score and reasoning
Save results in a CSV file
Display results in a readable format

Agent Workflow
Main components:

chatbot for conversation
tools for executing tasks
score_node for evaluation
human for user input

Flow:
User input goes to chatbot
If a tool is needed, it is executed
The result is returned to the chatbot
The process stops when the user types quit or q

Running the Project

The entire system runs inside a Kaggle notebook. It includes:

Step-by-step explanation
AI agent logic
RAG setup
Interactive interface

You can copy the notebook and run it directly without complex setup.

Example Questions

What is the mission of this community
Can you check and score new applications
How can I contribute
Can you evaluate this application

Project Structure

.
ai-agent-community-assistant.ipynb Main notebook
community-docs/ PDF files
scored_applications.csv Output results
README.md Documentation

Project Results

Built a complete AI-based onboarding assistant
Learned how to use RAG, embeddings, and vector databases
Gained experience in prompt engineering and agent workflows
Created a working interactive AI application

Future Improvements

Add more tools and features
Improve application scoring criteria
Enhance user interface with more options
Add feedback system for better learning

Author

Sarthak Mohanty
LinkedIn
www.linkedin.com/in/mohantysarthak98
