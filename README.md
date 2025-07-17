# 📡 LogWaveMonitor

A full-stack, AI-assisted log monitoring system that combines a C# Web API backend with a sleek, real-time RShiny frontend. Designed to help developers, analysts, and solutions architects visualize and track system events in real time, with zero manual database interaction.

---

## 📚 Table of Contents

* [✅ Project Summary](#-project-summary)
* [🧱 Folder Structure](#-folder-structure)
* [⚙️ Tech Stack & Tools](#️-tech-stack--tools)
* [🧭 Step-by-Step Setup](#-step-by-step-setup)
* [📦 R Code Samples](#-r-code-samples)
* [🧾 C# Backend Source Code](#-c-backend-source-code)
* [🔁 Mermaid Diagram](#-mermaid-diagram)
* [🌟 Features](#-features)
* [🧠 Why This Matters](#-why-this-matters)
* [📎 Credits & Attribution](#-credits--attribution)
* [🏷️ Hashtags](#️-hashtags)

---

## ✅ Project Summary

**LogWaveMonitor** was built to simulate and display live event logs as real-time signal waves. It includes:

* A `.NET 8` Web API backend for ingesting log data
* A `SQL Server LocalDB` database for persistent storage
* A `Swagger` UI for live API testing
* An `RShiny` frontend to display logs as animated signal graphs
* A `simulate_logs.R` script for auto-generating system events

This solution was built by a career-transitioning technologist using **AI engineering prompts** to streamline development. It’s a showcase of how low-code solutions and modern tooling can work together.

---

## 🧱 Folder Structure

```
/LogWaveMonitor/
├── LogWaveApi/            # .NET 8 Web API project
│   ├── Controllers/
│   ├── Data/
│   ├── Models/
│   ├── Migrations/
│   └── Program.cs, .csproj, etc.
├── LogWaveDB/             # SQL LocalDB schema (auto-generated)
├── shiny-app/             # RShiny frontend
│   └── app.R
├── simulate_logs.R        # R script for generating logs
└── README.md
```

---

## ⚙️ Tech Stack & Tools

### 💻 Languages & Frameworks

![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge\&logo=c-sharp\&logoColor=white)
![.NET 8](https://img.shields.io/badge/.NET-8.0-purple?style=for-the-badge\&logo=dotnet\&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL--Server-CC2927?style=for-the-badge\&logo=microsoftsqlserver\&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge\&logo=swagger\&logoColor=black)
![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge\&logo=r\&logoColor=white)
![Shiny](https://img.shields.io/badge/Shiny-2C3E50?style=for-the-badge\&logo=r\&logoColor=white)

### 🛠 Tooling

![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge\&logo=visualstudiocode\&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=for-the-badge\&logo=powershell\&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge\&logo=github)

### 📦 R Packages

![httr](https://img.shields.io/badge/httr-CRAN-blue)
![jsonlite](https://img.shields.io/badge/jsonlite-CRAN-blue)
![ggplot2](https://img.shields.io/badge/ggplot2-CRAN-blue)
![lubridate](https://img.shields.io/badge/lubridate-CRAN-blue)
![dplyr](https://img.shields.io/badge/dplyr-CRAN-blue)
![shiny](https://img.shields.io/badge/shiny-CRAN-blue)
![DT](https://img.shields.io/badge/DT-CRAN-blue)

---

## 🧭 Step-by-Step Setup

### 🔧 Backend (.NET 8 + SQL)

```bash
# From PowerShell or VS Code Terminal
cd C:\Users\YourName\Documents\LogWaveMonitor
mkdir LogWaveApi
cd LogWaveApi

dotnet new webapi
```

* Create `Controllers`, `Data`, and `Models` folders.
* Add `LogEvent.cs`, `LogWaveContext.cs`, and `LogEventsController.cs`
* Modify `Program.cs` for DI and SQL connection
* Update `appsettings.json`:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=(localdb)\\MSSQLLocalDB;Database=LogWaveDB;Trusted_Connection=True;"
}
```

### 🗄 EF Core Migration

```bash
dotnet ef migrations add InitSchema
dotnet ef database update
dotnet run --project .\LogWaveApi.csproj
```

### 🔍 Swagger UI

Visit: `http://localhost:5008/swagger`
Use POST and GET to simulate and retrieve logs manually.

### 📊 Frontend (R + RShiny)

1. Create `shiny-app/app.R`
2. Use `httr` + `jsonlite` to GET from the API
3. Build waveform UI using `ggplot2`
4. Add data table via `DT::renderDT`

### 🧪 Log Simulation

Run this in RStudio:

```r
source("simulate_logs.R")
```

This script randomly generates system events and POSTs to the API using `httr` with the correct JSON headers.

---
