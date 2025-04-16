# Rust To-Do

A fullstack to-do list application built with **Rust** as the backend and **Next.js** as the frontend, containerized with Docker and orchestrated using `docker-compose`.



## 🎯 Purpose

This project is intended as a practical exploration of building and running a fullstack web application using modern technologies. The main goals are:

- Practicing containerized development with Docker
- Structuring a fullstack project with frontend and backend services
- Using Rust in web backend development
- Leveraging Next.js for a responsive frontend
- Managing multi-service apps with `docker-compose`



## 🧰 Technologies Used

- **Actix-web** - for the backend API
- **Next.js** — React-based frontend framework
- **Docker** — for containerization
- **Docker Compose** — for service orchestration



## 📁 Project Structure

```bash
Rust-To-Do/
├── docker-compose.yml        # Runs both frontend and backend│
│
├── rust/                     # Rust backend
│   └── Dockerfile
│
└── frontend/                 # Next.js frontend
    └── Dockerfile
```



## 🚀 Running the Project

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Rust-To-Do.git
cd Rust-To-Do
```

### 2. Build and Start the App

Make sure you have **Docker** and **Docker Compose** installed.

Then run:

```bash
docker-compose up --build
```

This will build and start both the backend and frontend services.

### 3. Access the App

- Frontend: [http://localhost:3000](http://localhost:3000)  
- Backend API: [http://localhost:8080](http://localhost:8080)

---

### ✅ Notes

- The frontend connects to the backend using the `NEXT_PUBLIC_API_URL` environment variable defined in `docker-compose.yml`.
- No need for a `.env.local` file when using Docker.
- If you want to run the frontend without Docker, create a `.env.local` inside `frontend/` with this content:

```env
NEXT_PUBLIC_API_URL=http://localhost:8080
```

## 🧪 API & Features

- Basic CRUD for todo items
- Communication between frontend and backend over REST API
- JSON-based request/response
- Dynamic UI updates in the frontend


## 🙏 Acknowledgements

This project was initially based on the [Full-Stack Rust To-Do App Starter File](https://github.com/daulathussain/Full-Stack-Rust-To-Do-App-Starter-File) by [@daulathussain](https://github.com/daulathussain).  
It has been extended and modified for learning and experimentation purposes.




## 🧼 License

MIT — feel free to use, fork, and build upon this project.


