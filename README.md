# Task Manager REST API

A simple CRUD API for managing tasks built with ASP.NET Core 8 and SQLite.

## Overview

This API provides endpoints to create, read, update, and delete tasks. It uses Entity Framework Core with SQLite for data persistence and includes Swagger UI for interactive API documentation.

**Features:**
- Full CRUD operations
- SQLite database (no server setup required)
- Input validation and error handling
- Filter tasks by completion status
- Swagger/OpenAPI documentation

## Getting Started

**Prerequisites:**
- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)

**Setup:**

1. Clone the repository
```bash
git clone <your-repo-url>
cd TaskManagerAPI
```

2. Create `Properties/launchSettings.json`
```json
{
  "profiles": {
    "http": {
      "commandName": "Project",
      "dotnetRunMessages": true,
      "launchBrowser": true,
      "applicationUrl": "http://localhost:5000",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    }
  }
}
```

3. Run the application
```bash
dotnet restore
dotnet run
```

4. Open `http://localhost:5000` to access Swagger UI

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/tasks` | Get all tasks |
| GET | `/api/tasks?completed=true` | Filter by completion status |
| GET | `/api/tasks/{id}` | Get a specific task |
| POST | `/api/tasks` | Create a new task |
| PUT | `/api/tasks/{id}` | Update a task |
| DELETE | `/api/tasks/{id}` | Delete a task |

**Example Request:**
```json
POST /api/tasks
{
  "title": "Complete documentation",
  "description": "Write API documentation",
  "isCompleted": false,
  "dueDate": "2025-11-10T00:00:00Z"
}
```

## Technologies

- ASP.NET Core 8
- Entity Framework Core
- SQLite
- Swagger/OpenAPI
