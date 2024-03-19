#### 1 - Know the principles of Object Oriented programming (inheritance, encapsulation etc.)
- **Link**: OO_Principles.pdf
- **Inheritance**: Ability of a class to inherit function implementation from another class.
    - *Benefit*: Software reusability.
        - Reuse code and effort already invested in writing and testing.
    - *Downsides*:
        - Class hierarchy based on a single criterion.
            - If a system has several aspects of functionality that do not fit into a single hierarchy, Need to subclass from several superclasses for multiple aspects of functionality. (multiple inheritance)
            - Superclasses may come from different class hierarchies.
            - Compiler cannot enforce semantics.
        - Diamond Problem:
            - Occurs when a class inherits from two classes that have a common ancestor.
            - Ambiguity in inherited methods or attributes from two classes with a common ancestor, leading to potential bugs.

- **Polymorphism**: Ability to provide multiple implementations for a single function declaration. Subclass should be able to substitute for its superclass.
    - *Benefit*:
        - Delivers more succinct code.
            - Without polymorphism, different names for functions would be needed.
            - Requires switch statements to check conditions, leading to more code and potential bugs.
    - Downside:
        - Complicates testing.
            - (For example, with an array) Statically, you cannot determine the content of an array (depends on user interface or network decision).
            - Need to consider all possibilities, leading to a huge number of permutations.
            
- **Encapsulation**: Hiding an object's state so that it cannot be accessed directly, requiring functions to check for user permission or privilege.
    - *Benefit*:
        - Increase reliability by ensuring that the object's state is only modified through controlled methods.
    - *Downside*:
        - Complicates testing by requiring more complex test cases to ensure that the encapsulated state is being correctly modified and accessed.

---

#### 2 - Be able to give an overview of the Extreme Programming process from the survey of agile processes
- **Link**:  https://userweb.cs.txstate.edu/~rp31/papers/AgileComp.pdf (3.1.1 Process diagram)

![Life Cycke of XP Process](https://i.imgur.com/QkHvrll.png)

- **Extreme Programming (XP) Process**: involving iterative development and following an agile approach
    - *Exploration Phase*:
        - Gather stories or scenarios from the client and prioritize functionalities for each increment.
    - *Incremental Development*:
        - Develop increments based on priorities.
        - Merge branches into a common code base (e.g., master branch in a version control system like Git).
    - *Testing*:
        - Perform unit/regression/etc. testing after each iteration to ensure the code functions correctly.
    - *Pair Programming*:
        - Simple static code analysis by having another developer review your code, reducing bugs.
        - The process continues with small, updated releases until the final release.
    -  *After the final release, the software enters a maintenance phase where it is no longer actively maintained*.
	
---

#### 3 - Know the principles of Model-Driven development and its advantages
- **Link**: https://userweb.cs.txstate.edu/~rp31/slidesSEP/introClassesAttr.pdf (only talked about 1st slide)

![Model-driven](https://i.imgur.com/OWp7oQL.png)

- **Additional note**: LiftControlCaseStudy.pdf
    - *Definition*: The system is defined as a critical specification, typically a design of the software system.
    - *Specification*: This specification is often represented using UML diagrams, such as:
        - **Class diagrams**: Describe the structure of the system.
        - **State charts**: Describe the behavior of the system.
    - *UML (Unified Modeling Language)*: the preferred language for design, as it has become widely adopted.
    - *Sequence Diagrams and Activity Diagrams*:
        - While class diagrams are primarily used for structure and behavior, other UML diagrams like sequence diagrams and activity diagrams can also be used.
    - *Process*:
        - Starts by creating scenarios, which are then used to create sequence diagrams. From sequence diagrams, state charts are created.
        - Activity diagrams are used to describe the internal control flow of individual methods in a class.
    - *Execution of UML Specification*:
        - The system is defined as an executable specification, which is an object-oriented analysis model.
        - The system is validated at the analysis model level.
        - A software and execution architecture is defined as a set of class templates in an object-oriented programming system.
        - The executable system is realized by compilation of the validated analysis model to the software execution architecture.
    - *Scale Management*:
        - MDD is used to help manage the scale of software systems, especially as they become large (e.g., over 100,000 or 500,000 lines of code).
    - *Testing*: MDD aims to reduce testing time by checking design specifications against requirements to avoid obvious mistakes.
    - *Verification vs. Validation*:
        - Verification implies static analysis of the system against requirements.
        - Validation implies checking the system against the real world, often through testing.
    - *Executable Specification*:
        - While an executable specification can be seen as a form of validation due to its executable nature, some argue that it's still primarily a form of verification until actual code is generated.
    - *Benefits of Validated Design*:
        - Helps manage scale and complexity, reducing the number of test cases needed.
        - Allows for early identification and removal of deviations from the design.
        - Drastically reduces the number of potential bugs in the system.
    - *Software Execution Architecture*:
        - Defines the setup and templates for an object-oriented programming system.
        - Enables easy mapping from a class diagram to a skeleton of the code.
    - *Compilation of Devalued Nets*:
        - Realizes the executable system by compiling state charts or similar structures to the software execution architecture.
        - This process is challenging and is only practical for niche problem domains.

---
		
#### 4 - Know the Model-View-Controller (MVC) architectural style - its constraints and benefits
![MVC Diagram](https://i.imgur.com/ScUPwVz.png)

- **Link**: MVC Diagram.jpg (replicate diagram)
    - *Objective*: Replicate the MVC diagram and describe its components and communication types.
    - *Components*:
        - Model: Represents the data and business logic of the application.
        - View: Represents the user interface components.
        - Controller: Acts as an intermediary between the Model and View, handling user input and updating the Model.
    - *Communication Types*:
        - Method invocations: Used for procedure calls.
        - Events: Used for event notification, where the Model maintains a list of listeners and notifies them of changes.
    - *Constraints*:
        - Model updates the View via event-based notification.
        - View can only perform state queries on the Model, not directly change its state.
    - *Benefits*:
        - Allows changing the View without touching the Model's source code or shutting down the Model.
    - *Rationale*:
        - Design and architecture are sets of constraints with a rationale for their use.
        0 Constrained communication ensures benefits of the architecture style.
		
- **Remeber to include different types of communication when answering the midterm.**	

---

#### 5 - Know how to implement event-based notification in Java
- Link: https://userweb.cs.txstate.edu/~rp31/papers/Model-View-Controller.PDF (Listing 4: The AbstractModel class)
	- *Implementation*: To implement event-based notification in Java, you can use an abstract model class. In the abstract model class: 
		- Define a method (e.g., notifyChange) for sending events to listeners.
		- Maintain an array or collection of listeners.
		- Iterate over the listeners in a loop and invoke a method on each listener to notify them of the event.
		- This approach ensures that changes in the model are communicated to registered listeners using events, allowing for decoupling between components.
		
#### 6 - Know the syntax of the class diagram language (class representations, various kinds of associations)

- Class representations:
        Classes are represented as rectangles with three compartments. (class name, attributes, methods)
    - Associations:
        - Associations represent relationships between classes.
		- Association lines connect two classes and can have labels indicating the nature of the relationship (e.g., "has-a", "is-a").
		- Multiplicity notation (e.g., "1", "*", "0..1") can be used to indicate the number of instances of one class related to another.
            - ```One-to-One (1..1): A Person has one Passport, and a Passport belongs to one Person```.
			- ```One-to-Many (1..*): A Teacher teaches multiple Students, but a Student has only one Teacher```.
			- ```Many-to-One (*..1): Multiple Employees work in one Department, but each Employee works in only one Department```.
			- ```Many-to-Many (*..*: A Student can enroll in multiple Courses, and a Course can have multiple Students```.
	
	- Relationship: 
	    - Association: Represents a relationship between two classes. (Person knows Address)
			
            - ```Indicates that objects of one class are connected to objects of another class.```
		- Aggregation: Represents a "whole-part" relationship where the part can exist independently of the whole. (Car has Engine)
			- ```Indicates a weaker form of ownership compared to composition.```
		- Composition: Represents a stronger form of aggregation where the part cannot exist independently of the whole. (House has Room)
			- ```Implies exclusive ownership, meaning a single whole can own multiple parts, but each part belongs to only one whole.```
		- Dependency: Represents a weaker form of relationship where one class depends on another class. (Car depends on Gas)
			- ```Indicates that a change in one class may affect another class.```
		- Inheritance: Represents an "is-a" relationship between a base class (superclass) and a derived class (subclass). (Dog is Animal)
			- ```Indicates that the subclass inherits attributes and behaviors from the superclass.```
		- Realization: Represents a relationship between a class (interface) and its implementation. (Dog implements Animal Sound)
			- ```Indicates that a class implements the behavior specified by an interface.```

---
				
#### 7 - Know the syntax of the statechart diagram language
- *States*:
    - Represent conditions or situations during the life of an object.
    - Shown as rounded rectangles.
- *Transitions*:
    - Represent the change from one state to another.
    - Shown as arrows between states, labeled with the triggering event.
- *Initial and Final States*:
    - Initial states are indicated by a filled circle.
    - Final states are indicated by a circle surrounded by a larger circle.
- *Hierarchical States*:
    - States can be nested within other states to represent complex behavior.
    - Nested states are shown as smaller rectangles within a larger state rectangle.
- *Actions*:
    - Associated with transitions to specify what should happen when a transition occurs.
    - Actions are typically written next to the transition arrow or within the state rectangle.

---

#### 8 - Be able to create a class diagram and a statechart from requirements
- **Link**: LiftControlCaseStudy.pdf,  LibraryExample.doc,  LibraryExample.pdf, ExceptionAndLightBulbClass.pdf
  
	- **Common Mistakes in Class Diagrams**:
		- Not using proper notation for relationships (e.g., association, inheritance).
		- Omitting important class candidates from the diagram.
		- Improper use of generalization (inheritance) relationships.
	- **Common Mistakes in State Charts**:
		- Confusing state charts with flow charts.
		- Not understanding that nodes correspond to states, which are abstractions of attribute values.
		- Missing annotations on transitions, which represent method invocations and state changes.
	- *Example Requirement*s:
		- Use examples like the control case study, library example, or exception light bulb case to create class diagrams and state charts.
		- Analyze the requirements to identify nouns that serve as class candidates.
	- *Creating Class Diagrams*:
		- Properly represent relationships between classes (association, aggregation, composition).
		- Use generalization (inheritance) relationships correctly.
		- Ensure all important class candidates are included.
	- *Creating State Charts*:
		- Understand that nodes represent states, not individual attribute values.
		- Avoid repetition of states in the state chart.
		- Use annotations on transitions to indicate method invocations and state changes.
	- *Testing Based on State Charts*:
		- Use state charts to generate test cases that cover different sequences of method invocations.
		- Ensure that test cases achieve branch coverage to verify implementation against design.
	- *Overall Understanding*:
		- Class diagrams and state charts are used to visually represent the structure and behavior of a system based on its requirements.
		- Proper understanding and application of these concepts are crucial for effective software design and testing.

---
	
#### 9 - Know what is tested in different stages of testing (unit, integration, system, acceptance, regression)
- **Link**: VandV.pdf (Slide 9)
  
    - **Unit Testing**:
        - Exercise a single simple component (e.g., procedure, class).
        - Focus on testing the smallest units of code in isolation.
    - **Integration Testing**:
        - Exercise a collection of interdependent components.
        - Focus on checking the consistency between actual parameters and formal parameters' meanings, ensuring that components communicate correctly.
    - **System Testing**:
        - Exercise a complete, stand-alone system.
        - Different from integration testing, which focuses on interfaces between components.
        - Begins before the system is complete and continues after completion.
        - Typically involves testing via the user interface without running test cases.
    - **Acceptance Testing**:
        - Customer's evaluation of a system. Usually a form of system testing.
        - Done at the side of the client to ensure the system meets their requirements and expectations.
    - **Regression Testing**:
        - Exercise a changed system to ensure that existing functionality still works.
        - Focus on modifications or their impact, including bug fixes, new functionality, or performance improvements.
        - Typically done after every change to the system to ensure that previously working features remain functional.

---
		
#### 10 - Be able to create testcases with a JUnit framework
- **Link**: ExceptionAndLightbulbClass.pdf

    - *Creating Test Cases with JUnit Framework*:
        - Ability to create test cases using the JUnit framework.
        - Test cases should include assert functions to verify expected outcomes.
    - *JUnit Test Case Example*:
        - Example provided in the ExceptionAndLightbulbClass.pdf document.
        - Test cases are implemented using assert functions to check expected outcomes.
        - Understanding what to assert demonstrates knowledge of JUnit functionality.
    - *JUnit Setup and Teardown Functions*:
        - While not explicitly required, understanding of setup, teardown, and test method functions in JUnit can be beneficial.
        - These functions are used to prepare the test environment, clean up after tests, and define individual test cases, respectively.

---
		
#### 11 – Be able to create testcases according to boundary, statement and edge coverage criteria
	
- *Creating Test Cases According to Coverage Criteria*:
    - Ability to create test cases according to boundary, statement, and edge coverage criteria.
    - Focus on edge coverage, which is equivalent to branch coverage in this context.
