---
Module: Building Usable Software
Date: 11-10-2023
Topic: Use Case Diagrams
---
# What are Use Case Diagrams?
- How actors **interact** with a system: 2 elements
	- An actor is a **prospective** user or external system
	- Goal that some actor can achieve with the system
- *Design hint*: a use case shows what a system does, not how it does it
	- keep descriptions short, clear, and precise to separate the main flow of events from alternative and exceptional flows
- **Especially useful for requirements gathering and initial work with clients**
## Elements
**Actors**: Internal or external users that interact with the system (e.g. human, organisation, machine or other external system)
**Use cases**: System function/FR
**Relationships**: Connections between users and use cases
**Boundary**: Separate use cases that are internal to the system from the actors that are external to the system
#### How to find actors:
**Roles** played by people
	- What role do they play?
	- Who provides information to the system? (Input)
	- Who receives information from the system? (Output)
- Actors could be:
- Principal users
- Secondary (external hardware, other systems, etc)
They interact with use cases and are named by noun
#### How to find use cases:
1. **Start with list of actors** and consider:
	- **What use cases have value** for them? (what is needed from the system)
	- Any other interactions they expect to interact with the system
2. Use cases
	- Named by **verb + noun**
	- Each actor must be linked to a use case, while some use cases may not be linked to actors

##### Example: Ordering coffee through an app
1. **Customer** *starts app* and *logs in*
2. **Customer** *chooses preferred store*
3. **Customer** *enters coffee choice*
4. **App** *asks* if the customer "would like anything else?"
5. **Customer** *selects "checkout"*
6. **App** *asks for payment*
7. **Customer** *enters details*
8. **App** *validates order*
9. *Once done*, **app** *sends order* to the POS machine at preferred store and *leaves confirmation message* to customer's inbox
![[Pasted image 20231012000657.png]]

### Relationships
- Use `<<extend>>` when you are an option, alternating on normal behaviour, declaring your extension points in the base use case.
- Use `<<include>>` to show uses, complementary functionalities, and logical dependencies, or avoid repetition when you are repeating yourself in two or more separate use cases
- Use `<<generalization>>` when you are describing a variation on normal behaviour, or inheritance relations
#### Relation: `<<extend>>`
- Model optional system behaviour and conditions
- Add behaviour to the base use case
- Depicted with a directed arrow with a dotted line
	- Tip of the arrow points to the base use case and child use case is connected at the base of the arrow

![[Pasted image 20231012102414.png]]

![[Pasted image 20231012103243.png]]
#### Relation: `<<include>>`
- Put common event flows into a use case and then include it into the behaviour of the (base) use case to avoid repetitive descriptions
- Simplifies large use cases by splitting them into several use cases
- Represents common parts of the behaviours of other use cases
- Depicted with a directed arrow having a dotted line. Tip of arrowhead points to the child use case and the parent use case is connected at the base of the arrow

![[Pasted image 20231012103222.png]]

![[Pasted image 20231012103258.png]]

#### Relation: `<<generalization>>`
- Parent-child relationship between use cases where the child use case inherits behaviour and meaning from the parent use case
- Directed arrow with a triangle arrowhead. The child use case is connected at the base of the arrow. The tip of the arrow is connected to the parent use case

![[Pasted image 20231012103445.png]]

![[Pasted image 20231012103503.png]]

### Boundary
The system boundary is optional. Use cases are inside the systems and actors are out outside the system

![[Pasted image 20231012103830.png]]

## Use Case Diagram
#### Tips:
- Structure and organise the use case diagram from the perspective of actors
- They should start off simple and at the highest view possible before becoming more refined and detailed
- Base them upon functionality and focus on the  **what** not the *how*

#### Specification
A method to describe the *interactions between users and a system* using a *graphical model* and *structured text* using 2 elements:
1. **Actors**: A person, system, or organisation that interacts with the system
2. **Scenarios**:
	- Structure form of user story
	- Specific sequence of actions and interactions between actors
Captures the **FUNCTIONAL** requirements

#### Format
**Name**: Name of use case
**Brief Description**: Role and purpose of the use case
**Flow of Events**: What the system does in regard to a use case scenario. Write the description so that the customer can understand it
- Can include basic flow, alternative flows and sub-flows
**Key Scenarios**: Description of the most important or frequently discussed scenarios
**Special Requirements**: Description that collects all of the requirements of the use case that are not considered in the use-case model
**Preconditions**: Constraints on the system when the use case starts
**Post-Conditions:** Constraints on the system when the use case ends
**Extension Points**: List of locations within the flow of events of the use case at which additional behaviour can be inserted by using extend relationship
### Examples

![[Pasted image 20231012110256.png]]
![[Pasted image 20231012110320.png]]

### Exercise: SmartBank
![[Pasted image 20231012111234.png]]

1. Draw the first diagram to depict the entire system
![[Pasted image 20231012111339.png]]
2. Draw the second diagram to explain a critical process of the system e.g. deposit and transfer money
![[Pasted image 20231012111429.png]]
