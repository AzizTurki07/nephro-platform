# Nephro-Platform

Plateforme de gestion néphrologique développée avec Angular (frontend), Spring Boot (backend) et MySQL (base de données), conteneurisée avec Docker.

---

## Structure du projet

```
nephro-platform/
├── backend/         # Spring Boot
├── frontend/        # Angular
├── docker-compose.yml
└── README.md
```

---

## Prérequis

- Docker + Docker Compose
- Node.js (optionnel pour dev Angular local)
- Java 17 JDK (optionnel pour dev backend local)

---

## Lancer le projet

Depuis le dossier racine du projet :

```bash
docker compose up --build
```

- Backend : [http://localhost:8080](http://localhost:8080)  
- Frontend : [http://localhost:4200](http://localhost:4200)

Pour arrêter :

```bash
docker compose down
```

---

## Configuration API Angular

Le frontend Angular utilise `environment.ts` pour connaître l’URL du backend :

```ts
// frontend/src/environments/environment.ts
export const environment = {
  production: false,
  apiUrl: 'http://localhost:8080'
};
```

---

## Lancer en local (optionnel)

**Frontend Angular :**

```bash
cd frontend
npm install
ng serve
```

**Backend Spring Boot :**

```bash
cd backend
mvn clean package -DskipTests
java -jar target/*.jar
```

---

## Notes

- `.gitignore` est configuré pour ignorer `node_modules/`, `backend/target/`, IDE files et logs.
- Tous les services utilisent les ports par défaut :
  - Backend : 8080
  - Frontend : 4200
  - MySQL : 3306 (conteneur interne)

