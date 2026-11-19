
# 01-Improvise-Python-App-using-GitHub-Copilot-Chandra

## Improvising Python App Using GitHub Copilot

### Text Token API

A Python-based FastAPI application that generates text tokens and SHA-256 checksums.

This project demonstrates how GitHub Copilot can be used to enhance an existing Python application by creating API endpoints, validating JSON requests, generating checksums, documenting code, and creating automated test cases.

---

## Features

- FastAPI-based REST API.
- Personalized welcome message.
- Pydantic model for JSON request validation.
- GET endpoint for generating SHA-256 tokens.
- POST endpoint for generating text tokens and SHA-256 checksums.
- Automatic API documentation using Swagger UI.
- Input validation and error handling.
- Automated testing using Pytest and FastAPI TestClient.

---

## Technologies Used

- Python
- FastAPI
- Pydantic
- Uvicorn
- SHA-256 Hashing
- Pytest
- HTTPX
- GitHub Copilot

---

## Project Structure

```text
01-Improvise-Python-App-using-GitHub-Copilot-Chandra/
│
├── main.py
├── requirements.txt
├── test_main.py
└── README.md
```

### File Description

- **main.py:** Contains the FastAPI application, Pydantic model, welcome endpoint, token-generation endpoint, and checksum-generation endpoint.
- **requirements.txt:** Contains the Python dependencies required to run the application.
- **test_main.py:** Contains automated test cases for validating API functionality.
- **README.md:** Provides project information and execution instructions.

---

## Installation

### Step 1: Clone the Repository

```bash
git clone <your-github-repository-url>
```

### Step 2: Navigate to the Project Directory

```bash
cd 01-Improvise-Python-App-using-GitHub-Copilot-Chandra
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Running the Application

Start the FastAPI application using the Uvicorn web server.

```bash
uvicorn main:app --reload
```

Once the application starts successfully, it will be available at:

http://127.0.0.1:8000

---

## API Endpoints

### 1. Welcome Endpoint

**Endpoint:** `/`

**Method:** GET

**Description:** Displays a personalized welcome message.

**Sample Response:**

```json
{
  "message": "Welcome, Chandra Mani! Welcome to the Python Text Checksum Generator Application. Enter your text to generate its SHA-256 checksum."
}
```

### 2. Generate Text Token

**Endpoint:** `/generate`

**Method:** GET

**Description:** Accepts text as a query parameter and generates its SHA-256 token.

**Sample Request:**

```text
GET /generate?text=hello
```

**Sample Response:**

```json
{
  "token": "2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824"
}
```

### 3. Generate Text Tokens and Checksum

**Endpoint:** `/generate`

**Method:** POST

**Description:** Accepts text in a JSON request body, splits the text into individual tokens, and generates its SHA-256 checksum.

**Request Content-Type:** application/json

**Sample JSON Request:**

```json
{
  "text": "Hello Varsha"
}
```

**Sample JSON Response:**

```json
{
  "tokens": [
    "Hello",
    "Varsha"
  ],
  "checksum": "<generated SHA-256 checksum>"
}
```

---

## API Documentation

FastAPI automatically generates interactive API documentation using Swagger UI.

After starting the application, open the following URL in your browser:

http://127.0.0.1:8000/docs

The Swagger interface allows users to:

- View all available API endpoints.
- Understand request and response formats.
- Submit GET and POST requests.
- Test API functionality.
- View API responses and status codes.

---

## Running Test Cases

The project uses Pytest and FastAPI TestClient to validate the API endpoints.

### Execute All Tests

```bash
pytest
```

### Execute Tests with Detailed Output

```bash
pytest -v
```

### Test Coverage

The test cases validate:

1. Welcome endpoint functionality.
2. SHA-256 token generation.
3. JSON-based text token generation.
4. Correct checksum calculation.
5. Empty text handling.
6. Whitespace preservation in checksum generation.
7. Missing request fields.
8. Invalid JSON input.
9. Invalid data types.
10. API documentation and schema validation.

---

## Checksum Generation

The application uses the SHA-256 hashing algorithm to generate a unique hexadecimal digest for the submitted text.

The checksum is calculated using Python's hashlib library.

Example:

```python
import hashlib

text = "hello"

checksum = hashlib.sha256(
    text.encode("utf-8")
).hexdigest()

print(checksum)
```

---

## Purpose of the Project

The main objective of this project is to demonstrate the use of GitHub Copilot as an AI-powered coding assistant.

Through this project, developers can:

- Improve existing Python applications.
- Generate Pydantic models.
- Develop FastAPI endpoints.
- Generate text tokens and checksums.
- Add code comments and documentation.
- Create automated test cases.
- Improve Python code quality.
- Increase development productivity using GitHub Copilot.

---

## Author

Varsha

## Version

1.0.0
