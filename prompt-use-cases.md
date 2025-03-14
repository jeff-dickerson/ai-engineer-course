# Prompt Use Cases
Prompt examples I've used in my workflow, some from actual cases (shared by their developers) and hypothetical prompts to demonstrate different prompt engineering techniques. More prompts will be added over time.

- [Project Documentation](#project-documentation)
    - [Problem Statement: What you are solving](#problem-statement)
    - [Core Requirements: List of project essential elements](#core-requirements)
    - [Project Management Tracking: Track the progress of tasks](#project-management-tracking)
    - [Business Reqs & Product Reqs: Comprehensive requirements documentation](#create-business-reqs-&-product-reqs)


- [Real-world use case prompts](#real-world-use-case-prompts)
    - [Finance: vendor management](#finance-function)
    - [Cursor: Task-or-not classifier](#cursor-task-or-not-classifier)
    - [Grab: Data entity classification](#grab-data-entity-classification)
    - [Pinterest: Text-to-SQL](#pinterest-text-to-sql)
    - [Thoughtworks: Co-pilot for product ideation](#thoughtworks-co-pilot-for-product-ideation)
    - [Whatnot: Content moderation](#whatnot-content-moderation)




## Project Documentation
This prompt sequence is for creating project documentation and developer planning for sprint.
- **High level architecture**
- **Initial set of user stories**
- **Project management tracking**

### Problem Statement

```
Sufficiently describe problem you are solving in steps then ask this prompt:

"Generate a short problem statement that describes this project in sufficient 
detail that I can then derive a set of core requirements for this project."

```

### Core Requirements 

```
"Generate a set of core requirements for this problem statement 
Focus on the aspects most likely to impact a chosen architecture.  
Keep the requirements simple.  *Optional: We do not need any data 
storage or advanaced security, this is an MVP*"  Add a text document 
with your preferred core tech stack.
```




"Recommend a solution for the stated problem statement and core requirements.  Use only the core technology stack I provided, unless some functionality cannot be supported by it.  Do not generate any code.  Just describe the solution and components and relationships.  Conduct research on the internet if needed to understand how these technologies work together"


### Create a Project Plan

```
"Generate a project plan for this. I need to deliver this tool in 3 weeks. 
Be sure to take the problem, requirements and proposed solution into account.
The team works <fill in #> days per week.  The following resources will be 
committed to this project: one product manager, one developer, one ml engineer, 
and one tester.

Create a very very detailed markdown checklist of all of the stories for this project
plan, with one-story-point tasks (with unchecked checkboxes) that break down each
story.  It is critically important that all of the details to implement this are
in this list to autonomously create this application, so be sure not to miss any
details whatsoever, no matter how much time and thinking you must do to complete
this very challenging but critically important task.


I want to start coding by day <input #>.  I want to follow an iterative 
process, with 1 week sprints."
```

### For Project Management tracking (Jira)

```
"Generate Jira tickets for all the tasks that should be assigned to sprint
number 1 based on the project plan.  Be sure to include all the information
a developer would need in order to satisfy the ticket, without having to go 
back and review the problem statement, requirements or proposed solution.

Include relevant details in tickets of any design decisions - such as technologies and versions, 
names and roles of components, etc. - we've made in the proposed solution that could help 
guide the ticket implementator in developer an app thats an in alignment with our chosen design.  

The first developer ticket should be setting up the initial project, including all 
dependencies. Explicitly stated the following that ticket: Verify the compatibility
 of all required libraries to avod dependency conflicts."
```


### Create Knowledge Base Documentation

```
"Create a simple web page that I can download that contains the problem statement.  
The page title should be <select project title name>."
```


### Create Business REqs Doc & Product REQs Docs
[Senior Technical Product Manager prompts for comprehensive PRDs and BRDs](https://chatgpt.com/share/67be0a59-e484-800d-a078-346b2c29d727) (Shared by Kevin Leneway)

```
I want your help to create enhanced prompts that can help a very senior Technical
 Product Manager create detailed, comprehensive PRDs and BRDs. 

Here is an example of an "enhanced prompt":

Original: Develop a comprehensive strategy for Microsoft 
entering the personalized medicine market by 2027.

Enhanced: 

Develop a comprehensive strategy for Microsoft entering 
the personalized medicine market by 2027.

Begin with:
1. A Blue Ocean Strategy canvas
2. Apply Porter's Five Forces to identify competitive pressures

Next, conduct a scenario planning exercise with four 
distinct futures based on regulatory and technological variables.

For each scenario:
- Develop strategic responses using the Ansoff Matrix

Finally, apply the Three Horizons framework to:
- Map the transition pathway
- Identify potential disruptive innovations at each stage



Notice that in the enhanced version, the prompt specifies multiple real-world analytical frameworks that must be applied sequentially.

Please come up with "enhanced prompts" for the following three scenarios:

Scenario One: I am a Senior Product manager and I want to create a Business Requirements Document (BRD). Here are the high-level specs for this product: <SPECS GO HERE>

Scenario Two: I am a Senior Product manager and I want to create a Product Requirements Document (PRD). Here are the business requirements for this product: <BRD GOES HERE>

Scenario Three: I am a Senior Product manager and I want to create a detailed list of one-story-point stories to create a product that is defined in the following PRD: <PRD GOES HERE>

Create three enhanced prompts for these three scenarios, and be sure to use multiple real-world analytical frameworks for each of these scenarios.
```

## Real world use case prompts


### Finance function

Here's a step-by-step process that allows a user to interact with a Large Language Model (LLM) to work through the vendor master data setup and maintenance workflow. The process includes well-thought-out prompts and user instructions to guide the interaction.

```
  Step 1: Introduction to the Process

    Instruction to User:
        "Welcome! This process will guide you through setting up and maintaining vendor master data, managing approval workflows, and executing changes automatically in your systems. You'll interact with an LLM to receive guidance, generate ideas, and ensure all steps are covered."

    Prompt 1:
        "Please describe your current vendor master data process, including any pain points, inefficiencies, or areas where you think improvements are needed."

    Step 2: Requirements Gathering & Analysis

    Instruction to User:
        "Next, we'll gather and analyze the requirements for your vendor master data process. Please follow the prompts to ensure all aspects are covered."

    Prompt 2:
        "What are the key data elements required for vendor creation, modification, and deletion in your system? Please list mandatory fields, validation rules, and any compliance requirements."

    Prompt 3:
        "Who are the primary stakeholders involved in the vendor master data process (e.g., procurement, finance, IT)? Describe their roles and responsibilities."

    Step 3: Designing the Approval Workflow

    Instruction to User:
        "We'll now design the approval workflow. This includes mapping out the approval stages, notifications, and any exception handling."

    Prompt 4:
        "Please outline the steps involved in your current approval workflow for vendor creation, change, and deletion. Include the stages of approval, who is responsible for each stage, and any conditions that trigger specific actions."

    Prompt 5:
        "What notifications and reminders should be included in the workflow? Specify when these should be triggered and who should receive them."

    Prompt 6:
        "Describe any exceptions in your workflow, such as urgent vendor setups or changes. How should these be handled?"

    Step 4: Tool Selection and Configuration

    Instruction to User:
        "Let's discuss the tools and systems you'll use to manage this workflow. Consider integration points and automation needs."

    Prompt 7:
        "Which tools or platforms are you considering for managing your vendor master data workflow (e.g., SAP MDG, Oracle)? Describe their key features that align with your needs."

    Prompt 8:
        "Identify the systems that need to be integrated with your vendor master data workflow (e.g., ERP, procurement systems). What data flows and integration points are necessary?"

    Prompt 9:
        "How would you like to automate the execution of changes in your systems? Describe any rules or conditions that should trigger automatic updates."

    Step 5: Testing and Validation

    Instruction to User:
        "Testing is crucial to ensure that your workflow operates as intended. Let's plan the testing phases and validation steps."

    Prompt 10:
        "Describe the testing plan for your vendor master data workflow. How will you conduct unit testing, end-to-end testing, and user acceptance testing (UAT)?"

    Prompt 11:
        "What criteria will you use to validate that the workflow is functioning correctly? Consider both technical and business perspectives."

    Step 6: Training and Documentation

    Instruction to User:
        "Effective training and documentation will ensure that all users are comfortable with the new process. Let’s plan this aspect."

    Prompt 12:
        "What training methods will you use to educate users on the new vendor master data workflow? Consider hands-on workshops, user guides, and online modules."

    Prompt 13:
        "What documentation will you create to support the workflow? Ensure that it covers roles, processes, and system configurations."

    Step 7: Deployment and Go-Live

    Instruction to User:
        "It's time to prepare for deployment. We’ll start with a pilot phase and then roll out the workflow across the organization."

    Prompt 14:
        "How will you manage the pilot phase of your vendor master data workflow? Identify the group of users involved and how you will gather feedback."

    Prompt 15:
        "Describe your plan for full deployment. How will you ensure a smooth transition and minimal disruption to ongoing operations?"

    Step 8: Ongoing Maintenance and Optimization

    Instruction to User:
        "The final step involves maintaining and optimizing the workflow over time. Continuous improvement is key."

    Prompt 16:
        "How will you monitor the efficiency of the vendor master data workflow? What metrics will you track, and how will you identify bottlenecks?"

    Prompt 17:
        "Describe the process for optimizing the workflow based on feedback and performance metrics. How will you manage changes and updates?"

    Step 9: Governance and Reporting

    Instruction to User:
        "Governance and reporting will ensure that the workflow remains compliant and effective. Let's finalize these details."

    Prompt 18:
        "What governance framework will you establish for the vendor master data workflow? Consider audit trails, reporting tools, and oversight committees."

    Prompt 19:
        "What reports will you need to generate from the workflow? Describe the key data points and metrics that should be included."

    Conclusion

    Instruction to User:
        "Congratulations! You’ve worked through the entire vendor master data setup and maintenance process. Review the responses and use them to guide your implementation."

    Prompt 20:
        "Would you like to revisit any part of the process for further refinement? If so, specify the step or area you'd like to explore in more detail."


```

This series of prompts and instructions will guide a user through the entire process of setting up and maintaining vendor master data using an LLM, ensuring that every aspect is carefully considered and executed.


