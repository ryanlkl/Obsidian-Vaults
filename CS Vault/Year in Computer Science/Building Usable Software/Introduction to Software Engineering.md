# What is Software Engineering
****
Software engineering is an **engineering discipline** concerned with the **cost-effective design, build and test** of large and complex software intensive systems.

![[Screenshot 2023-09-28 122806.png]]
****
### What does Software Engineering focus on?
- **Real-world goals** for services provided and constraints
- **Precise specification of systems structure and behaviour**, and the implementation of these specifications
- **Activities required** in order to develop based on requirements and real-world goals
- **Evolution** of systems over time
- **Processes, methods and tools** for developing software-intensive systems in an economical and timely manner
****
### Why is Software Engineering important?
Software engineering **produces reliable and trustworthy systems** economically and quickly. They also **provide methods and techniques** for professional development of software systems.

| **Engineer**                       | **Developer**                                      |
| ------------------------------ | ---------------------------------------------- |
| Develops as well               | Narrower in scope than Engineer                |
| Broad knowledge base           | Creative approaches                            |
| Systematic development process | Write code to implement specific functionality |
|                                | Solve specific problems                        |                               |                                                |
****
##### Software Engineer responsibilities
- **Design, build and maintain** software systems
- **Write and test** code
- **Meet** with stakeholders, third party vendors, security specialists, and other team members
****
## Software Engineering Process
Structured set of activities required to develop a software system. It involves **four** activities:
1. *Specification*
	Defining the **main functions** of the software and constraints.
2. *Design and implementation*
	Design of a **system to meet the requirements**
3. *Verification and validation*
	The system does what the **customer wants**
4. *Evolution*
	Modifying the system in **response to changing customer needs**
****
# Software Development Life Cycle (SDLC)

![[Screenshot 2023-09-28 141921.png|350]]

- **Systematic process** to develop high-quality software
- Produce software that **meets requirements**
- Defined **phases** with their own processes
- Cycle of **planning, design, and development**
- Minimises the development risks and cost
****
**Advantages**
- Improves efficiency and reduces risks
- Reduces overlapping responsibilities
- Facilitates communication among stakeholders
- Respond to changing requirements

# Life Cycle Phases
### Phase 1: Planning
![[Screenshot 2023-09-28 164108.png|400]]
##### Requirements:
- Gathered
- Analysed
- Documented
- Prioritized
### Phase 2: Analysis
![[Screenshot 2023-09-28 164318.png|400]]
##### Architecture:
Development using the SRS document
### Phase 3: Design
![[Screenshot 2023-09-28 164405.png|250]]
### Phase 4: Testing
**Code** is tested to ensure stability, security, and the requirements of the SRS.
**Bugs** are reported, tracked, fixed, and retested
### Phase 5: Deployment
![[Screenshot 2023-09-28 164442.png]]
### Phase 6: Maintenance
![[Screenshot 2023-09-28 164450.png]]
# Models
## Waterfall Model
![[Screenshot 2023-09-28 165102.png|450]]
### Characteristics
- **Sequential approach**: each activity is represented as a separate phase and involves feedback from one phase to another
- Used when the **requirements** are **well-understood** and **changes** will be fairly **limited** during the design process
### Phases
#### Phase 1: Requirements Definition
##### What is the system about?
Process of establishing **what services are required** and the constraints on the system's operation and development.
#### Phase 2: System and Software Design
##### How the requirements can be realized?
Description of the **structure of the software to be implemented**
(e.g. data models, interfaces and algorithms)
#### Phase 3: Implementation and Unit Testing
**Implementation:** Executable code
**Unit Testing:** Individual components tested independently
#### Phase 4: Integration and System Testing
**System Testing:** Testing the system as a whole.
**Acceptance Testing:** Use customer data to test the system.
#### Phase 5: Operation and Maintenance
- **Deployment** of the software
- **Continuous testing** maintenance
- Trigger for software evolution
	- (new features, evolved versions)
### Pros and Cons

| **Advantages**                                                       | *Disadvantages*                                                  |     |     |     |     |     |
| ---------------------------------------------------------------- | -------------------------------------------------------------- | 
| **Save time** since the activities are planned and scheduled already | **Lack of flexibility** to respond to changing requirements        |     |     |     |     |     |
| Examples are: embedded, critical and large software systems      | **A phase has to be completed** before moving on to the next phase |     |     |     |     |     |
## Incremental Development
![[Screenshot 2023-09-28 165454.png|500]]
### Characteristics
- Develop an **initial implementation**, get **user feedback** and **evolve** it through several version
- **Requirements** are likely to **change** during the development process
	- e.g. business systems and software products
- **High-priority requirements** are **included in early increments**
- **Early increments act as prototype** to help elicit requirements for **later**
- **Feedback** from customer is **incorporated in the next version**
### Pros and Cons

| **Advantages**                                     | *Disadvantages*          |
| ---------------------------------------------- | ---------------------- |
| Cost of implementing changes is reduced        | Process is not visible |
| Easier to get customer feedback on development | System structure tends to degrade as new increments are added  |
| Rapid delivery and deployment of software                                               |                        |

## Spiral Model
### Characteristics
- **Focus on risk assessment and minimising project risk** by breaking a project into **smaller segments**
- Each cycle passes through the **same sequence** of steps
**Identify Objectives:** Specific requirements are identifies
**Risk Assessments and reduction:** Risks are assessed and activities put in place to reduce the key risks
**Development and validation:** A generic development model is chosen for the system
**Planning:** The project is reviewed and the next phase of the spiral is planned
### Pros and Cons

| **Advantages**                                          | *Disadvantages* |
| --------------------------------------------------- | ------------- |
| Development is fact and features can be added later | **Costly** in term of development              |
| Avoidance of possible risk                          | **Not appropriated for low-risk** projects              |
| **Suitable for high-risk** (critical) and large sized projects                                                    |Depends on the risk analysis phase               |
********
## Component-based Development
### Characteristics
- Focus on the design and development of reusable components
- Uses OOP technologies
- Components and classes encapsulate data and algorithms

### Steps
**1.** Identify all the required candidate components
	- i.e. classes
**2.** Reuse components from previous projects. If not, build or create the component as per requirement
**3.** Repeat steps **1 and 2** for n iterations where n is the number of cycles required to develop the complete application

| **Advantages**                                                        | *Disadvantages*                |
| ----------------------------------------------------------------- | ---------------------------- |
| Break the monolith into components, using consumer/producer model | Component integration issues |
| Reusable/shared libraries                                                                  |                              |


## Agile Model
![[Screenshot 2023-09-28 174627.png|350]]
**Individuals and interactions** over processes and tools
**Working Software** over comprehensive documentation
**Customer Collaboration** over contract negotiation
**Responding to change** over following a **plan**
### Characteristics
- Breaking project phases
- Cycle through plan, execute and evaluate
### Pros and Cons

| **Advantages**                   | *Disadvantages*                                      |
| ---------------------------- | -------------------------------------------------- |
| Flexibility and adaptability | Difficult to implement in larger organisations     |
| Faster time to market        | Lack of documentation                              |
| Encourages collaboration     | Project's scope expands beyond original parameters |
| Increase project visibility  |                                                    |
| Project risk reduction                             |                                                    |


## Scrum Development
![[Screenshot 2023-09-28 174843.png|500]]
### Characteristics
- **Sprints are fixed** in length (generally 2-4 weeks)
- **Product backlog** is the **starting point** for planning
- **Selection phase** involves selecting features and functionalities from the product backlog
- Team organize themselves to develop the software and communicate with the customer via the **Scrum Master**
- After the sprint, **work is reviewed** and presented to stakeholders
### Pros and Cons

| **Advantages**                                     | *Disadvantages*                                   |
| -------------------------------------------------- | ------------------------------------------------- |
| **Short iterations** allow quick solutions             | All members **equally skilled and committed**         |
| **Responsive to changes** as given regular feedback    | Daily Scrum **meetings may drain energy**             |
| **Economic and effective**                             | **Increase time to market** due to no strict deadline |
| **Individual contributions noticed** in Scrum meetings | **Not suitable for large products**                   |                                                   |                                                   |