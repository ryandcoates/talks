# Architecture as Code
### Scalable Design with C4 and LikeC4
#### - by Ryan Coates

---

## A brief history of software architecture

#### How we got here

|||

## The Early Days
In the early decades of software engineering — the 1960s through the 1980s. architecture was **implicit**.  

>Designs lived in **engineers’ heads** or **sketches on whiteboards**.  

- Systems were small, monolithic, and tightly coupled  
- Documentation was rare or bespoke  
- Architecture was *an art*, not a discipline  

|||

This worked… *until* systems grew larger than any one person could hold in memory.

|||

## The Rise of Formal Methods
By the late 1980s, software projects were failing at alarming rates.  
In response, structured design methods emerged, each with their own notations:

- **Yourdon / DeMarco** data flow diagrams  
- **Booch** method for object-oriented design  
- **OMT (Object Modeling Technique)** by Rumbaugh Et Al.
- **OOSE (Object-Oriented Software Engineering)** by Jacobson  

|||

Each tried to bring **rigor and consistency** to how we described systems, but none of them spoke a *common language*.

|||

## The Birth of UML
In the mid-1990s, the "three amigos" — **Booch, Rumbaugh, and Jacobson** unified their methods into the  

**Unified Modeling Language (UML)**.  

UML gave us a standard way to model:

- Structure (class, component, deployment diagrams)  
- Behavior (sequence, state, activity diagrams)  

For a time, UML brought a golden age of **architectural clarity and documentation**.  
Architecture was once again a first-class concern.

|||

## The Agile Era and Architectural Drift

Then came **2001** and the **Agile Manifesto**.  

|||

While Agile revolutionized delivery speed and adaptability, it also carried an unintended side effect:  

>Working software over comprehensive documentation 

- __Architecture__ became a dirty word.
- Diagrams and models were seen as bureaucracy  
- Architectural rigor eroded in favor of iteration speed  


|||

## Where We Are Now
Modern systems are distributed, complex, and fast-moving. microservices, containers, cloud-native, event-driven architectures.  

Yet, we often still design them the way we did in the whiteboard era.  

|||

We need a lightweight, expressive, *shared language* for describing modern architecture, one that fits our Agile world without losing structure or clarity.

Enter __C4__

---

## The C4 Model

Introduces four defined levels of abstraction for an architectural model

- **Context** – the system in its environment  
- **Containers** – applications, databases, services  
- **Components** – internals of a container  
- **Code** – class level (optional)

|||

## Context

A software system is the highest level of abstraction and describes something that delivers value to its users, whether they are human or not. This includes the software system you are modelling, and the other software systems upon which your software system depends (or vice versa)

|||

## Containers

In the C4 model, a container represents an application or a data store. A container is something that needs to be running in order for the overall software system to work.

A container is an element of a system with an **independently managed lifecycle**

|||

## Components

With the C4 model, components are not separately deployable units. Instead, it’s the container that’s the deployable unit. In other words, all components inside a container execute in the same process space. 

|||


## Code

Finally, components are made up of one or more code elements constructed with the basic building blocks of the programming language that you’re using - classes, interfaces, enums, functions, objects, etc.

|||

## Other Views

- System Landscape
- Dynamic
- Deployment

---

<!-- .slide: data-background-image="context_c4.png" data-background-size="contain"-->

|||

<!-- .slide: data-background-image="containers_c4.png" data-background-size="contain"-->

|||

<!-- .slide: data-background-image="components_c4.png" data-background-size="contain"-->

|||

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
```

|||

## LikeC4 Tooling

- lkec4 cli tool
- likec4 vscode extension
- likec4 playground

|||

## LikeC4 CLI

Install via `npm` or use `npx` at runtime

- `likec4 serve`
- `likec4 generate`
- `likec4 build`
- `likec4 export`

Note: Demo some of these ryan