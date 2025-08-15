# AuthService (Appwrite Authentication Wrapper)

This module provides a simple wrapper around [Appwrite](https://appwrite.io/) authentication APIs.  
It allows you to easily create accounts, log in users, fetch the current user, and log out.

## 📦 Installation

Before using this service, make sure you have:

- An Appwrite project set up.
- Your Appwrite **endpoint URL** and **project ID** ready.

Install the Appwrite JavaScript SDK:

```bash
npm install appwrite
```

## 📂 Project Structure

```
src/
 ├── conf/
 │    └── conf.js         # Appwrite configuration (URL, Project ID, etc.)
 ├── services/
 │    └── AuthService.js  # This file
```

---

## ⚙️ Configuration

`conf/conf.js` should export your Appwrite configuration:

```javascript
const conf = {
    appwriteUrl: "YOUR URL",
    appwriteProjectId: "YOUR_PROJECT_ID"
};

export default conf;
```

---

## 🚀 Usage

### 1️⃣ Import the Service
```javascript
import AuthService from "./services/AuthService";

const authService = new AuthService();
```

---

### 2️⃣ Create a New Account
```javascript
await authService.createAccount({
    email: "test@example.com",
    password: "securepassword",
    name: "Example Name"
});
```
If account creation is successful, the method automatically logs the user in.

---

### 3️⃣ Login
```javascript
await authService.login({
    email: "test@example.com",
    password: "securepassword"
});
```

---

### 4️⃣ Get Current User
```javascript
const currentUser = await authService.getCurrentUser();
console.log(currentUser);
```

---

### 5️⃣ Logout
```javascript
await authService.logout();
```

---

## 📜 Methods Overview

| Method               | Parameters                                         | Description |
|----------------------|----------------------------------------------------|-------------|
| `createAccount`      | `{ email, password, name }`                        | Creates a new user account and logs them in automatically. |
| `login`              | `{ email, password }`                              | Logs in a user using email and password. |
| `getCurrentUser`     | `none`                                              | Fetches details of the currently logged-in user. |
| `logout`             | `none`                                              | Logs out the current user by deleting all sessions. |

---

## 🛠 Error Handling
All methods use `try...catch` blocks and log errors to the console for debugging.  
You can customize error handling as needed.

---

## 📄 License
This service is free to use in your Appwrite projects.
