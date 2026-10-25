ScreenGuide AI
An AI-powered screen-sharing assistant designed to help users understand on-screen tasks through screenshot-based visual guidance.
Overview
ScreenGuide AI combines an AI vision model with a web interface and backend services to provide contextual guidance based on what is visible on the user's screen. The project includes authentication, persistent storage, voice interaction, session history, and a foundation for real-time communication.
Note: The assistant guides the user; it does not autonomously click, type, or submit actions.

Key Features
- AI-powered task planning — creates dynamic task plans using a vision model.
- Screenshot-based visual guidance — analyzes screenshots and provides contextual assistance.
- Screen sharing and continuous analysis — supports ongoing visual assistance.
- Visual pointer guidance — provides pointer-based visual guidance.
- Secure authentication — JWT-based authentication and bcrypt password hashing.
- Database persistence — SQLAlchemy integration with SQLite by default and PostgreSQL-ready configuration.
- Real-time communication foundation — WebSocket transport foundation for agent communication.
- Voice interaction — voice input and speech output.
- Session recording and replay — supports recording and replaying sessions.
- Dashboard and history — includes dashboard, history, and admin/team interface components.
Tech Stack
- Backend: Python, FastAPI
- Database / ORM: SQLite, SQLAlchemy; PostgreSQL-ready via DATABASE_URL
- Authentication: JWT, bcrypt
- Communication: WebSockets
- AI: Vision model for screenshot understanding and task planning
- Frontend: HTML, CSS, JavaScript (based on the project interface)
Project Structure
The expected layout based on the setup instructions is:
ScreenGuide-AI/
├── backend/
│   ├── main.py
│   └── requirements.txt
├── frontend/
│   └── index.html
├── .env.example
├── .gitignore
└── README.md
Your actual folder may contain additional files or directories.
Getting Started
Prerequisites
- Python installed
- Git (for cloning the repository)
- An OpenAI API key for AI features
- A terminal such as PowerShell, Command Prompt, or a VS Code terminal
1. Clone the repository
git clone https://github.com/PrityKumari-png/ScreenGuide-AI.git
cd ScreenGuide-AI
2. Create and activate a virtual environment
Windows (PowerShell):
cd backend
python -m venv .venv
.venv\Scripts\Activate.ps1
If PowerShell blocks activation, use Command Prompt:
.venv\Scripts\activate.bat
Linux / macOS:
cd backend
python3 -m venv .venv
source .venv/bin/activate
3. Install dependencies
Run from the backend directory:
pip install -r requirements.txt
4. Configure environment variables
Set the required environment variables in your terminal. Replace the placeholders with your own values.

Windows PowerShell:
$env:OPENAI_API_KEY="YOUR_OPENAI_API_KEY"
$env:JWT_SECRET="YOUR_RANDOM_SECRET"
Windows Command Prompt:
set OPENAI_API_KEY=YOUR_OPENAI_API_KEY
set JWT_SECRET=YOUR_RANDOM_SECRET
Linux / macOS:
export OPENAI_API_KEY="YOUR_OPENAI_API_KEY"
export JWT_SECRET="YOUR_RANDOM_SECRET"
Keep real credentials private. Do not commit API keys, passwords, or production secrets to GitHub.
5. Start the backend
From the backend directory:
uvicorn main:app --reload
6. Open the frontend
With the backend running, open:
http://127.0.0.1:8000/frontend/index.html
If the page does not load, check the backend logs and confirm that your project's frontend files are served or accessible at this path.
Database Configuration
SQLite is the default database. To use PostgreSQL, configure DATABASE_URL with your PostgreSQL connection string, for example:
postgresql+psycopg2://USER:PASSWORD@HOST:5432/screenguide
Use your own database credentials and keep them out of source control.
Security Notes
- Keep OPENAI_API_KEY on the server side.
- Use a strong, randomly generated JWT_SECRET.
- Do not commit .env files or real credentials.
- Restrict CORS origins before production deployment.
- Use HTTPS in deployed environments; browser screen sharing requires a secure context outside localhost.
- For production, move recordings from browser object URLs to authenticated object storage.
- Review authentication, authorization, and data retention settings before deploying publicly.
Current Scope
The project provides visual guidance and supports the user in carrying out tasks. It is not designed to autonomously click, type, or submit actions on the user's behalf.
Future Improvements
Possible future enhancements include:
- Expanded automated tests and API documentation.
- More granular access controls for team/admin features.
- Secure cloud storage for session recordings.
- Production deployment with HTTPS and restricted CORS.
- Improved error handling and accessibility.
Author
Prity Kumari
- GitHub: PrityKumari-png
- Project repository: ScreenGuide AI