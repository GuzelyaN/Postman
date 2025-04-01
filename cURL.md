# 📌 API Requests for Reqres.in  

This document provides **cURL** examples for interacting with the **Reqres.in** API, including user creation, authentication, updates, and deletion.  

## 🔹 User Registration & Authentication  

### 🚀 **Register a New User**  
```bash
curl --location 'https://reqres.in/api/register' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "eve.holt@reqres.in",
    "password": "pistol"
}'
```

### 🔐 **User Login**  
```bash
curl --location 'https://reqres.in/api/login' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "eve.holt@gmail.com",
    "password": "cityslicka"
}'
```

### 📝 **Register Another User**  
```bash
curl --location 'https://reqres.in/api/register' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "eve.holt@reqres.in",
    "password": "cityslicka"
}'
```

## 🔹 User Data Management  

### 📄 **Get User Data**  
```bash
curl --location 'https://reqres.in/api/users/2'
```

### ✏️ **Update User (PATCH)**  
```bash
curl --location --request PATCH 'https://reqres.in/api/users/' \
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

📌 **Note:** Modify the request payloads as needed.  

