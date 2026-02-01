# Nephro-Platform

Nephrology management platform developed with Angular (frontend), Spring Boot (backend), and MySQL (database), containerized with Docker.

---

## Project Structure

```
nephro-platform/
├── backend/         # Spring Boot
├── frontend/        # Angular
├── docker-compose.yml
└── README.md
```

---

## Prerequisites

* Docker + Docker Compose
* Node.js (optional for running Angular locally)
* Java 17 JDK (optional for running backend locally)

---

## Run the Project with Docker

From the root folder of the project:

```bash
docker compose up --build
```

* Backend: [http://localhost:8080](http://localhost:8080)
* Frontend: [http://localhost:4200](http://localhost:4200)

To stop:

```bash
docker compose down
```

---

## Angular API Configuration

The Angular frontend uses `environment.ts` to set the backend URL:

```ts
// frontend/src/environments/environment.ts
export const environment = {
  production: false,
  apiUrl: 'http://localhost:8080'
};
```

---

## Run Locally (Optional)

**Angular Frontend:**

```bash
cd frontend
npm install
ng serve
```

**Spring Boot Backend:**

```bash
cd backend
mvn clean package -DskipTests
java -jar target/*.jar
```

---

## Notes

* `.gitignore` is configured to ignore `node_modules/`, `backend/target/`, IDE files, and logs.
* Default ports used:

  * Backend: 8080
  * Frontend: 4200
  * MySQL: 3306 (internal container port)
