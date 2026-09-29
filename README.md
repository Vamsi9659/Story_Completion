# 📖 AI Story Completion & Analysis Platform

An AI-powered full-stack web application that helps students generate and analyze stories through an interactive platform. The application provides student authentication, story prompts, story submission, and machine-learning-based analysis and summarization.

The project is built using **React + Vite** for the frontend, **FastAPI** for the backend, **MongoDB** for data storage, and **Facebook mBART** for multilingual story analysis and generation-related NLP tasks.

---
## 🌐 Live Demo

- **Frontend:** https://story-completion-xd2n.vercel.app/
- **Backend API:** https://story-completion.onrender.com
- **API Documentation:** https://story-completion.onrender.com/docs
---

## ✨ Features

### 👨‍🎓 Student Features

* Student registration
* Student login
* Secure password hashing
* Story prompt retrieval
* Interactive story completion
* Story submission
* AI/ML-based story analysis
* Generated story summary
* Responsive user interface
* Error handling and validation

### 👨‍🏫 Teacher Features

* Teacher authentication
* Teacher login
* Teacher-side access to the application functionality
* Backend-supported teacher authentication flow

### 🤖 AI / NLP Features

* Natural Language Processing
* Story classification
* Story summarization
* AI-assisted story analysis
* Facebook **mBART** model integration
* Multilingual NLP capability

### 🔐 Security Features

* Password hashing using bcrypt
* Password verification during login
* Pydantic request validation
* Email validation
* CORS configuration
* Authentication-based API endpoints
* Environment-based configuration for sensitive values

---

# 🏗️ System Architecture

```text
                    ┌─────────────────────┐
                    │       User          │
                    │  Student / Teacher  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   React + Vite      │
                    │     Frontend        │
                    └──────────┬──────────┘
                               │
                         HTTP / REST API
                               │
                               ▼
                    ┌─────────────────────┐
                    │   FastAPI Backend   │
                    │      Python         │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
              ▼                ▼                ▼
       ┌────────────┐   ┌─────────────┐  ┌──────────────┐
       │ MongoDB    │   │ Authentication│  │ NLP / ML     │
       │ Database   │   │   & Security │  │ Processing    │
       └────────────┘   └─────────────┘  └──────┬───────┘
                                                 │
                                                 ▼
                                        ┌────────────────┐
                                        │ Facebook mBART │
                                        └────────────────┘
```

---

# 🛠️ Technology Stack

## Frontend

| Technology | Purpose               |
| ---------- | --------------------- |
| React.js   | User interface        |
| Vite       | Frontend build tool   |
| JavaScript | Application logic     |
| HTML5      | Structure             |
| CSS3       | Styling               |
| Fetch API  | Backend communication |

## Backend

| Technology | Purpose                 |
| ---------- | ----------------------- |
| Python     | Backend programming     |
| FastAPI    | REST API framework      |
| Uvicorn    | ASGI server             |
| Pydantic   | Data validation         |
| Passlib    | Password hashing        |
| bcrypt     | Secure password hashing |

## Database

| Technology | Purpose                   |
| ---------- | ------------------------- |
| MongoDB    | NoSQL database            |
| PyMongo    | Python-MongoDB connection |

## AI / Machine Learning

| Technology         | Purpose                            |
| ------------------ | ---------------------------------- |
| Facebook mBART     | NLP / multilingual text processing |
| NLP techniques     | Story analysis                     |
| Text summarization | Story summary generation           |
| Classification     | Story analysis/classification      |

## Development Tools

* Visual Studio Code
* Git
* GitHub
* Postman / Swagger UI
* MongoDB
* Chrome / Edge

## Deployment

* Vercel — Frontend
* Render — Backend
* MongoDB Atlas — Database

---

# 📂 Project Structure

```text
Story_Completion/
│
├── backend/
│   │
│   ├── main.py
│   ├── auth.py
│   ├── database.py
│   ├── models.py
│   ├── ml_analysis.py
│   ├── requirements.txt
│   │
│   └── ...
│
├── frontend/
│   │
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── App.jsx
│   │   └── ...
│   │
│   ├── package.json
│   ├── vite.config.js
│   └── ...
│
├── .gitignore
└── README.md
```

> Folder names may vary slightly depending on the current frontend component structure.

---

# 🔄 Application Workflow

## 1. Student Registration

```text
Student
   ↓
Registration Form
   ↓
React Frontend
   ↓
POST /student/register
   ↓
FastAPI
   ↓
Pydantic Validation
   ↓
Password Hashing
   ↓
MongoDB
   ↓
Registration Response
   ↓
Frontend
```

## 2. Student Login

```text
Student
   ↓
Login Form
   ↓
POST /student/login
   ↓
FastAPI
   ↓
Find Student in MongoDB
   ↓
Verify Password
   ↓
Authentication Response
   ↓
Frontend
```

## 3. Story Generation / Analysis

```text
Student
   ↓
Story Prompt
   ↓
Story Input
   ↓
FastAPI
   ↓
ML / NLP Processing
   ↓
Facebook mBART
   ↓
Classification / Summary
   ↓
Result
   ↓
React Frontend
```

---

# 🔌 API Documentation

The backend provides REST APIs through FastAPI.

When the backend is running locally:

```text
http://127.0.0.1:8000/docs
```

FastAPI automatically provides an interactive **Swagger UI** where API endpoints can be tested.

---

## 📌 API Endpoints

### Student Registration

```http
POST /student/register
```

Registers a new student.

Example request:

```json
{
  "name": "John",
  "email": "john@example.com",
  "password": "password123"
}
```

---

### Student Login

```http
POST /student/login
```

Authenticates a registered student.

Example request:

```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

---

### Get Story Prompt

```http
GET /story/prompt
```

Returns a story prompt that can be used by the student to create a story.

---

# 🧠 Machine Learning Module

The project contains an ML/NLP processing module responsible for analyzing user-provided story content.

The major processing flow is:

```text
User Story
    ↓
Text Processing
    ↓
NLP Model
    ↓
Classification
    ↓
Summary Generation
    ↓
Final Result
```

The project uses the **Facebook mBART model** for multilingual sequence-to-sequence NLP processing.

The ML-related functionality is organized inside:

```text
backend/ml_analysis.py
```

The module is designed to separate AI/NLP processing from the main FastAPI application logic.

---

# 🔐 Authentication & Security

The application does not store plain-text passwords.

Instead:

```text
User Password
      ↓
bcrypt hashing
      ↓
Hashed Password
      ↓
MongoDB
```

During login:

```text
Entered Password
      ↓
Password Verification
      ↓
Stored Hash
      ↓
Authentication Result
```

Additional validation is handled using Pydantic models.

Email fields are validated before registration/login processing.

---

# 🗄️ Database

The application uses **MongoDB** as its NoSQL database.

The backend communicates with MongoDB through **PyMongo**.

Conceptually:

```text
FastAPI
   │
   ▼
PyMongo
   │
   ▼
MongoDB
   │
   ├── Student Data
   ├── Teacher Data
   └── Story Data
```

For production deployment, MongoDB Atlas can be used instead of a local MongoDB instance.

---

# ⚙️ Local Installation

## Prerequisites

Make sure the following are installed:

* Python 3.11+
* Node.js
* npm
* Git
* MongoDB / MongoDB Atlas
* Visual Studio Code

---

# 📥 Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

Move into the project:

```bash
cd Story_Completion
```

---

# 🐍 Backend Setup

Open a terminal:

```powershell
cd backend
```

Create a virtual environment:

```powershell
python -m venv venv
```

Activate it on Windows:

```powershell
.\venv\Scripts\Activate.ps1
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

If PowerShell blocks activation, you can alternatively run the backend using the Python environment where the dependencies are installed.

---

# ▶️ Start Backend

Inside the `backend` directory:

```powershell
python -m uvicorn main:app --reload
```

Backend will run at:

```text
http://127.0.0.1:8000
```

Swagger documentation:

```text
http://127.0.0.1:8000/docs
```

---

# ⚛️ Frontend Setup

Open a **second terminal**.

Move into frontend:

```powershell
cd frontend
```

Install dependencies:

```powershell
npm install
```

Start the development server:

```powershell
npm run dev
```

The frontend will normally run at:

```text
http://localhost:5173
```

---

# 🔗 Frontend ↔ Backend Connection

During local development:

```text
React
http://localhost:5173
       │
       │ API Requests
       ▼
FastAPI
http://127.0.0.1:8000
       │
       ▼
MongoDB
```

For production deployment, the frontend API base URL should point to the deployed Render backend instead of localhost.

Example:

```text
Local:
http://127.0.0.1:8000

Production:
https://your-backend.onrender.com
```

---

# 🌐 Production Deployment

## Frontend — Vercel

The React/Vite frontend can be deployed using Vercel.

Typical configuration:

```text
Framework:
Vite

Root Directory:
frontend

Build Command:
npm run build

Output Directory:
dist
```

After deployment:

```text
User
 ↓
Vercel
 ↓
React Application
```

---

## Backend — Render

The FastAPI backend can be deployed using Render.

Typical configuration:

```text
Root Directory:
backend

Build Command:
pip install -r requirements.txt

Start Command:
uvicorn main:app --host 0.0.0.0 --port $PORT
```

Production architecture:

```text
Vercel
   │
   ▼
React Frontend
   │
   ▼
Render
   │
   ▼
FastAPI
   │
   ▼
MongoDB Atlas
```

---

# 🔑 Environment Variables

Sensitive information should not be hardcoded into the source code.

Example:

```env
MONGODB_URI=your_mongodb_connection_string
DATABASE_NAME=your_database_name
```

For frontend production configuration, use an environment variable such as:

```env
VITE_API_URL=https://your-backend.onrender.com
```

Never commit sensitive `.env` files to GitHub.

Add them to `.gitignore`:

```gitignore
.env
.env.local
```

---

# 🧪 Testing

## Backend Health Check

Open:

```text
http://127.0.0.1:8000/docs
```

If Swagger UI loads successfully, the FastAPI application is running.

## API Testing

The APIs can be tested using:

* Swagger UI
* Postman
* Frontend application

Important endpoints:

```text
GET  /story/prompt
POST /student/register
POST /student/login
```

---

# 🐛 Error Handling

The application includes validation and error handling for scenarios such as:

* Invalid email format
* Missing required fields
* Incorrect login credentials
* Duplicate student registration
* Invalid request payloads
* Database-related errors
* Backend API failures

The frontend handles API responses and displays appropriate feedback to the user.

---

# 📊 Key Technical Concepts Demonstrated

This project demonstrates practical knowledge of:

* Full-stack web development
* REST API development
* React component architecture
* FastAPI backend development
* MongoDB database integration
* CRUD operations
* Authentication
* Password hashing
* Pydantic validation
* CORS
* API integration
* NLP
* Machine Learning
* Text classification
* Text summarization
* Transformer-based models
* Git/GitHub
* Cloud deployment
* Vercel
* Render
* MongoDB Atlas

---

# 💡 Why This Project?

Traditional story-writing applications generally focus only on text input.

This project combines:

```text
Web Development
       +
Authentication
       +
Database
       +
Natural Language Processing
       +
Machine Learning
       +
Cloud Deployment
```

This makes the application a practical example of integrating **AI/ML capabilities into a modern full-stack web application**.

---

# 🔮 Future Enhancements

Potential future improvements include:

* JWT-based authentication
* Role-based access control
* Student dashboard
* Teacher dashboard
* Story history
* Story evaluation scores
* Advanced grammar analysis
* Sentiment analysis
* More multilingual models
* AI-generated story continuation
* Improved NLP pipelines
* Real-time feedback
* User profile management
* Analytics dashboard
* Docker containerization
* CI/CD pipeline
* Automated testing
* Production monitoring

---

# 📸 Screenshots

Add project screenshots here:

```markdown
## 📸 Screenshots

### Home Page
![Home Page](screenshots/home.png)

### Student Registration
![Registration](screenshots/register.png)

### Student Login
![Login](screenshots/login.png)

### Story Interface
![Story](screenshots/story.png)

### AI Analysis
![AI Analysis](screenshots/analysis.png)
```

Recommended folder:

```text
screenshots/
├── home.png
├── register.png
├── login.png
├── story.png
└── analysis.png
```

---

# 🧑‍💻 Development

To contribute or modify the project:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd Story_Completion
```

Create a new branch:

```bash
git checkout -b feature/new-feature
```

After making changes:

```bash
git add .
git commit -m "Add new feature"
git push origin feature/new-feature
```

---

# 📜 Git Workflow

Recommended workflow:

```text
Modify Code
    ↓
Test Locally
    ↓
git status
    ↓
git add .
    ↓
git commit
    ↓
git push
    ↓
GitHub
    ↓
Deployment
```

---

# 🏆 Project Highlights

### Full-Stack Development

Built an end-to-end web application using React, FastAPI, and MongoDB.

### AI Integration

Integrated NLP/ML processing using the Facebook mBART model.

### Secure Authentication

Implemented student and teacher authentication with password hashing and validation.

### REST API

Designed backend APIs using FastAPI and exposed interactive Swagger documentation.

### Cloud Ready

Structured the application for frontend and backend deployment using Vercel and Render.

### Database Integration

Connected the backend with MongoDB for persistent application data.

---

# 👨‍💻 Author

**Vamsi Lalam**

B.Tech Graduate | Python Full Stack Developer | AI/ML Enthusiast

### Connect With Me

* GitHub: `https://github.com/Vamsi9659`
* LinkedIn: `Add your LinkedIn URL`
* Portfolio: `Add your portfolio URL`

---

# ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is developed for educational and portfolio purposes.

Add an appropriate open-source license if you plan to distribute or reuse the project publicly.
