# Smart Skill Map System

A comprehensive AI-driven career pathing and assessment platform that helps users explore career paths, assess their skills, and receive personalized recommendations.

## Prerequisites

Before running the application, ensure the following software is installed:

* Java (JDK 17 or later)
* Apache Maven
* MySQL Server
* MySQL Workbench

## Database Setup

1. Open MySQL Workbench and connect to your local MySQL server.
2. Create the database:

```sql
CREATE DATABASE IF NOT EXISTS smartskillmap;
```

3. Open the SQL script:

```
database/reset_and_seed_final.sql
```

4. Execute the entire script to:

   * Create all required database tables
   * Insert sample data
   * Seed career paths and assessments

> **Note:** Update the database configuration in `src/main/resources/application.properties` with your own MySQL username and password before running the application.

## Running the Application

Open a terminal in the project root directory and run:

```bash
mvn spring-boot:run
```

Wait until you see a message similar to:

```
Tomcat started on port 8081
```

## Access the Application

Open your browser and visit:

```
http://localhost:8081/
```

## Troubleshooting

### Port 8081 Already in Use

If the application fails to start because port **8081** is already in use, terminate the existing process.

**PowerShell**

```powershell
Stop-Process -Id (Get-NetTCPConnection -LocalPort 8081).OwningProcess -Force
```

**Command Prompt (CMD)**

```cmd
for /f "tokens=5" %a in ('netstat -aon ^| findstr :8081') do taskkill /f /pid %a
```

Then restart the application:

```bash
mvn spring-boot:run
```
