# Architecture as Code
### Scalable Design with C4 and LikeC4
#### Ryan Coates

---

## A brief history of software architecture


---

## The C4 Model
- **Context** – the system in its environment  
- **Containers** – applications, databases, services  
- **Components** – internals of a container  
- **Code** – class level (optional)

|||

## Context

|||

## Containers

|||

## Components

|||

## Code

---

## Why use C4?
- Consistent way to describe software architecture  
- Zoom levels from high-level to detail  
- Communicates to technical & non-technical audiences

---

## LikeC4
A domain-specific language for expressing C4 diagrams as code.

```likec4
model {
  system demoSystem {
    title "Demo System"
    container api {
      technology "ASP.NET Core"
      title "API Service"
    }
    container db {
      technology "MongoDB"
      title "Database"
    }
    relationship api -> db "Reads/Writes"
  }
}
