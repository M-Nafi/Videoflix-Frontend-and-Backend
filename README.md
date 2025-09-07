<h1 align="center">Videoflix – Full-Stack Streaming Platform</h1>

<p align="center">
Videoflix is a full-stack video streaming application, combining a modern <strong>Angular 19</strong> frontend with a robust <strong>Django REST Framework</strong> backend.  
It provides user authentication, video management, and adaptive HLS streaming.
</p>

---

<p align="center">
This project was developed collaboratively by three team members:  
<p align="center">
<a href="https://github.com/MarcoAngermann">Marco Angermann</a>, <a href="https://github.com/MarioWinter">Mario Winter</a>, and myself
<a href="https://github.com/M-Nafi">Nafi</a>.  
<p align="center">
Although each of us maintained our own individual repositories, we worked closely together throughout the development process.  
All three of us contributed to both the frontend and backend, using tools such as **Visual Studio Code Live Share** to enable real-time collaboration and pair programming.
</p>
</p>
</p>
</p>

---

<p align="center">
  <img src="https://img.shields.io/badge/Frontend-Angular%2019-red?style=for-the-badge&logo=angular&logoColor=white">
  <img src="https://img.shields.io/badge/Backend-Django%20DRF-green?style=for-the-badge&logo=django&logoColor=white">
  <img src="https://img.shields.io/badge/Database-PostgreSQL-blueviolet?style=for-the-badge&logo=postgresql&logoColor=white">
  <img src="https://img.shields.io/badge/Task%20Queue-Redis%20%2F%20Django%20RQ-orange?style=for-the-badge&logo=redis&logoColor=white">
  <img src="https://img.shields.io/badge/Streaming-HLS-red?style=for-the-badge">
  <img src="https://img.shields.io/badge/Docker-Enabled-lightgrey?style=for-the-badge&logo=docker&logoColor=white">
</p>

---

<h2 align="center">Repositories</h2>

<table align="center">
  <tr>
    <th>Section</th>
    <th>Technologies</th>
    <th>Link</th>
  </tr>
  <tr>
    <td>Frontend</td>
    <td>Angular 19, TypeScript, SCSS</td>
    <td><a href="https://github.com/M-Nafi/Videoflix-Angular">Videoflix-Angular</a></td>
  </tr>
  <tr>
    <td>Backend</td>
    <td>Django REST Framework, PostgreSQL, Redis/Django RQ, Docker</td>
    <td><a href="https://github.com/M-Nafi/Videoflix-Django">Videoflix-Django</a></td>
  </tr>
</table>

---

<h2 align="center">Architecture</h2>

<p align="center">
<code>[Angular Frontend]</code> → <code>[Django REST API]</code> → <code>[PostgreSQL Database]</code><br>
<code>Video Upload</code> → <code>Background Transcoding (Redis + Django RQ)</code> → <code>HLS Streaming</code>
</p>

---

<h2 align="center">Features</h2>

Frontend (Angular 19)
- Responsive UI with Angular components  
- TypeScript & SCSS styling  
- Integration with Django API  

Backend (Django DRF)
- User registration with email activation  
- JWT authentication (login, logout, refresh)  
- Password reset with email confirmation  
- Video upload & automatic HLS transcoding (480p, 720p, 1080p)  
- RESTful API endpoints for videos and users  
- Dockerized environment for easy setup  

---

<h2 align="center">Installation & Setup</h2>

### Clone Repositories

```bash
# Frontend
git clone https://github.com/M-Nafi/Videoflix-Angular.git

# Frontend Setup
cd Videoflix-Angular
npm install
ng serve


# Backend
git clone https://github.com/M-Nafi/Videoflix-Django.git

# Backend Setup
cd Videoflix-Django
python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows
pip install -r requirements.txt

# Create a .env file:
SECRET_KEY=your_secret_key
DEBUG=True
DATABASE_URL=postgres://user:pass@localhost:5432/videoflix
REDIS_URL=redis://localhost:6379/0

# Apply migrations:
python manage.py migrate
python manage.py createsuperuser  # optional

# Docker (Optional):
docker-compose up --build

