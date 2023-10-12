---
Module: Building Usable Software
Date: 12-10-2023
Topic: Activity Diagrams
---
# What are activity diagrams?
Show dependencies and coordination between activities within the system
- How events in a single use case related to one another
- How use cases coordinate to represent business workflow
Describe the parallel, branched and concurrent flow of the system. Uses:
- Modelling business requirements
- High level understanding of the system's functionalities
- Show the constraints, conditions and logic behind algorithms
### Elements
**Action**: A task to be performed
**Control Flow**: Execution sequence
**Initial Node**: Start of the flow
**End Node**: Terminates the activity
**Decision Node**: Represent a test condition to ensure that the control flow or object flow only goes down one path
**Merge node**: Bring back together different decision paths that were created using a decision-node
**Fork node**: Splits behaviour into set of parallel or concurrent flows
**Join node**: Brings together set or *forked* nodes

![[Pasted image 20231012133245.png]]

## How to create Activity Diagrams.
1. Identify candidate use cases
2. Identify pre and post conditions for use cases
3. Model workflows between/within use cases
4. Model complex workflows in operations on object
5. Model complex activities in a high-level diagram

![[Pasted image 20231012134550.png]]
### Examples
##### Processing Orders
###### Description
Once the order is received, the activities are split into two parallel sets of activities. One side fills and sends the order while the other handles the billing.

On the Fill Order side, the method of delivery is decided conditionally. Depending on the condition either the Overnight Delivery activity or the Regular Delivery activity is performed.

Finally, the parallel activities combine to close the order.
![[Pasted image 20231012140312.png]]

##### University Enrolment
###### Description
- Applicant wants to enrol in the university
- Applicant hands in an Enrolment Form
- Registrar inspect the form
- Registrar determines whether forms are filled out correctly
- Registrar informs students to attend overview presentation
- Registrar helps student enrol in seminars
- Registrar asks student to pay initial tuition fee
![[Pasted image 20231012140845.png]]

## Swimlane
This is a method to **group activities** performed by the same actor on an activity diagram or a single thread
#### Example
##### SmartBank
![[Pasted image 20231012140949.png]]

