---
Module: Building Usable Software
Date: 11-10-2023
Topic: System Modelling and UML
---
- [ ] Describe the object-oriented analysis and design process
- [ ] Explain various models that can be used to describe an object-oriented analysis and design
- [ ] Understand how the Unified Modelling Language (**UML**) may be used in software systems
# System Modelling
## What is it?
- It is the process of **developing abstract models** of a system, where each represents a different view or perspective of the system
- Partial or full representation of the system to be built or as built using a graphical notation, which is based on **UML**
## Who uses them?
Analysts use this to **help understand the functionality** of the system **and communicate** to customers

**What are system models?**
- **Hide the systems complexity** by looking at a problem from a certain perspective
- Focus on relevant parts **ignoring irrelevant details**
- Relevant details **depend on the model used**

**Why *not* use code to model?**
- Software is getting more complex and contains many lines of code
- Single programmers cannot manage this amount of code
- Code is not easily understandable by developers who did not write it

## When are system models used?
- During requirements engineering
	- help **clarify function, strengths and weaknesses**
- Help explain proposed requirements to other system stakeholders
	- Help discuss design proposals and document system for implementation
- Possible to generate a complete or partial system implementation from system model

## What do we model?
**Different views**:
- *External*: system **context or environment**
- *Interaction*: **How system interacts** with environment, users or components
- *Structural (static)*: System's **organisation** or data
- *Behavioural (dynamic sequence of flow)*: System's **dynamic behaviour and how it responds** to events
### External
- Places the system in context
- Define what is inside/outside the system
	- **Not always clear**
	- Profound effect on the system requirements
### Interaction
- **User:** Helps identify user requirements
- **System-to-system:** highlights communication problems that may occur (*external*)
- **Component**: Helps understand if a proposed system structure is likely to deliver the required system performance dependability (*internal*)
### Structural and Behavioural Perspective
#### Structural Models
- Represent the **elements** and the **mechanism** to assemble them
- Discover the **key data** contained in the problem domain
#### Behavioural Models
- Describe the internal behaviour of a system
- Representations of the details of a business process identified by use cases (*Sequence & Communication diagrams*)
- Representations of changes in the data. Focus on the dynamic view of the system, not on how it is implemented
## What is UML?
**UML** is the **general purpose modelling language** for *specifying, visualising, constructing and documenting* software systems.
- **Specification**: simple enough to be understood by the clients, requirements engineers, designers, developers
- **Visualisation**: can be represented graphically
- **Construction**: precise enough to make code generation possible and to enable analysis on constructs Model Driven Engineering and Generative
- **Documentation**: widely used and understandable by other developers

![[Pasted image 20231011235050.png]]

**UML Models**
- [[Use Case Diagrams]]
- [[Activity Diagrams]]
