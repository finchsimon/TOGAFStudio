## TogafStudio

**TogafStudio** is a Clean Architecture based C# application for generating **TOGAF ADM-aligned architecture documents**.

It provides a structured way to:

* capture architecture inputs
* guide users through TOGAF phases (Preliminary + A–H)
* generate professional **Word (.docx) documents**
* maintain traceability, governance, and audit history

---

## Purpose

This tool is designed to support **Enterprise Architecture activities** by :

* standardising TOGAF deliverables
* guiding architects through ADM phases
* capturing structured questionnaire responses
* generating consistent, reusable documentation
* enabling future governance, approval, and traceability workflows

---

## Architecture

The solution follows **Clean Architecture principles** with a strict separation of concerns:

```text
Domain         → Core business logic and entities  
Application    → Use cases (CQRS: Commands & Queries)  
Infrastructure → External concerns (EF Core, OpenXML, file storage)  
Web API        → Backend interface (minimal APIs)  
Desktop (WPF)  → User interface (client application)
```

---

## ⚙️ Technology Stack

* **.NET (C#)**
* **ASP.NET Core Web API**
* **WPF (Desktop Client)**
* **Entity Framework Core**
* **PostgreSQL**
* **FluentValidation**
* **xUnit + NSubstitute + FluentAssertions**
* **Docker Compose**
* **Seq** (structured logging)

---

## Key Concepts

### Architecture Engagement

Represents a full architecture initiative.

### TOGAF ADM Phases

Supports:

* Preliminary
* Phase A–H

Each phase includes:

* structured descriptions
* guided questions
* captured responses
* generated documents

### Questionnaire System

* phase-specific questions
* structured responses
* reusable templates (JSON-based)

### Document Generation

* Word (.docx) generation
* phase-level documents
* full ADM document packs (future)

### 📊 Requirements Traceability

* track requirements across phases
* support audit and governance

---

## CQRS Implementation

The application uses a **custom CQRS implementation**:

### Commands

Used for state changes:

* Create engagement
* Save answers
* Generate documents
* Approve/reject outputs

### Queries

Used for data retrieval:

* Get templates
* Get questionnaire data
* Get generated documents
* Get traceability matrix

---

## Project Structure

```text
src/
  Domain/
  Application/
  Infrastructure/
  Web.Api/
  Desktop/
  SharedKernel/

tests/
  UnitTests/
  IntegrationTests/
  ArchitectureTests/
  Desktop.Tests/
```

---

## 🐳 Local Development

The solution uses **Docker Compose** for local infrastructure:

* PostgreSQL (database)
* Seq (logging)

Run:

```powershell
docker-compose up -d
```

---

## 🧪 Testing Strategy

### Unit Tests

* Command handlers
* Query handlers
* Domain logic
* Validators

### Architecture Tests

* Enforce Clean Architecture boundaries

### Integration Tests

* API endpoints
* Database interactions
* document generation

---

## Roadmap

### Version 1

* Engagement creation
* Phase A–H templates
* Questionnaire capture
* Phase document generation

### Future Enhancements

* Full ADM document pack generation
* Approval workflows
* Architecture governance features
* Event sourcing (optional, via Marten)
* Multi-user support
* Web-based UI

---

## Notes

* TOGAF content used in this project is **customised and not copied verbatim** from official publications.
* Templates are designed to be **adaptable to organisational needs**.

## License

[![BSL 1.1](https://img.shields.io/badge/License-BSL%201.1-lightblue)](LICENSE)

**BSL 1.1** - Free for non-production use. Production/SaaS requires license.
→ [LICENSE](LICENSE) | Converts to MIT 2030

---

## Author

Developed by Simon Finch as a structured TOGAF support tool using modern .NET architecture patterns
