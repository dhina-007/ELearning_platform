# 🌍 Digital Learning Platform (DLP)

**Offline-First Digital Education Platform** that enables students and teachers to access learning materials anytime, even in low or no internet connectivity.  
It supports interactive lessons, digital literacy modules, quizzes, progress tracking, and multimedia learning experiences.

---

## 🚀 Overview

The **Digital Learning Platform** (DLP) is a full-stack application designed to make education accessible in both online and offline environments.  
Built using **Java (Spring Boot)** for the backend and **React (PWA)** for the frontend, it provides a fast, reliable, and mobile-first experience.

---

## 🧩 Key Features

✅ **Offline-first Learning** — Works seamlessly even with poor or no internet connection.  
✅ **Interactive Lessons** — Supports text, video, audio, and quiz-based modules.  
✅ **Digital Literacy** — Courses for both students and teachers to improve digital skills.  
✅ **Progress Tracking** — Track completion, time spent, and quiz results.  
✅ **Gamification** — Badges, points, and leaderboards to boost engagement.  
✅ **Teacher Portal** — Create, manage, and monitor course content.  
✅ **Student Portal** — Access courses, attempt lessons, and view progress.  
✅ **Multi-device Support** — Optimized for low-end Android devices and desktops.  
✅ **PWA Ready** — Add to home screen and use offline via service workers.  
✅ **Admin Dashboard** — Manage users, roles, and platform analytics.  
✅ **Reporting System** — Course completion, user activity, and system metrics.  
✅ **Notifications** — In-app and push notifications for updates.  

---

## 🏗️ Tech Stack

### Backend
- **Java 17 + Spring Boot 3**
- **Spring Data JPA + Hibernate**
- **Spring Security + JWT**
- **PostgreSQL (Primary Database)**
- **Redis (Caching & Session Management)**
- **MinIO / AWS S3 (File Storage for materials)**
- **Liquibase** (Database versioning)
- **Maven**

### Frontend
- **React (Vite) + TypeScript (optional)**
- **Redux Toolkit** (State management)
- **IndexedDB / LocalForage** (Offline data storage)
- **Service Workers (PWA)**
- **Tailwind CSS / Material UI**
- **Axios / RTK Query (API Integration)**

---

## 📁 Project Structure

### Backend (Spring Boot)
backend/
│
├── src/
│ ├── main/
│ │ ├── java/com/dlp/
│ │ │ ├── controller/
│ │ │ │ ├── CourseController.java
│ │ │ │ ├── LessonController.java
│ │ │ │ ├── MaterialController.java
│ │ │ │ ├── EnrollmentController.java
│ │ │ │ ├── UserController.java
│ │ │ │ ├── ReportController.java
│ │ │ │ ├── QuizController.java
│ │ │ │ ├── DiscussionController.java
│ │ │ │ ├── NotificationController.java
│ │ │ ├── model/
│ │ │ ├── repository/
│ │ │ ├── service/
│ │ │ ├── dto/
│ │ │ ├── security/
│ │ │ └── DlpApplication.java
│ │ ├── resources/
│ │ │ ├── application.yml
│ │ │ └── db/changelog/
│ │ │ └── changelog-master.xml
│ └── test/
│
└── pom.xml


### Frontend (React PWA)

frontend/
│
├── src/
│ ├── components/
│ ├── pages/
│ │ ├── Home.jsx
│ │ ├── Courses.jsx
│ │ ├── Lessons.jsx
│ │ ├── Profile.jsx
│ │ ├── AdminDashboard.jsx
│ ├── features/
│ │ ├── auth/
│ │ ├── courses/
│ │ ├── lessons/
│ │ ├── offline/
│ ├── hooks/
│ ├── utils/
│ ├── serviceWorker.js
│ ├── App.jsx
│ └── main.jsx
│
└── package.json


---

## 🔗 API Documentation

### 🧑 User APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `POST` | `/users` | Create a new user (student/teacher) |
| `GET` | `/users/{id}` | Get user details |
| `PUT` | `/users/{id}` | Update user profile |
| `POST` | `/auth/login` | Login and get JWT token |
| `POST` | `/auth/register` | Register a new user |
| `POST` | `/auth/refresh` | Refresh JWT token |

---

### 🎓 Course APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `GET` | `/courses` | Get all courses |
| `GET` | `/courses/{id}` | Get specific course |
| `POST` | `/courses` | Create a course |
| `PUT` | `/courses/{id}` | Update course |
| `DELETE` | `/courses/{id}` | Delete course |
| `GET` | `/courses/category/{category}` | Filter by category |

---

### 📘 Lesson APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `GET` | `/courses/{courseId}/lessons` | List all lessons in a course |
| `GET` | `/courses/{courseId}/lessons/{lessonId}` | Get lesson details |
| `POST` | `/courses/{courseId}/lessons` | Create lesson |
| `PUT` | `/courses/{courseId}/lessons/{lessonId}` | Update lesson |
| `DELETE` | `/courses/{courseId}/lessons/{lessonId}` | Delete lesson |

---

### 📂 Material APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `GET` | `/courses/{courseId}/lessons/{lessonId}/materials` | Get materials for a lesson |
| `POST` | `/courses/{courseId}/lessons/{lessonId}/materials` | Upload material (PDF, Video, etc.) |
| `PUT` | `/courses/{courseId}/lessons/{lessonId}/materials/{materialId}` | Update material |
| `DELETE` | `/courses/{courseId}/lessons/{lessonId}/materials/{materialId}` | Delete material |

---

### 👥 Enrollment APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `POST` | `/enrollments` | Enroll student to course |
| `GET` | `/users/{userId}/enrollments` | List enrolled courses of a user |
| `GET` | `/courses/{courseId}/students` | List students enrolled in a course |

---

### 🧠 Quiz APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `GET` | `/courses/{courseId}/lessons/{lessonId}/quizzes` | Get quizzes for a lesson |
| `POST` | `/courses/{courseId}/lessons/{lessonId}/quizzes` | Add a new quiz |
| `POST` | `/courses/{courseId}/lessons/{lessonId}/quizzes/{quizId}/submit` | Submit quiz attempt |
| `GET` | `/users/{userId}/quiz-results` | Get user's quiz performance |

---

### 💬 Discussion APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `GET` | `/courses/{courseId}/discussions` | Get course discussions |
| `POST` | `/courses/{courseId}/discussions` | Add new discussion thread |
| `POST` | `/courses/{courseId}/discussions/{threadId}/comments` | Add comment to discussion |

---

### 🏆 Gamification APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `GET` | `/users/{userId}/badges` | Get earned badges |
| `POST` | `/users/{userId}/badges` | Award badge |
| `GET` | `/leaderboard` | Get top users by points |

---

### 📊 Report APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `GET` | `/reports/courses` | Get course engagement report |
| `GET` | `/reports/users` | Get user learning analytics |
| `GET` | `/reports/system` | System-wide usage and performance metrics |

---

### 🔔 Notification APIs
| Method | Endpoint | Description |
|--------|-----------|-------------|
| `GET` | `/notifications/{userId}` | Fetch all notifications |
| `POST` | `/notifications/send` | Send notification to users |
| `POST` | `/notifications/subscribe` | Subscribe user to push notifications |

---

## ⚙️ Offline-First Strategy

- **Frontend** stores lessons, quizzes, and user progress using **IndexedDB**.
- **Service Workers** handle background sync when internet is restored.
- **Backend** provides **sync endpoints**:
  - `POST /sync/offline-progress`
  - `GET /sync/updates`

---

## 🔒 Security

- JWT-based Authentication (Access + Refresh Tokens)
- Role-based Authorization (`ADMIN`, `TEACHER`, `STUDENT`)
- HTTPS enforced for production
- XSS and CSRF protection enabled
- Rate Limiting via Spring Filters

---

## 📦 Deployment

| Environment | Technology |
|--------------|-------------|
| **Backend** | Deployed on AWS Elastic Beanstalk / EC2 |
| **Database** | AWS RDS (PostgreSQL) |
| **Storage** | AWS S3 or MinIO |
| **Frontend** | Deployed on Netlify / Vercel / AWS Amplify |
| **Domain** | Cloudflare / Route53 with HTTPS |
| **CI/CD** | GitHub Actions + Docker |

---

## 🧪 Testing

- **Backend:** JUnit, Mockito, Testcontainers
- **Frontend:** Jest, React Testing Library
- **API Testing:** Postman / Newman Collection

---

## 🧰 Installation

### Backend
```bash
cd backend
mvn clean install
mvn spring-boot:run

### Frontend

cd frontend
npm install
npm run dev
