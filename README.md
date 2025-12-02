# 📂 Docket-DOCMS

**Fullstack Document Management System**

Docket-DOCMS is a robust application designed to help users manage their documents in an organized and secure way. It utilizes a RESTful API architecture to handle document creation, editing, sharing, and role-based access control.

🚀 [View Live Demo](#)

---

## 📑 Table of Contents

* [Features](#-features)
* [Tech Stack](#-tech-stack)
* [Installation](#-installation)
* [Testing](#-testing)
* [API Documentation](#-api-documentation)
* [Contributing](#-contributing)
* [License](#-license)

---

## ✨ Features

The application offers three distinct levels of authorization, ensuring secure access control.

### 👤 Guest

* View public documents.
* Register and create a new account.

### 🧑‍💻 Regular User

* **Document Management**: Create, edit, and delete personal documents.
* **Access Control**: Set document access to `Public`, `Private`, or `Role`.
* **Profile**: Edit and delete user profile.
* **View Permissions**:
   * View all public documents.
   * View `Role` documents created by users with the same or lesser role level.

### 🛡️ Admin

Includes all Regular User privileges, plus:

* **User Management**: View all users and update user roles (e.g., upgrade a user to Admin).
* **Role Management**: Create, edit, and delete roles (excluding the default Admin role).

---

## 🛠 Tech Stack

### Backend

* **Node.js** - Runtime environment
* **Express** - Web framework
* **PostgreSQL** - Relational Database
* **Sequelize** - ORM

### Frontend

* **ReactJS** - UI Library
* **Redux** - State Management

---

## 💻 Installation

Follow the steps below to set up a local development environment.

### Prerequisites:

* PostgreSQL
* Node.js (v6.10.0 or higher)

### 1. Clone the Repository

```bash
git clone https://github.com/andela-angene/document-management-system.git
cd document-management-system
```

### 2. Configure Environment

Rename the sample environment file and update the database credentials.

```bash
mv .env_sample .env
# Open .env and add your DATABASE_URL
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Start the Server

```bash
npm start
```

---

## 🧪 Testing

Ensure the project dependencies are installed before running tests.

### Server & Client Tests

1. Add a `DATABASE_TEST_URL` to your `.env` file.
2. Run the test suite:

```bash
npm test
```

### End-to-End (E2E) Tests

1. Start the application in one terminal: `npm start`
2. Open a new terminal and run the setup:

```bash
npm run e2e-setup
```

3. Execute the tests:

```bash
npm run e2e-test
```

---

## 📖 API Documentation

The full API documentation is available [here](#). Below is a summary of the available endpoints.

### 👥 Users

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/users/login` | Logs in a user. |
| `POST` | `/users/logout` | Logs out a user. |
| `POST` | `/users/` | Creates a new user. |
| `GET` | `/users/` | Gets all users (Admin only). |
| `GET` | `/users/:id` | Find a user by ID. |
| `PUT` | `/users/:id` | Updates a user's profile. |
| `DELETE` | `/users/:id` | Delete a user's profile. |
| `GET` | `/users/:id/documents` | Gets all documents for a specific user. |
| `GET` | `search/users/?q={query}` | Search users by username. |

### 📄 Documents

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/documents/` | Creates a new document. |
| `GET` | `/documents/` | Gets all documents. |
| `GET` | `/documents/:id` | Find document by ID. |
| `PUT` | `/documents/:id` | Updates a document (Author only). |
| `DELETE` | `/documents/:id` | Delete a document (Author only). |
| `GET` | `search/documents/?q={query}` | Search documents by title. |

### 🔑 Roles (Admin Only)

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/roles/` | Get all Roles. |
| `POST` | `/roles/` | Create a new Role. |
| `PUT` | `/roles/:id` | Edit an existing Role. |
| `DELETE` | `/roles/:id` | Delete a Role. |

---

## ⚖️ Scalability & Limitations

* **Scalability**: The application architecture is designed to scale horizontally if the need arises.
* **Current Limit**: Currently optimized for standard enterprise loads (supports massive user bases theoretically).

---

## 🤝 Contributing
Contributions are most welcome!