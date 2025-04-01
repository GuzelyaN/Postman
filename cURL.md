# 📌 API Requests for Reqres.in

This document provides **cURL** examples for interacting with the **Reqres.in** API, covering user creation, authentication, updates, and deletion. Additionally, error handling scenarios are included to ensure robustness.

---

## 🔹 **User Registration & Authentication**

### 🚀 **Register a New User**
```bash
curl --location 'https://reqres.in/api/register' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "eve.holt@reqres.in",
    "password": "pistol"
}'
```

#### **Error Handling: Bad Request (400)**
```bash
curl --location 'https://reqres.in/api/register' \
--data-raw '{
    "email": "eve.holt@reqres.in"111,  # Invalid email format
    "password": "pistol"
}'
```
- **Expected Response:**
```json
{
  "error": "Bad Request"
}
```

#### **Error Handling: Incorrect User (400)**
```bash
curl --location --globoff 'https://reqres.in/api/register' \
--data-raw '{
    "email": "eva@gmail.com",
    "password": "pistol"
}'
```
- **Expected Response:**
```json
{
    "error": "Note: Only defined users succeed registration"
}
```

---

### 🔐 **User Login**
```bash
curl --location 'https://reqres.in/api/login' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "eve.holt@gmail.com",
    "password": "cityslicka"
}'
```

#### 🔐 **Error Handling: Missing Password**
```bash
curl --location 'https://reqres.in/api/login' \
--data-raw '{
    "email": "eve.holt@reqres.in",
    "password": ""  # Empty password
}'
```
- **Expected Response:**
```json
{
  "error": "Missing password"
}
```

---

### 📝 **Register Another User**
```bash
curl --location 'https://reqres.in/api/register' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "eve.holt@reqres.in",
    "password": "cityslicka"
}'
```

#### 🔐 **Error Handling: Missing Password**
```bash
curl --location 'https://reqres.in/api/login' \
--data-raw '{
    "email": "eve.holt@reqres.in",
    "password": ""  # Empty password
}'
```
- **Expected Response:**
```json
{
  "error": "Missing password"
}
```

---

## 🔹 **User Data Management**

### 📄 **Get User Data**
```bash
curl --location 'https://reqres.in/api/users/2'
```

#### **Error Handling: Not Found (404)**
```bash
curl --location 'https://reqres.in/api/users/sdfsdf'  # Non-existent user ID
```
- **Expected Response:**
```json
{
  "error": "User not found"
}
```

### ✏️ **Update User Data (PATCH)**
```bash
curl --location --request PATCH 'https://reqres.in/api/users/2' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "123@123"
}'
```

### 🔄 **Update User Data (PUT)**
```bash
curl --location --request PUT 'https://reqres.in/api/users/2' \
--header 'Content-Type: application/json' \
--data-raw '{
    "first_name": "Neo_first",
    "last_name": "Anderson"
}'
```

### ❌ **Delete User**
```bash
curl --location --request DELETE 'https://reqres.in/api/users/2'
```

---

📌 **Note:** Modify the request payloads as needed for your testing purposes. Always ensure you are testing edge cases like missing parameters, invalid formats, and error scenarios.





