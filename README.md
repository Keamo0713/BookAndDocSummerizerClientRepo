LumiReads Backend
The backend of the LumiReads web application, built with FastAPI, is responsible for handling API requests from the frontend to search for books, generate text summaries, and create audio versions of book content. It leverages several powerful APIs to provide this functionality.

💻 Technologies & APIs
FastAPI: A modern, fast (high-performance) web framework for building APIs with Python 3.7+.

Python 3.8+: The programming language used to build the backend.

Google Gemini API: Used for generating intelligent and concise summaries of book descriptions or uploaded documents.

ElevenLabs API: Powers the text-to-speech functionality, converting summaries into audio.

OpenLibrary API: The external API used by the frontend to search for books.

✨ Features
Content Generation: Generates text summaries and audio from book descriptions or uploaded documents (PDF/text).

Multilingual Support: Supports text summarization and audio generation in multiple languages, including English, French, Spanish, Afrikaans, and Zulu.

File Handling: Processes uploaded PDF and text files for summarization and audio creation.

File Downloads: Enables the download of generated summaries as .txt files and audio as .mp3 files.

📂 Project Structure
LumiReads/
└── server/ # FastAPI backend
    ├── main.py        # Main FastAPI application
    ├── requirements.txt # Python dependencies
    ├── .env           # Environment variables (for local use)
    └── ...

🛠️ Prerequisites
Python (3.8 or higher)

pip (included with Python)

Git

API keys for:

Google Gemini API

ElevenLabs API

🚀 Setup & Installation
Clone the Repository
git clone https://github.com/Keamo0713/BookAndDocSummerizerClientRepo.git
cd LumiReads/server

Create a Virtual Environment
It is recommended to use a virtual environment to manage dependencies.

On Windows (PowerShell):

python -m venv venv
.\venv\Scripts\Activate.ps1

On Linux/Mac:

python3 -m venv venv
source venv/bin/activate

Install Dependencies
pip install -r requirements.txt

Configure API Keys
For local development, create a .env file in the server/ directory and add your API keys:

GEMINI_API_KEY=your_gemini_api_key
ELEVENLABS_API_KEY=your_elevenlabs_api_key

Note: For deployment on Render, you will set these as environment variables in the Render dashboard, not in this file.

▶️ Running Locally
Make sure your virtual environment is active.

Navigate to the server/ directory.

Start the FastAPI server:

uvicorn main:app --reload

The backend server will be running at http://localhost:8000.

☁️ Deployment on Render
This project is configured for deployment on Render using a render.yaml file located in the repository's root.

Push to GitHub: Ensure your changes are committed and pushed to your GitHub repository.

Create a Blueprint: In the Render dashboard, create a new Blueprint and connect it to your GitHub repository.

Set Environment Variables: In the Render dashboard, navigate to your backend service and set the following environment variables:

GEMINI_API_KEY: Your Gemini API key.

ELEVENLABS_API_KEY: Your ElevenLabs API key.

Deploy: Render will automatically build and deploy your services based on the render.yaml file.

⚠️ Troubleshooting
Service Root Directory Missing: If you encounter an error during Render deployment, ensure that the root directory for your backend service is correctly set to server.

API Key Errors: Verify that your API keys are correctly set in the Render Dashboard environment variables. You can test the backend's health with a simple curl command.

CORS Issues: If the frontend is unable to connect to the backend, check that the CORS policy in main.py is configured to allow requests from your frontend URL.

🔒 Security Notes
API Keys: Never commit your API keys directly to the repository. Use .env for local development and set environment variables securely in your production environment (like Render's Dashboard).

Add .env to your .gitignore file to prevent it from being pushed.

🤝 Contributing
Contributions are welcome! Please follow the steps in the main README.md for the project.

📞 Contact
Project Link: https://github.com/Keamo0713/BookAndDocSummerizerClientRepo
