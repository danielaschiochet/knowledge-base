# Course Introduction – Analysis and Management of Production Systems

## Course Structure
This course is divided into two main parts:
- **Part 1**: Operations Strategy (covered by Prof. Cantamessa)
- **Part 2**: Manufacturing Systems Modeling and Analysis (this module)

The focus of this second part is on **modeling, analyzing, and evaluating production systems**, with particular attention to **manufacturing systems**.

---

## Instructor and Organization
- **Instructor**: Prof. Giulia Bruno  
  Associate Professor, Department of Management and Production Engineering
- Lessons are recorded and uploaded weekly.
- Exercises and practice sessions are supported by a teaching assistant.

---

## Learning Objectives
At the end of the course, students will be able to:
- Analyze and describe manufacturing systems
- Identify critical points such as bottlenecks and unbalanced resources
- Compute key performance indicators (KPIs)
- Evaluate production system performance using analytical models
- Understand when simulation is required instead of analytical models

---

## Course Topics Overview

### 1. Process Representation Formalisms
Tools to represent **material flows**:
- Flow Process Chart
- Value Stream Mapping (VSM)
- IDEF0

These formalisms are essential for describing production systems clearly and consistently.

---

### 2. Manufacturing System Modeling
Core of the course, based on **queueing theory applied to production systems**:
- Factory models and terminology
- Key KPIs and basic formulas
- Single workstation models
- Serial production lines
- Networked systems
- Multi-product systems
- Batch production

The course starts **from scratch**, introducing a unified terminology.

---

### 3. Simulation and Advanced Topics
When systems become too complex:
- Analytical formulas are insufficient
- Discrete-event simulation is introduced

Additional topics:
- Industry 4.0 and Industry 5.0
- Machine learning applications in manufacturing

Simulation tools are demonstrated but **not required to be learned**.

---

## Exam Structure
- **Written exam** (2 hours)
- Includes:
  - Multiple-choice theoretical questions
  - Numerical exercises
- No supporting material allowed
- All necessary formulas are provided directly on the exam paper

Mock exams and examples are provided during the course.

---

## Reference Materials
- **Operations Strategy** (Part 1): Lewis
- **Manufacturing Systems Modeling and Analysis** (Part 2): Carín & Feldman, Springer  
  (freely available online; course follows from Chapter 2 onward)

For process representation formalisms, slides are sufficient; additional sources may be consulted.

---

## Scope of the Course

### Type of Production
The course focuses on **discrete manufacturing systems**:
- Automotive
- Electronics
- Mechanical production

Continuous processes (e.g. chemical plants) are **excluded**.

---

## Manufacturing System Elements Considered
Due to model complexity, the course focuses on:
- Products (as analysis units)
- Operations (manufacturing activities)
- Workstations and machines

Elements **not explicitly modeled**:
- Operators
- Transportation systems
- Warehousing
- Maintenance logistics

---

## Production System Analysis Framework
The course follows four logical steps:

1. **Analyze**
   - Understand system structure
   - Identify elements and flows
2. **Model**
   - Apply mathematical and queueing models
3. **Evaluate**
   - Compute KPIs
4. **Interpret**
   - Identify critical points and improvement opportunities

---

## Key Performance Indicators (KPIs)

### Throughput (TH)
Number of products produced per unit time:
```
TH = items / time
```
Objective: **maximize**

---

### Cycle Time (CT)
Average time a product spends in the system:
```
CT = exit time − entry time
```
Objective: **minimize**

---

### Work In Process (WIP)
Number of items inside the system:
- being processed
- waiting in queues

Objective: **minimize**

---

### Utilization (U)
Fraction of time a resource is busy:
```
0 ≤ U ≤ 1
```
Objective: **maximize**, but excessive utilization increases waiting and WIP

---

## Critical Concepts
- **Bottleneck**: slowest resource limiting throughput
- **Critical path**: longest path determining cycle time
- **Unbalanced resources**: uneven production rates causing congestion

High utilization leads to increased queues and waiting times, requiring trade-offs.

---

## Final Remarks
This course emphasizes:
- time-based performance evaluation
- system-level thinking
- analytical rigor

Cost analysis and managerial decision-making are **outside the scope**, but KPIs studied here are foundational for them.
