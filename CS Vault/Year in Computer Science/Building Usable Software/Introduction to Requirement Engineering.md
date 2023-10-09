### Recap for [[Introduction to Software Engineering]]
`fas:Undo` **Requirements**
					- Gathered
					- Analysed
					- Documented
					- Prioritised

`fas:Undo` **Architecture**
					- Development using the SRS

`fas:Undo` **Design**
					-  Transform requirements into code

`fas:Undo` **Implementation**
					- Code quality

`fas:Undo` **Implementation** Software meets **requirements** and is free of **bugs**

`fas:Undo` **Maintenance** Check for bugs, code improvements, UI, issues, etc.

# What are Software Requirements?
**Software requirements** of the *system services* and *constraints*, generated during the requirements engineering process.
This ranges from high-level abstract statements of a **service** or of a **system constraint** to a *low-level detailed specification*

### General Rule
*Abstract (General)* => *Refine (more detailed and specific)*

# Requirements: "General" Statements
### Sources of requirements:
##### Stakeholders:
- Decision-makers
- End-users
- System administrators
- Engineering
- Marketing
- Sales
- Customer Support
##### Goals/Objectives
Broad, long-term achievable outcomes / Actionable, measurable actions that achieve the goal
##### Application Domain:
- Details of the specific customer problem where the system will be applied
##### Problem to be solved
Details of the specific customer problem where the system will be applied
##### Business Context
How the system interacts and contributes to overall business goals.
##### Stakeholder needs and constraints
Specific needs of people who require system support in their work

# Case Study
## Mentcare System
### What is the mentcare system?

![[Pasted image 20231002170652.png]]

**Patient information system** that is intended for use in clinics. It maintains information about patients suffering from mental health problems and the treatments that they have received.
### Purposes
1. Generate management information that allows health service managers to assess performance against local and government targets
2. Provide medical staff with timely information to support the treatment of patients
### Features
- Individual care management
- Patient monitoring
- Administrative reporting
### Who are the stakeholders?
- Patients with information in the system
- Doctors responsible for assessing and treating patients
- Nurses coordinating consultations with doctors and administer treatments
- Medical receptionists managing patients' appointments
- IT staff responsible for installing and maintaining the system
- Medical ethics manager ensuring the system meets current ethical guidelines for patient care
- Health care managers who obtain management information from the system
- Medical records staff responsible for ensuring system information can be maintained and preserved, and that record keeping procedures have been properly implemented

# Requirements Engineering Process
## Requirements Elicitation

![[Pasted image 20231002172256.png]]

Engineers work with stakeholders to discover or capture requirements:
- Find out about **application domain**
- **Services** that the system should provide
- **Required system performance, hardware constraints**, etc.
- **Information** about existing systems

## Requirements Discovery
### Processes
**Interviews**: structured/unstructured, facilitated meetings
**Stories and scenarios**: 
	*Stories*: High-level description of system use
	*Scenarios*: Parts of the story in more detail (starting situation, normal flow of events, possible issues, concurrent activities, state when the scenario finishes)
**Prototypes**: Small-scale replica of the system, mock-up using paper, diagrams or software
**Observations**: Observing "real world" work and revisiting documentation, manual systems, etc.

## Requirements Classification
**Functional**: Functions of the software
**User Interface**: User and interactions with other hardware or software
**System Features**: Functions of the system
**Non-functional Requirements**: Performance, safety, security, quality

### User and System Requirements
#### User Requirements
Abstract statements of the system requirements for the customer and end-user of the system
#### System Requirements
Detailed description of the functionalities the system is expected to provide to users and the constraints under which it operates

![[Pasted image 20231002173431.png]]

### Functional Requirements (FR)
High-level statements to describe the *functionalities* or *services* the system should provide:
- How the system should react to particular inputs
- How the system should behave in particular situations
The requirements may state what the system should not do.

##### Examples
1. User shall be able to search the appointment lists for all clinics
2. System *shall* generate each day, for each clinic, a list of patients who are expected to attend appointments that day
3. Each staff member using the system *shall*  be uniquely identified by his or her eight-digit employee number

##### Issues in Functional Requirements
**Precision**: Ambiguous requirements may be interpreted in different ways by developers and users
**Completeness**: They should include descriptions of all facilities required
**Consistency**: There should be no conflicts or contradictions in the description of the services
### Non-Functional Requirements (NFR)
These define the **overall qualities or attributes** of the resulting system
- Reliability
- Response Time
- Performance
- Security
- Availability
They also describe the **constraints on the services** offered by the system and may also specify process requirements like specific IDE's or programming languages.
#### Types of NFR

![[Pasted image 20231002190945.png]]

**Product Requirements**: Specify that the delivered product must begave in a particular way
- Execution Speed
- Reliability
**Organisational Requirements**: Consequence of organisational policies and procedures
- Process Standards used
- Implementation Requirements
**External Requirements**: Arise from factors which are external to the system and its development process
- Interoperability Requirements
- Legislative Requirements

#### Examples
Downtime within normal working hours shall not exceed 5 seconds in any one day. *Product*
Users of the Mentcare system shall identify themselves using their health authority identity care. *Organisational*
The system shall implement patient privacy provisions as set out in HStan-03-2006-priv. *External*

#### NFR Dimensions of Dependability

![[Pasted image 20231002191407.png]]

##### Metrics for NFR

![[Pasted image 20231002191432.png]]

# Requirements Prioritization

![[Pasted image 20231002191520.png]]

## Requirements Specification
Translating the information during requirements analysis into a **document** that defines a set of requirements
- **Natural language sentences**: Sentence (#) expresses requirements
- **Structural natural language**: Follow a standard form or template where field provide specific aspects of the requirements
- **Graphical models**: Use to define functional requirements
- **Formal languages**: examples are Abstract State Machines (ASMs), Alloy, B-method, Z-method

##### Structured Specification

![[Pasted image 20231002191853.png]]

#### Use Cases
Kind of scenarios that are described using the Unified Modelling Language (UML). High-level graphical model supplemented by more detailed tabular description.

Includes:
- **Actors**: Users or other systems
- **Use Cases**: Represented in ellipses
- **Interaction** Links actors and use cases

# Requirement Validation
- Discover problems, incompleteness and inconsistencies in the elicited requirements
- Check the system meets the user's needs

##### Issues
- **Lack of Clarity**: Natural language is ambiguous and lacks precision
- **Requirements Confusion**: FR and NFR tend to be mixed up
- **Over-flexibilty**: The same requirements may be described in different ways
- **Others**: Inconsistency, missing requirements, stakeholders' bias, incompleteness, redundancy, irrelevance, and overloaded statements

# Requirement Checking
- **Validity**: Does the system provide the functions which best support the customer's needs?
- **Consistency**: Are there any requirements conflicts?
- **Completeness**: Are all functions required by the customer included?
- **Realism**: Can the requirements be implemented given the available budget and technolgy?
- **Verifiability**: Can the requirements be checked?

### Example:
##### Example 1
**R100**: The screen allows input of the following information: length, temperature and current time
**R100**: The screen allows input of the following information: length *in meters*, the temperature *in C*, and current time *in YYYY-MM-DD HH:MM:SS format*
##### Example 2
**R1000**: The system MUST support a maximum of 10 sensors connected concurrently
**R1010**: The system response time MUST not exceed 10 ms when 20 sensors are connected to it concurrently
##### Example 3
**R1000**: The system MUST support a maximum of *20 sensors* connected to it concurrently.
**R1010**: The REQUIRED maximum output system response time in dependency on the number of sensors connected concurrently is shown in Table 1:

| #     | Sensors Connected | Maximum Response Time (ms) |
| ----- | ----------------- | -------------------------- |
| R1000 | 20                | 10                         |
| R1010      |10                   |5                            |

# Requirements Documentation
- Structured document setting out detailed descriptions of the system's functions, services and operational constrains
- Should include both a definition of **user requirements** and **a specification** of the **system requirements**.
- It is *NOT* a *design document*. It should set **WHAT** the system should do rather than *HOW* it should do it

# Requirements Management and Change
Change is inevitable when building systems:
- The business and technical environment of the system always changes
- Large systems usually have a diverse user community, with many users having different requirements and priorities that may be conflicting or contradictory
### How to manage changes?
- **Traceability**: Keep track of individual requirements
- **Dependency**: Maintain links between dependent requirements
- **Change impact analysis**: Asses the impact of requirements changes
- Establish a formal process for making change proposals and linking these to system requirements