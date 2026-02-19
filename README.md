# 💼 AI Career Coaching Assistant with LangGraph + Gemini

An interactive, intelligent career QA agent built using LangGraph, Google Gemini 1.5 Flash and Streamlit.  
It provides career guidance, resume audits, profile enhancement, and job-fit analysis — all via natural conversations.

Now includes a minimal LangGraph agent that drafts a 30-60-90 day career plan, pauses for human review (interrupt), and resumes to finalize. Sessions/runs/checkpoints are persisted in MongoDB.

---

## 🚀 Setup & Installation

### Prerequisites
- Python 3.8+
- MongoDB (optional, for session persistence)

### MongoDB Setup (Optional)
For session persistence across restarts:

1. **Install MongoDB:**
   ```bash
   # Ubuntu/Debian
   sudo apt-get install mongodb
   
   # macOS
   brew install mongodb-community
   
   # Windows: Download from https://www.mongodb.com/try/download/community
   ```

2. **Start MongoDB:**
   ```bash
   # Ubuntu/Debian
   sudo systemctl start mongodb
   
   # macOS
   brew services start mongodb-community
   
   # Windows: Start MongoDB service
   ```

3. **Set Environment Variables:**
   ```bash
   # .env file
   MONGODB_URI=mongodb://localhost:27017
   MONGODB_DB=career_bot
   MONGODB_COLLECTION=sessions
   ```

4. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

### Run the Application
```bash
cd linkedin
streamlit run app.py
```

## ✨ Features

### 🤖 AI Career Assistant
- **Profile Analysis**: Get insights on your LinkedIn profile
- **Job Fit Analysis**: Compare your profile with job descriptions
- **Profile Enhancement**: Get suggestions to improve your profile
- **General Career Q&A**: Ask any career-related questions

### 📝 Career Plan Generator with Human Review
- **Minimal Input**: Just describe your career goal briefly
- **AI Generation**: Get detailed 30-60-90 day career plans
- **Human Review**: Interrupt the process to provide feedback
- **Resume & Refine**: Continue with your changes applied
- **Session Persistence**: Save and load your career planning sessions

### 💾 Session Management
- **MongoDB Persistence**: Sessions are saved to MongoDB (with fallback to memory)
- **Load Previous Sessions**: Continue where you left off
- **Request Review Button**: Manually trigger review process
- **Cross-Restart Persistence**: Your sessions survive app restarts

## 🔄 Career Plan Flow

1. **Generate Plan**: Provide brief career goal → Get detailed plan
2. **Interrupt**: Process pauses for human review
3. **Provide Feedback**: Suggest changes (timeline, role, etc.)
4. **Resume**: AI applies your feedback and generates revised plan
5. **Persist**: Session is saved for future use
