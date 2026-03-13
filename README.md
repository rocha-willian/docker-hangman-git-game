<p align="center">
<img src="assets/images/unicast_logo.png">
</p>

# Docker Hangman Git Game 

**A containerized hangman game to learn Git, GitHub, and DevOps terminology through interactive gameplay**
Teste
This educational game combines the classic hangman experience with essential development concepts, making it perfect for students, bootcamps, and anyone looking to master Git and GitHub vocabulary in a fun way.

> **A fun hangman game to learn Git and GitHub terms!**

Discover words related to Git, GitHub, and DevOps while having fun playing!

## 🎯 How to Play

1. **Objective**: Guess the secret word related to Git/GitHub
2. **Letters**: Click on alphabet letters to make your guesses
3. **Lives**: You have 6 wrong attempts before losing the game
4. **Victory**: Guess all letters correctly to win!

## 🎓 Game Words

### Git Basics
- **commit**, **push**, **pull**, **clone**, **branch**, **merge**

### GitHub Features  
- **repository**, **fork**, **issue**, **action**, **workflow**, **release**

### DevOps Terms
- **docker**, **pipeline**, **deploy**, **cloud**, **container**

## 🚀 Quick Start

### 📋 Prerequisites
- [Docker](https://www.docker.com/get-started) installed
- [Docker Compose](https://docs.docker.com/compose/install/) installed

### 🏃‍♂️ Run the Game

```bash
# 1. Clone this repository
git clone https://github.com/YOUR-USERNAME/docker-git-game-hangman.git
cd docker-git-game-hangman

# 2. Run with Docker Compose
docker-compose up -d

# 3. Wait a few seconds and access
open http://localhost:3000
```

### 🛑 Stop the Game

```bash
# Stop all containers
docker-compose down

# Stop and remove volumes (deletes database data)
docker-compose down -v
```

## 🏗️ Architecture

```
🎮 Frontend (React)  ←→  ⚡ Backend (Python)  ←→  💾 Database (PostgreSQL)
    localhost:3000        localhost:8000          localhost:5432
```

## 🛠️ Development

### 🐳 With Docker (Recommended)
```bash
# Run in development mode
docker-compose up

# Watch logs in real-time
docker-compose logs -f

# Rebuild after changes
docker-compose up --build
```

### 💻 Local Development

#### Backend (FastAPI)
```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

#### Frontend (React + Vite)
```bash
cd frontend
npm install
npm run dev
```

#### Database (PostgreSQL)
```bash
docker run -d \
  --name postgres \
  -p 5432:5432 \
  -e POSTGRES_DB=gitgame \
  -e POSTGRES_USER=gitgame \
  -e POSTGRES_PASSWORD=gitgame123 \
  postgres:15
```

## 📁 Project Structure

```
docker-git-game-hangman/
├── 🎮 frontend/           # Game interface (React + TailwindCSS)
│   ├── src/
│   │   ├── components/    # Game components
│   │   └── App.jsx       # Main component
│   ├── Dockerfile        # Production container
│   └── package.json      # Node.js dependencies
│
├── ⚡ backend/            # Game API (FastAPI + Python)
│   ├── main.py           # API server
│   ├── Dockerfile        # Production container  
│   └── requirements.txt  # Python dependencies
│
├── 💾 db/                 # Database (PostgreSQL)
│   ├── init.sql          # Initial database structure
│   └── Dockerfile        # Custom container
│
├── 🐳 docker-compose.yml  # Container orchestration
├── 📋 README.md          # This file
└── 🔧 .env.example       # Configuration examples
```

## 🎨 Technologies Used

### Frontend
- **React 18** - User interface
- **TailwindCSS** - Modern styling
- **Vite** - Fast build tool
- **Nginx** - Web server

### Backend  
- **FastAPI** - Modern Python web framework
- **SQLAlchemy** - Database ORM
- **PostgreSQL** - Relational database
- **Python 3.11** - Programming language

### DevOps
- **Docker** - Containerization
- **Docker Compose** - Local orchestration

## 🎯 Features

- ✅ Complete hangman game
- ✅ Life counter (6 wrong attempts)
- ✅ Responsive interface (mobile-friendly)
- ✅ Modern cyberpunk theme
- ✅ Data persistence
- ✅ Documented RESTful API
- ✅ Automatic health checks

## 📖 API Endpoints

### Game
- `GET /api/game/new` - Start new game
- `POST /api/game/guess` - Make letter guess
- `GET /api/game/status` - Current game status

### System
- `GET /health` - Application health check
- `GET /docs` - Automatic API documentation (Swagger)

## 🔧 Configuration

### Environment Variables

Copy `.env.example` to `.env` and adjust as needed:

```bash
# Database
POSTGRES_DB=gitgame
POSTGRES_USER=gitgame  
POSTGRES_PASSWORD=gitgame123

# Backend
DATABASE_URL=postgresql://gitgame:gitgame123@database:5432/gitgame
FRONTEND_URL=http://localhost:3000

# Frontend
VITE_API_URL=http://localhost:8000
```

## ❓ Common Issues

### 🐳 Docker won't start
```bash
# Check if Docker is running
docker --version
docker ps

# Clean old containers
docker-compose down -v
docker system prune -f
```

### 🌐 Application won't load
```bash
# Check logs
docker-compose logs

# Check if ports are free
lsof -i :3000,8000,5432
```

### 💾 Database issues
```bash
# Reset database
docker-compose down -v
docker-compose up -d database
# Wait 30 seconds
docker-compose up -d
```

## 🤝 How to Contribute

1. 🍴 Fork the project
2. 🌿 Create a feature branch (`git checkout -b feature/new-feature`)
3. 📝 Commit your changes (`git commit -m 'Add new feature'`)
4. 📤 Push to the branch (`git push origin feature/new-feature`)
5. 🔄 Open a Pull Request

## 🎉 Have Fun!

<p align='center'>
  Do you like my open source projects? <a href='https://stars.github.com/nominate/'>Nominate me to Github Stars ⭐</a>
</p>

## :memo: License

This project is under [MIT License](./LICENSE).
