# Course Introduction – Analysis and Management of Production Systems

# Description
Different courses of the Degree in Management Engineering present the broad theme of the production of goods and services from multiple points of view: technological, plant engineering, economic, operational management, and quality

The aim of the course is to provide to the students of the Master Degree in Management Engineering a complementary knowledge, both through the development of new analysis tools and approaches, and their integration in the perspective of contemporary business, characterized by its inclusion in globalized and competitive markets, not only by considering traditional concepts of value and cost, but also new aspects such as the sustainability

# Expected Learning Outcomes

The course aims to develop the ability of students to analyze, evaluate and design a production system, both of manufacturing and services, coherently with the company strategy and organization

This will be obtained by learning new technical skills, by creating connections between skills already developed, and by familiarizing with the most important changes taking place in the production sectors

# Pre-requirements

Knowledge of topics covered in courses dedicated to Production Systems and Production Planning and Contro

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
Written exam, including both the numerical exercises and questions on the theoretical aspects (qualitative and quantitative)
The questions can be open or multiple choice or true/false answer
Numerical exercises and theoretical questions can be integrated in the same exercise
During the written exam it is not possible to consult any support (form, handouts, texts, etc.)

---

## Reference Materials
Slides and notes, available online, on the course page
Suggested reference books:
➢ Curry G.L., Feldman, R.M., "Manufacturing Systems Modeling and Analysis", Springer, 2011
➢ Slack N., Lewis N., "Operations Strategy", Pearson, 2017
Additional material: Internet

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
