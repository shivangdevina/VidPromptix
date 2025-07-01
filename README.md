VidPromptix
VidPromptix is a web application that allows users to interact with an AI-powered chatbot capable of answering questions based on YouTube video transcripts. The application uses React for the frontend, Node.js with Express for the backend, and integrates with LangChain and Anthropic's Claude model for natural language processing. It also leverages Bright Data for YouTube video scraping and a vector store for efficient transcript retrieval.
Features

Chat Interface: A modern, responsive chat UI built with React and TypeScript.
YouTube Transcript Analysis: Fetches and processes YouTube video transcripts to answer user queries.
AI-Powered Responses: Uses Anthropic's Claude model via LangChain to generate accurate and context-aware responses.
Vector Store Integration: Stores and retrieves transcript chunks using a PostgreSQL-based vector store for efficient similarity search.
Bright Data Integration: Triggers YouTube video scraping to fetch transcripts dynamically.

Tech Stack

Frontend:
React with TypeScript
Tailwind CSS (via CDN)
Vite for build and development


Backend:
Node.js with Express
LangChain for AI agent creation
Anthropic's Claude model for natural language processing
PostgreSQL with PGVector for vector storage
OpenAI Embeddings for text embedding
Bright Data API for YouTube video scraping


Deployment:
Genezio for deploying backend and frontend
Environment variables for configuration



Prerequisites
Before you begin, ensure you have the following installed:

Node.js (v18 or higher)
npm (v9 or higher)
PostgreSQL (with PGVector extension)
Genezio CLI (npm install -g genezio)
Accounts and API keys for:
Anthropic (for Claude model)
OpenAI (for embeddings)
Bright Data (for YouTube scraping)
PostgreSQL database connection string



Setup Instructions

Clone the Repository
git clone <repository-url>
cd VidPromptix


Install Dependencies

For the backend (in the server directory):cd server
npm install


For the frontend (in the client directory):cd client
npm install




Configure Environment Variables
Create a .env file in the server directory with the following variables:
PORT=3000
DB_URL=<your-postgresql-connection-string>
BRIGHTDATA_API_KEY=<your-brightdata-api-key>
ANTHROPIC_API_KEY=<your-anthropic-api-key>
OPENAI_API_KEY=<your-openai-api-key>
API_URL=<your-backend-api-url>

Create a .env file in the client directory with:
VITE_API_URL=<your-backend-api-url>


Database Setup
Ensure your PostgreSQL database is running and has the PGVector extension installed. The backend will automatically create the necessary tables (transcripts) when initialized.

Run the Application Locally

Start the backend:cd server
npm start


Start the frontend:cd client
npm run dev



The frontend will be available at http://localhost:5173, and the backend will run on http://localhost:3000 (or the port specified in your .env file).

Deploy with Genezio
Ensure the genezio.yaml file is configured correctly. Then, deploy both backend and frontend:
genezio deploy

This will deploy the backend to Genezio's serverless infrastructure and the frontend to the specified dist directory.


Usage

Open the application in your browser.
Enter a YouTube video URL or a query about a video in the chat input.
The AI will either retrieve information from the vector store (if the transcript is already stored) or trigger a scrape via Bright Data to fetch the transcript and process it.
View the AI's response in the chat interface.
Use the "New Chat" button to reset the conversation.

Example Query
What will people learn from this video? (https://www.youtube.com/watch?v=Pxn276cWKeI)

The AI will fetch the transcript (if not already stored), analyze it, and respond with relevant information, such as:

This video teaches how to build an Apple-style Invite App using React Native and Reanimated 4. It covers creating a beautiful UI with blur effects, smooth animations, gesture handling, and navigation transitions. You'll learn about Expo for cross-platform development, CSS animations, and best practices for React Native projects.

Project Structure
VidPromptix/
├── client/                   # Frontend code
│   ├── src/
│   │   ├── App.tsx          # Main React component
│   │   ├── index.css        # Global styles
│   │   ├── main.tsx         # Entry point for React
│   └── vite.config.ts       # Vite configuration
├── server/                   # Backend code
│   ├── index.js             # Express server
│   ├── agent.js             # LangChain agent configuration
│   ├── embeddings.js        # Vector store and embedding logic
│   ├── brightdata.js        # Bright Data API integration
│   ├── data.js              # Sample YouTube video data
│   └── package.json         # Backend dependencies
├── genezio.yaml             # Genezio deployment configuration
└── README.md                # This file

Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Make your changes and commit (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgments

LangChain for AI agent and vector store functionality
Anthropic for Claude model
Bright Data for YouTube scraping
React Native and Reanimated for frontend inspiration
Genezio for deployment
