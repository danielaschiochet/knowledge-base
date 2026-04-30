# Analysis and Management of Production Systems

# Lesson 01: Formalisms for manufacturing process modeling

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Importance of formalism

Problem of making customers/colleagues with different backgrounds to understand the process to reach the solution of a problem   
Everyone reasons and expresses concepts according to their own cultural background   
V distance of languages

# Communication problem

Metaphor of the swing   
Problem of using words to describe processes   
Importance of being able to formalize a process to have an effective communication

# Importance of processes in production systems

Processes are used to manage a product during its whole Product Lifecycle

Plan   
Design   
Implement   
Support   
Disposal


# Process definition

A process is characterized by a series of activities linked together to provide a certain output given a certain input

### Visual Diagram: Basic Process Definition
- **Visual Element 1 (Left)**: A solid black arrow pointing horizontally to the right. Text positioned directly above the arrow: "Input".
- **Visual Element 2 (Center)**: A solid blue rectangle. Text centered inside the shape: "Process" (in black font).
- **Visual Element 3 (Right)**: A solid black arrow pointing horizontally to the right, originating from the right edge of the blue rectangle. Text positioned directly above the arrow: "Output".
- **Logical Flow**: The "Input" arrow enters the left side of the "Process" rectangle. The "Output" arrow exits from the right side of the "Process" rectangle.

V Representation at various levels of detail   
To represent a process, it is necessary to identify the activities of which it is composed and their sequence

V Activities may be difficult to be identified or separated from the other related activities

# Types of processes

> Information processes: functions that create, manage, process and provide information (e.g. management of a purchase order)   
> Physical processes: processing activities of physical objects (e.g. material flows within a production system)   
Functional processes: functions related to the overall activity of the organization or company (e.g. production of a car, publication of a book,management of an airline)

# Types of formalism

> Depending on the process type, different representation formalism can be used

> Information flows Flow chart, UML Activity diagram, BPMN   
V Material flows Flow process chart, Value Stream Mapping   
V Functional flows IDEFO diagrams

Many variants   
>The same formalism may be used to represent diferent process types

# Flow chart

### Visual Diagram: Flow Chart Symbols Legend
- **Overall Layout**: The diagram is a legend enclosed within a white box with rounded corners and a thin black border. It features a vertical list of five standard flowchart symbols aligned to the left, with their corresponding definitions written to the right.
- **Element 1 (Top)**: A light green oval (ellipse) with a black outline. Associated text to the right: "Start and End".
- **Element 2**: A light peach/beige rectangle with a black outline. Associated text to the right: "Activity".
- **Element 3**: A light pink diamond (rhombus) with a black outline. Associated text to the right: "Decision".
- **Element 4**: A blue parallelogram with a black outline. Associated text to the right: "Input/output data".
- **Element 5 (Bottom)**: A solid black horizontal arrow pointing to the right. Associated text to the right: "Flow control".

# Example: Customer support service

### Visual Diagram: Customer Support Service Flowchart
- **Diagram Type**: Swimlane Flowchart (Cross-functional process).
- **Swimlanes (Horizontal, top to bottom)**: "Customer", "Service Desk", "Technical support".

**Nodes and Process Routing:**
1. **Start**: An oval node labeled "Send request" located in the **Customer** lane. An arrow flows down to the next node.
2. **Activity**: A rectangle labeled "Determine nature of request" in the **Service Desk** lane. An arrow flows right to a decision node.
3. **Decision**: A diamond labeled "Previous incident?" in the **Service Desk** lane. 
    - The **"no"** branch flows to a rectangle labeled "Create new incident record".
    - The **"yes"** branch flows to a rectangle labeled "Review existing incident".
4. **Merge**: Arrows from both "Create new incident record" and "Review existing incident" converge and flow right into a rectangle labeled "Investigation and diagnosis" (all still within the **Service Desk** lane).
5. **Decision**: An arrow flows right from "Investigation and diagnosis" to a diamond labeled "SD able to solve?" in the **Service Desk** lane.
    - The **"yes"** branch flows right to a rectangle labeled "Recovery" in the **Service Desk** lane.
    - The **"no"** branch flows down to a rectangle labeled "Investigation and diagnosis" in the **Technical support** lane.
6. **Technical Support Escalation Path**: From "Investigation and diagnosis" in the **Technical support** lane, an arrow flows right to a rectangle labeled "Recovery". From this "Recovery", an arrow flows back up into the **Service Desk** lane, connecting to "Resolution notification".
7. **Service Desk Direct Path**: From the Service Desk's own "Recovery" node, an arrow flows right to a rectangle labeled "Resolution notification" in the **Service Desk** lane.
8. **Customer Confirmation**: From "Resolution notification", an arrow flows up into the **Customer** lane to a diamond labeled "Confirmed resolution".
    - The **"no"** branch creates a feedback loop, flowing left and down back to the "Investigation and diagnosis" node in the **Service Desk** lane.
    - The **"yes"** branch flows right to a rectangle labeled "Give a rating" in the **Customer** lane.
9. **End of Process**: From "Give a rating", an arrow flows down to a rectangle labeled "Store rating" in the **Service Desk** lane. Finally, an arrow flows right to an oval node labeled "End" in the **Service Desk** lane.

# UML Activity Diagram

### Visual Diagram: UML Activity Diagram Symbols Legend
- **Overall Layout**: The diagram is a legend enclosed within a white box with rounded corners and a thin black border. It features a vertical list of six standard UML activity diagram symbols aligned to the left, with their corresponding definitions written to the right.
- **Element 1 (Top)**: A solid black circle. Associated text to the right: "Initial state".
- **Element 2**: A solid black circle surrounded by an outlined circle (resembling a bullseye). Associated text to the right: "End state".
- **Element 3**: A light green rectangle with rounded corners and a black outline. Associated text to the right: "Activity".
- **Element 4**: A light pink diamond (rhombus) with a black outline. Associated text to the right: "Decision".
- **Element 5**: Two distinct symbols shown side-by-side to represent splitting and merging paths. 
    - The left symbol (Fork) shows one arrow pointing down into a thick black horizontal line, with two arrows pointing down and away from the bottom of the line.
    - The right symbol (Join) shows two arrows pointing down into a thick black horizontal line, with one arrow pointing down from the center of the bottom line.
    - Associated text to the right: "Fork and Join".
- **Element 6 (Bottom)**: A solid black horizontal arrow pointing to the right. Associated text to the right: "Flow control".

# Example: order management

### Visual Diagram: UML Activity Diagram - Order Management
- **Diagram Type**: UML Activity Diagram with Swimlanes.
- **Swimlanes (Vertical, Left to Right)**: "WAREHOUSE", "CUSTOMER SERVICE", "ACCOUNTING".

**Nodes and Process Routing:**
1. **Start**: A solid black circle (Initial state) located at the top of the **CUSTOMER SERVICE** lane. An arrow flows down to the first activity.
2. **Activity**: A rounded rectangle labeled "RECEIVE ORDER" in the **CUSTOMER SERVICE** lane. An arrow flows down to a Fork node.
3. **Fork (Parallel Routing)**: A thick black horizontal line (Fork) in the **CUSTOMER SERVICE** lane. It splits the flow into two parallel paths:
    - **Path A (Physical Fulfillment)**: An arrow flows left into the **WAREHOUSE** lane to an activity labeled "FULFILL ORDER". From there, an arrow flows down to an activity labeled "24 h SHIPPING".
    - **Path B (Invoicing)**: An arrow flows down within the **CUSTOMER SERVICE** lane to an activity labeled "SEND BILL". From there, an arrow flows right into the **ACCOUNTING** lane to an activity labeled "RECEIVE PAYMENT".
4. **Join (Synchronization)**: Arrows from the ends of both parallel paths ("24 h SHIPPING" in the Warehouse lane and "RECEIVE PAYMENT" in the Accounting lane) converge onto a single thick black horizontal line (Join) located in the **CUSTOMER SERVICE** lane. This indicates the process cannot proceed until both the shipping and payment are complete.
5. **Activity**: From the Join node, an arrow flows down to a rounded rectangle labeled "CLOSE ORDER" in the **CUSTOMER SERVICE** lane.
6. **End of Process**: An arrow flows down from "CLOSE ORDER" to a bullseye symbol (End state) located at the bottom of the **CUSTOMER SERVICE** lane.

# Business process model and notation

Based on popular graphical flowcharts:

Core set of notation elements   
Each core element has various subtypes

### Visual Diagram: BPMN Core Elements Legend
- **Overall Layout**: The diagram is a horizontal legend arranged in four columns, displaying the core notation elements for BPMN. Each column contains a geometric symbol, its name, and a textual description below it.
- **Element 1 (Left)**: A white rectangle with rounded corners and a black outline. 
  - **Name**: activity
  - **Description**: Activities capture work performed in a process.
- **Element 2 (Center-Left)**: Two circles shown side-by-side. The left circle has a thin black outline (with the word "start" below it). The right circle has a thick black outline (with the word "end" below it).
  - **Name**: event
  - **Description**: Events represent the process' triggers (start event) and outcomes (end event).
- **Element 3 (Center-Right)**: A white diamond (rhombus) with a black outline.
  - **Name**: gateway
  - **Description**: Gateways capture forking and joining paths in the control flow.
- **Element 4 (Right)**: A thin black horizontal arrow pointing to the right.
  - **Name**: sequence flow
  - **Description**: Sequence flows represent the order in which activities and events will be performed.

# Example Order-to-cash

### Visual Diagram: BPMN Example - Order-to-cash
- **Diagram Type**: BPMN Collaboration Diagram with Pools and Swimlanes.
- **Pools**: 
    - Top Pool: "Customer" (Black-box pool, no internal process details shown).
    - Bottom Pool: "Seller".
- **Swimlanes (within "Seller" Pool, top to bottom)**: 
    - "Warehouse & Distribution" (contains sub-lanes "ERP System" and "Warehouse Staff").
    - "Sales".
- **Message Flows (Dashed arrows crossing pool boundaries)**:
    - From Customer to Seller (ERP System): "Purchase order".
    - From Seller (Sales) to Customer: "Order confirmation", "Order rejection", "Invoice".
    - From Seller (Warehouse Staff) to Customer: "Shipment notice".

**Nodes and Process Routing (inside Seller Pool):**
1. **Start Event**: A message start event (circle with an envelope icon) labeled "Purchase order received" in the **ERP System** lane. It is triggered by the "Purchase order" message from the Customer.
2. **Activity**: A sequence flow leads to a task labeled "Check stock availability" in the **ERP System** lane.
3. **Exclusive Gateway (X)**: The flow moves down to an exclusive gateway (diamond with an 'X') in the **Sales** lane.
    - **Path "items not in stock"**: Flows to a task labeled "Reject order" in the **Sales** lane. This task sends an "Order rejection" message back to the Customer. The flow then terminates at an End Event labeled "Order rejected".
    - **Path "items in stock"**: Flows to a task labeled "Confirm order" in the **Sales** lane. This task sends an "Order confirmation" message to the Customer.
4. **Parallel Gateway (+) - Split**: After "Confirm order", the flow reaches a parallel gateway (diamond with a '+') in the **Sales** lane, splitting into two concurrent paths:
    - **Parallel Path A**: Flows up to a task labeled "Ship goods" in the **Warehouse Staff** lane. This task sends a "Shipment notice" message to the Customer.
    - **Parallel Path B**: Flows to a task labeled "Emit invoice" in the **Sales** lane. This task sends an "Invoice" message to the Customer.
5. **Parallel Gateway (+) - Join**: The sequence flows from both "Ship goods" and "Emit invoice" converge at a second parallel gateway in the **Sales** lane.
6. **Activity**: The unified flow continues to a task labeled "Archive order" in the **Sales** lane.
7. **End Event**: The process concludes at a standard end event (thick black circle) labeled "Order fulfilled" in the **Sales** lane.

# Flow process chart

V Many physical and manual processes consist of a sequence of simple actions, such as transport, waiting or inspection   
> ldentifying these simple activities makes it easier to find ways to improve the process   
When to use it:

>To provide a detailed description of a physical process by representing the individual activities in sequence   
>To analyze processes to identify and eliminate waste   
>To represent process with few decision blocks

> Uses the American Society of Mechanical Engineers (ASME) symbols

# ASME symbols

### Visual Diagram: ASME Symbols Legend for Flow Process Charts
- **Overall Layout**: The diagram is a legend enclosed within a white box with rounded corners and a thin black border. It features a vertical list of five standard ASME symbols aligned to the left, with their corresponding descriptions written to the right. All symbols have a thin black outline and a white fill.
- **Element 1 (Top)**: A circle.
  - **Description**: Activity, changes physical or chemical material characteristics
- **Element 2**: A block arrow pointing to the right.
  - **Description**: Transport, movement of people or material (distance measures could be included)
- **Element 3**: A semi-circle (resembling the capital letter 'D', with the flat vertical edge on the left).
  - **Description**: Waiting, for material arrivals or machines availability
- **Element 4**: An inverted triangle (pointing downwards).
  - **Description**: Warehouse, for material storage
- **Element 5 (Bottom)**: A square.
  - **Description**: Inspection, material quality and quantity control

# Example: Baking Cookies Factory

> A cookie factory decides to analyze how to improve its process   
> In the current process the cookies are formed after introducing the dough into the mould, then they are baked in the oven,cooled on a cooling belt and inspected on an inspection line   
>8.2% of the cookies do not pass the shape control and are discarded,the rest of them are packed for shipping

# Flow process chart

The main flow follows a vertical line from the top to the bottom   
Alternative flows representedon parallel lines   
Numbers for counting the symbols of the same type   
Description at the right side of the activity

### Visual Diagram: Flow Process Chart - Baking Cookies Factory
- **Overall Layout**: A vertical flow process chart using ASME symbols. Nodes are connected by a central vertical line, with one alternative flow branching horizontally to the right. Each symbol contains a sequential number corresponding to its specific category.

**Main Flow (Top to Bottom):**
1. **Transport (Block Arrow)**: Number inside: 1. Text right: "Introduce the dough into the mould". Measurement left: "50 m".
2. **Activity (Circle)**: Number inside: 1. Text right: "Shape the cookies".
3. **Transport (Block Arrow)**: Number inside: 2. Text right: "Place the cookies in the oven".
4. **Activity (Circle)**: Number inside: 2. Text right: "Bake the cookies in the oven". Measurement left: "13 min".
5. **Transport (Block Arrow)**: Number inside: 3. Text right: "Take the cookies to the cooling belt". Measurement left: "30 m".
6. **Waiting (Semi-circle)**: Number inside: 1. Text right: "Cooling of cookies". Measurement left: "30 min".
7. **Transport (Block Arrow)**: Number inside: 4. Text right: "Take the cookies to the inspection line". Measurement left: "30 m".
8. **Inspection (Square)**: Number inside: 1. Text right: "Inspection of cookies".

**Alternative Flow (Branching right after Inspection):**
- **Path**: A horizontal line branches to the right from the main vertical flow. 
- **Text on path**: "(8.2 %) Rejection of flan cookies".
- **Destination**: Leads to a **Transport (Block Arrow)** pointing right. Measurement left: "20 m".

**Main Flow Continuation (Downward after Inspection):**
9. **Activity (Circle)**: Number inside: 3. Text right: "Stacking for packaging".
10. **Activity (Circle)**: Number inside: 4. Text right: "Wrap the cookies".
11. **Warehouse (Inverted Triangle)**: Number inside: 1. Text right: "Place the cookies in the shipping boxes".

# Observations

Analyzing the material flow,you can see that the shape quality rejection rate is very high   
V A simple improvement could be to introduce an inspection immediately after the manufacture of the cookies,before baking, since the raw dough is easier to re-mix   
V With a successive intervention, the mixing and molding processes can be improved to further reduce the rejection rate

# Example: reengineering comparison

### Visual Diagram: Process Reengineering Comparison
- **Diagram Type**: Side-by-side comparison of a process flow before and after optimization.
- **Left Panel (Present State)**: Shows the "Original Process". The flow is highly complex, featuring multiple decision branches, long queues, and numerous waiting times.
    - **Key Metric 1**: Manufacturing Cycle = 349.49 Hours
    - **Key Metric 2**: Customer Order Cycle = 101.31
- **Right Panel (Future State)**: Shows the "Re-Engineered Process". The flow is significantly simplified, more linear, and structured to minimize delays.
    - **Key Metric 1**: Manufacturing Cycle = 80.79 Hours
    - **Key Metric 2**: Customer Order Cycle = 19.21

# Example: packaging process

### Visual Diagram: Flow Process Chart - Packaging Process
- **Overall Layout**: A continuous vertical flow process chart using standard ASME symbols. The flow is split into two columns for layout purposes, but represents a single sequential process starting from the top left and ending at the bottom right.

**Process Sequence:**
1. **Warehouse (Inverted Triangle)**: Store of waste paper
2. **Transport (Block Arrow)**: Convey to mixer
3. **Activity (Circle)**: Pulping and mixing
4. **Transport (Block Arrow)**: Convey to forming machine
5. **Activity (Circle)**: Forming (Moulding)
6. **Activity (Circle)**: Drying
7. **Inspection (Square)**: Inspecting & counting
8. **Activity (Circle)**: Stacking
9. **Activity (Circle)**: Packing
10. **Transport (Block Arrow)**: Convey to warehouse
11. **Warehouse (Upright Triangle)**: Store at warehouse

# Example: chair assembly

### Visual Diagram: Flow Process Chart - Chair Assembly
- **Overall Layout**: An assembly chart utilizing ASME symbols. It displays three parallel processing lines for distinct components ("Legs", "Sills", "Top"), which subsequently merge into a single main assembly line. Every node displays a timing value to its left and a descriptive label to its right. Activity nodes (Circles) enclose an operational number format (e.g., "0-12"), whereas Inspection nodes (Squares) enclose an inspection number format (e.g., "Ins. 3").

**Component Line 1 (Left): Legs**
- **Material**: Legs (4 Req'd) Dwg. 2834421-3, 2 1/2"x2 1/2"x16" White Maple.
1. **Activity (Circle)**: .09 Min. [0-12] Saw to Rough Length.
2. **Activity (Circle)**: .30 " [0-3] Joint Two Edges.
3. **Activity (Circle)**: .32 " [0-4] Plane to Size.
4. **Activity (Circle)**: .11 " [0-5] Saw to Finished Length.
5. **Inspection (Square)**: D.W. [Ins. 3] Check Over-All Dimensions.
6. **Activity (Circle)**: .28 Min. [0-16] Sand All Over.
*-> Merges into the main assembly line prior to operation [0-17].*

**Component Line 2 (Center): Sills**
- **Material**: Sills (4 Req'd) Dwg. 2834421-2, 1 1/2"x3"x12" Yellow Pine.
1. **Activity (Circle)**: .08 Min. [0-6] Saw to Rough Length.
2. **Activity (Circle)**: .15 " [0-7] Joint Two Edges.
3. **Activity (Circle)**: .30 " [0-8] Plane to Size.
4. **Activity (Circle)**: .10 " [0-9] Saw to Finished Length.
5. **Inspection (Square)**: D.W. [Ins. 2] Check Over-All Dimensions.
6. **Activity (Circle)**: .25 Min. [0-10] Sand All Over.
*-> Merges into the main assembly line prior to operation [0-11].*

**Component Line 3 (Right) & Main Assembly Line: Top**
- **Material**: Top Dwg. 2834421-1, 1 1/2"x14"x14" White Maple.
1. **Activity (Circle)**: .13 Min. [0-1] Saw to Rough Length.
2. **Activity (Circle)**: .23 " [0-2] Joint Two Edges.
3. **Activity (Circle)**: .32 " [0-3] Plane to Size.
4. **Activity (Circle)**: .18 " [0-4] Saw to Finished Length.
5. **Inspection (Square)**: D.W. [Ins. 1] Check Over-All Dimensions.
6. **Activity (Circle)**: .50 Min. [0-5] Sand All Over.
*-> Sills merge here.*
7. **Activity (Circle)**: 2.00 Min. [0-11] Assemble Four Sills to Top.
*-> Material added: 8 Slotted Head 1 1/2" Wood Screws, Pc. 416412.*
*-> Legs merge here.*
8. **Activity (Circle)**: 3.25 Min. [0-17] Assemble Legs Complete.
9. **Inspection (Square)**: D.W. [Ins. 4] Inspect Complete.
*-> Material added: Clear Shellac #173-111.*
10. **Activity (Circle)**: 1.15 Min. [0-18] Spray One Coat Clear Shellac.
11. **Activity (Circle)**: .75 " [0-19] Sand Complete.
*-> Material added: Gun Lacquer #115-309.*
12. **Activity (Circle)**: 1.15 Min. [0-20] Spray One Coat Lacquer.
13. **Inspection (Square)**: D.W. [Ins. 5] Inspect Finish.

### Visual Diagram: Flow Process Chart - Preparing Direct Mail Ads
- **Diagram Type**: Standard tabular Flow Process Chart template using ASME symbols.

**Header Information:**
- **Location**: Dorben Ad Agency
- **Activity**: Preparing Direct Mail Ads
- **Date**: 1-26-98
- **Operator**: J.S. / **Analyst**: A.F.
- **Method**: Present
- **Type**: Material

**Summary Table (Present State):**
- **Operation**: 4
- **Transport**: 4
- **Delay**: 4 *(Note: The traced path actually indicates 8 delays, but the handwritten summary explicitly reports 4)*
- **Inspection**: 0
- **Storage**: 2
- **Distance (ft)**: 340

**Process Sequence (Traced Events from top to bottom):**
1. **Storage (Triangle)**: stock room
2. **Transport (Arrow)**: to collating room | Distance: 100 ft
3. **Delay (D-shape)**: in collating rack by type
4. **Operation (Circle)**: collate 4 sheets
5. **Delay (D-shape)**: in stack
6. **Transport (Arrow)**: to folding room | Distance: 20 ft
7. **Delay (D-shape)**: in stack
8. **Operation (Circle)**: jog, fold, crease
9. **Delay (D-shape)**: in stack
10. **Transport (Arrow)**: to angle stapler | Distance: 20 ft
11. **Delay (D-shape)**: in stack
12. **Operation (Circle)**: staple
13. **Delay (D-shape)**: in stack
14. **Transport (Arrow)**: to mail room | Distance: 200 ft
15. **Delay (D-shape)**: in stack
16. **Operation (Circle)**: addressing
17. **Delay (D-shape)**: in stack
18. **Storage (Triangle)**: mailbag

# Exercise: paper factory

V The wood is partly purchased from a supplier and partly produced in the company's own forests. The wood is conveyed through an artificial channel to the covered storage area. From there,it is taken to be cut in the chipper, where the dimensions are made uniform to the standard size of 1x1/4 inch. Wood chips that are too large are returned to the previous station,and those that are too small are removed. The chips are then stored in silos.   
V Lignin is removed from wood chips by boiling them in caustic soda and sodium sulphide solution. Then the chips pass into a low-pressure discharge vat which physically separates the fibres.The wood fibres are then centrifuged and pressed. The pulp produced in this process is finally subjected to bleaching and then put to rest in the warehouse.   
The paper is produced starting from the pulp in a dedicated machine,in which the pulp is deprived of part of its content in water and compressed in steam-heated cylinders. Then it is wrapped in large reels and stored. When delivered to the customer it is cut and rewound into smaller reels.

# Solution

### Visual Diagram: Flow Process Chart - Paper Factory (Solution)
- **Overall Layout**: A vertical flow process chart using ASME symbols. It features two initial parallel inputs merging into a main line, one inspection node with a feedback loop and a rejection branch, followed by a sequential processing line.

**Sourcing and Initial Storage:**
- **Warehouse (Triangle 1)**: FOREST
- **Warehouse (Triangle 2)**: SUPPLIER
- **Transport (Block Arrow 1)**: From Forest
- **Transport (Block Arrow 2)**: From Supplier
*-> Transports 1 and 2 merge into:*
- **Warehouse (Triangle 3)**: WOOD STORAGE AREA

**Chipping and Inspection:**
- **Transport (Block Arrow 3)**: To chipper
- **Activity (Circle 1)**: CUTTING
- **Inspection (Square 1)**: CHIP INSPECTION
    - *Feedback Loop (Large Chips)*: Returns to the flow immediately before Activity 1 (CUTTING).
    - *Rejection Path (Small Chips)*: Flows right to **Transport (Block Arrow 4)** for removal.
    - *Main Flow Continuation*: Flows down to the next step.

**Pulp Processing:**
- **Transport (Block Arrow 5)**: To silos
- **Warehouse (Triangle 4)**: SILOS
- **Transport (Block Arrow 6)**: To boiling
- **Activity (Circle 2)**: BOILING
- **Transport (Block Arrow 7)**: To discharge vat
- **Activity (Circle 3)**: FIBER SEPARATION
- **Transport (Block Arrow 8)**: To centrifuge
- **Activity (Circle 4)**: CENTRIFUGE
- **Activity (Circle 5)**: PRESSING
- **Activity (Circle 6)**: BLEACHING
- **Transport (Block Arrow 9)**: To warehouse

**Paper Production and Delivery:**
- **Waiting/Delay (Semi-circle 1)**: REST IN THE WAREHOUSE
- **Transport (Block Arrow 10)**: To paper machine
- **Activity (Circle 7)**: DRYING
- **Activity (Circle 8)**: COMPRESSION
- **Activity (Circle 9)**: WRAPPING
- **Transport (Block Arrow 11)**: To storage
- **Warehouse (Triangle 5)**: REEL STORAGE
- **Transport (Block Arrow 12)**: To preparation for customer
- **Activity (Circle 10)**: CUTTING
- **Activity (Circle 11)**: REWINDING
- **Transport (Block Arrow 13)**: DELIVERY TO THE CUSTOMER

# Value Stream Mapping (VSM)

V Value Stream Mapping was introduced in 1980 by Taiichi Ohno and Shigeo Shingo，as part of the Toyota Production System， through which the Japanese company has implemented a policy of reducing waste in production processes   
V It is composed by a set of activities and processes necessary for the realization of a product， starting from the supplier to the delivery of the finished product   
> Activities are divided in two groups: value-added activity and non value-added activity   
V The VSM Objective is to identify and reduce any non-value-added activity (waste)，highlighting the points of improvement of the process

# Introduction

> Value Stream Mapping is a tool that analyses the current state of a production process   
> It allows to visualize in a clear and concise way the current production situation by drawing the material and information flows in order to decrease the inventory and the production time and to eliminate the overproduction   
Y It allows to identify each parts of the production flow to reengineer it   
> It describes the flow of materials/components of a given product inside the manufacturing(orlogistic) system， providingadescriptivevisual representation of each phase   
> lt highlights the points of material accumulation (i.e. raw material stocks, finished products and WIP) along the production process，as well as the causes of this accumulation

# Advantages of using Value Stream Mapping:

> shows the process flow as a whole, without detailing individual processes   
>allows to identify waste and the causes that determine it   
>is a common international language to talk about the production process   
>helps to define how the production flow should look like and lays the foundation for a Lean implementation plan   
> shows the link between material flows and information flows   
Vis a qualitative tool that describes how the plant should operate to produce value

# VSM Diagram

### Visual Diagram: Value Stream Mapping (VSM) Core Structure
- **Overall Layout**: A Value Stream Map divided into three distinct horizontal sections.
  1. Top Section: Information Flows.
  2. Middle Section: Material Flows.
  3. Bottom Section: Lead Time Ladder.

**1. Information Flows (Top Section):**
- **Supplier (Left)**: Factory icon.
- **Customer (Right)**: Factory icon.
- **Production Control (Center)**: Rectangular box.
- **Connections**: 
  - An electronic information flow (lightning arrow) goes from the Customer to Production Control, labeled "Monthly order".
  - An electronic information flow (lightning arrow) goes from Production Control to the Supplier, labeled "Weekly order".

**2. Material Flows (Middle Section):**
- **Supplier Delivery**: A truck icon labeled "Weekly" moves material from the Supplier down to the start of the production line (Process A) via a wide, white delivery arrow.
- **Internal Production Line (Left to Right)**:
  - **Process A**: Process box. Data box below reads: C/T = 300 sec, C/O = 60 min, Uptime = 80%, 2 Shifts, 27000 sec available. Preceded by an inventory triangle (1783).
  - **Push Flow**: A striped arrow connects Process A to Process B.
  - **Process B**: Process box. Data box below reads: C/T = 45 sec, C/O = 10 min, Uptime = 90%, 2 Shifts, 27000 sec available. Preceded by an inventory triangle (1202).
  - **Push Flow**: A striped arrow connects Process B to Process C.
  - **Process C**: Process box. Data box below reads: C/T = 300 sec, C/O = 240 min, Uptime = 100%, 2 Shifts, 27000 sec available. Preceded by an inventory triangle (733).
  - **Push Flow**: A striped arrow connects Process C to Shipping. Preceded by an inventory triangle (593).
  - **Shipping**: Process box.
- **Customer Delivery**: A truck icon labeled "Monthly" moves the finished product from Shipping up to the Customer via a wide, white delivery arrow.

**3. Lead Time Ladder (Bottom Section):**
- A continuous, stepped timeline showing non-value-added time (waiting/inventory) on the upper steps and value-added time (processing) on the lower steps.
- **Timeline Values (Left to Right)**:
  - Wait time: 6 days -> Processing time: 300 sec
  - Wait time: 4 days -> Processing time: 45 sec
  - Wait time: 1 day -> Processing time: 240 sec
  - Wait time: 3 days
- **Summary Box (Right)**:
  - Production lead time = 14 days
  - Processing time = 585 sec
  
# Formalism

The manufacturing process mapping is performed using a series of simple unified icons

These icons can represent both physical flows and information flows of the production planning system (e.g., an MRP system)

### Visual Diagram: Value Stream Mapping (VSM) Symbols Legend
- **Overall Layout**: A comprehensive legend organized into three thematic groups: "Flow Symbols" (Top Left), "Internal/External Process Symbols" (Bottom Left), and "Process Improvement Symbols" (Right Column).

**1. Flow Symbols (Physical, Informational, Temporal):**
- **Physical flow**: A solid black horizontal arrow.
- **Electronic information**: A "lightning" style arrow.
- **Manual information**: A thin straight horizontal arrow.
- **Inbound/Outbound physical flow**: A wide white arrow (hollow arrow) pointing diagonally up.
- **Time Line**: A stepped line showing alternating upper and lower levels for non-value-added and value-added time.

**2. Internal and External Process Symbols:**
- **Process Box**: A rectangle divided by a horizontal line near the top.
- **Process Box (multiple processes)**: A rectangle with a shaded/striped header.
- **Process Box (generic)**: A plain white rectangle.
- **External source (Supplier/Customer)**: A factory icon with a jagged roof.
- **Process Box Data box**: A rectangle containing horizontal lines (representing rows of data).
- **Inventory/Warehouse**: An upright triangle.
- **Operator**: A simple semi-circle icon representing a person.
- **Computer-assisted process (MRP)**: A 3D cylinder/canister icon.

**3. Process Improvement Symbols:**
- **Kaizen burst (Obiettivo kaizen)**: A spiked "explosion" shape.
- **Supermarket**: A symbol resembling an open shelf (three horizontal lines within a three-sided frame).
- **Kanban post**: A symbol resembling a goalpost or a "U" shape on a stand.
- **Kanban flow**: A dashed arrow pointing down and then right.
- **Production Kanban**: A square containing a small "P" in a corner box.
- **Withdrawal Kanban**: A square containing a small "W" in a corner box.
- **Signal Kanban**: A square containing an inverted triangle with an "S".
- **FIFO Lane**: A long rectangle containing circular and triangular symbols, labeled "Max = XX".
- **U-shaped work cell**: A rectangle with a thick black "U" path inside.
- **Buffer Warehouse**: A rectangle containing two small boxes labeled "B".
- **Safety Stock**: A rectangle containing two small boxes labeled "S".

The manufacturing process mapping is performed using a series of simple unified icons   
> These icons can represent both physical flows and information flows of the production planning system (e.g., an MRP system)

# Factory

It is the symbol used to represent external sources

Clients   
>Suppliers   
>Outsourced Process

Factory + Data Box

>Shipping frequency per shift   
>Information about the material handled   
>Purchase lot size   
>Average demand per time bucket   
>In the case of supliers you can enter data such as number of parts/day, tray (pallet capacity, product bins), On Time Delivery.   
>In case of customers: number of products ordered/day, turnover, OTD.   
>In the case of services, the concepts are similar, it remains only to identify the appropriate measurements   
18400 parts/month   
12000 Left side   
6400Right side   
Shelf=20 parts   
2 shifts

### Visual Diagram: VSM External Sources and Data Boxes
- **Overall Layout**: Two examples of the "Factory" symbol used in Value Stream Mapping to represent external entities (Suppliers or Customers).

**1. External Source Symbol (Top)**
- **Visual Shape**: A factory icon with a jagged, sawtooth-style roof and a rectangular base.
- **Label**: "ABC COMPANY" written inside the rectangular base.
- **Context**: This symbol represents an external source, such as a supplier or a customer, before additional data is attached.

**2. Factory with Data Box (Bottom)**
- **Visual Shape**: A larger factory icon with a jagged roof, labeled "Customer" inside the main rectangular body.
- **Attached Element**: A "Data Box" is positioned directly underneath the factory icon. It is a rectangle divided into four horizontal rows of technical data.
- **Data Box Content (Top to Bottom)**:
    - **Row 1**: 18400 parts/month | 12000 Left side | 6400 Right side
    - **Row 2**: (empty)
    - **Row 3**: Shelf = 20 parts
    - **Row 4**: 2 shifts
- **Context**: This combination represents a specific external entity (Customer) along with their demand requirements, logistics (shelf capacity), and operational constraints (shifts).

# Customer

# Production process

> It is the symbol used to represent the production process

>A machine   
>A process   
>A factory

V Process + Data box

>Cycle Time (C/T)   
>Setup Time  
>Production Rate per hour/shift   
>Machine downtime,uptime and waiting time   
>Waste and Rework   
>etc.

Operators

>Whether a process is automated or needs operators   
Report the number of operators required

### Visual Diagram: Basic VSM Process Box
- **Visual Shape**: A rectangle with a black outline, divided by a horizontal line near the top to create a header section.
- **Text**: The word "PROCESS" is centered within the top header.
- **Functional Meaning**: This is the generic symbol used to represent a single machine, a specific manufacturing process, or an entire factory department.

### Visual Diagram: VSM Process with Integrated Data Box
- **Visual Shape**: A process box (labeled "WELDING" in the header) with a multi-row table (Data Box) attached directly to its bottom edge.
- **Internal Elements**: Contains an operator icon (circle over a semi-circle) followed by the number "**2**" in the bottom-left corner of the process box.
- **Data Box Content**: A vertical list of technical metrics:
    - **C/T** (Cycle Time) = **39 sec**
    - **C/O** (Setup Time) = **10 Min**
    - **Uptime** = **100%**
    - **Shifts** = **2 Shifts**
    - **Availability** = **27600 sec**
- **Functional Meaning**: Represents a specific workstation (Welding) including its human resource requirements (2 operators) and its operational performance data.

### Visual Diagram: VSM Operator Symbol
- **Visual Shape**: A standalone icon consisting of a small circle (representing a head) positioned over a larger semi-circle (representing a torso or workstation seat).
- **Functional Meaning**: This symbol is used to report human resource requirements. It indicates whether a process needs manual intervention and is used to specify the exact number of operators required for a task.

# Inventory

> It shows the accumulation of products between processes   
> It can be expressed in terms of WIP or time,while in the services and offices it can be understood as pending files, emails to be processed, etc   
V Traditionally the icon is a triangle, as it represents a significant danger in terms of waste.

### Visual Diagram: VSM Inventory Symbol
- **Visual Shape**: An upright equilateral triangle with a black outline.
- **Internal Elements**: The capital letter "**I**" (standing for Inventory) is centered inside the triangle.
- **External Text**: Positioned directly underneath the base of the triangle in two rows:
    - **Row 1**: "300 pezzi" (identifying the quantity of items).
    - **Row 2**: "2 Giorni" (identifying the inventory lead time/coverage).
- **Functional Meaning**: This is the standard symbol used to show the accumulation of products between processes. It can represent Work-in-Progress (WIP), raw materials, or finished goods. In Lean manufacturing, the triangle shape is used as a warning sign for waste. The data below the symbol quantifies the stock both in physical units and in time (days of supply).

# Material flow

### Visual Diagram: VSM Push Flow Arrow
- **Visual Shape**: A horizontal arrow pointing to the right, characterized by a fill of alternating black and white segments (striped or dashed pattern).

>Represents the material flow between two stations   
>Indicates a "Push" type flow

# White arrow

### Visual Diagram: VSM External Shipment Arrow
- **Visual Shape**: A wide, hollow (white) horizontal arrow with a clean black outline, pointing to the right.

> Represents the movement of raw materials from suppliers   
>Represents the movement of finished products towards customers

# Way of transport

Icon to represents the transportation adopted

>Truck   
Rail   
>Ship   
V Plane

Frequency of supplying and/or delivery is indicated

### Visual Diagram: VSM Transport Component Structure (image_ff24f6.png)
- **Component Type**: External Logistics Notation.
- **Logic**: The symbol combines a fixed visual icon (mode) with a variable text descriptor (frequency).

#### 1. Transportation Mode Icons (Static)
- **Truck Icon**: Represents road-based transport.
- **Rail Icon**: Represents train/railway-based transport.
- **Ship Icon**: Represents maritime/sea-based transport.
- **Plane Icon**: Represents air-freight transport.

#### 2. Frequency Labels (Variable/Placeholder Examples)
- **Structure**: A rectangular text box placed directly below the icon.
- **Example Values**: "Daily", "Weekly", "Montly", or "Twice x week".
- **Functional Use**: In a real VSM, these labels are replaced with the actual supply or delivery frequency identified.

# Information Flow

Straight arrow

>Manual information flows (fax,e-mail, telephone, etc.)

Lightning arrow

Electronic information flows

Information Label

> Specify the type of information   
> It is shown above the arrows of the information flow

### Visual Diagram: VSM Information Flow Symbols
- **Component Type**: Information Flow Notation.
- **Logic**: These symbols represent the communication and scheduling links that coordinate material flows.

#### 1. Manual Information Flow
- **Visual Shape**: A thin, straight horizontal arrow pointing to the left.

#### 2. Electronic Information Flow
- **Visual Shape**: A "lightning" or "zigzag" style arrow pointing to the left.

#### 3. Information Label
- **Visual Shape**: A simple rectangle containing text.
- **Text**: "Schedulazione settimanale" (English: Weekly Scheduling).


# Timeline

> The Timeline shows the overall Lead Time given by the sum of the processing, handling and waiting times.

>The low line means that the product is within the process, and it will be worked for different time (it is the time in which the product is processed on the machine)   
>ln the high part of the line are indicated the waiting times

### Visual Diagram: VSM Lead Time Ladder
- **Component Type**: Time Analysis Notation.
- **Visual Shape**: A continuous stepped line (alternating crests and troughs) ending in a dual-row summary box.
- **Functional Meaning**:
    - **Upper Steps (Crests)**: Represent **Non-Value-Added Time**, which is the time material spends waiting or sitting in inventory between processes.
    - **Lower Steps (Troughs)**: Represent **Value-Added Time**, which is the actual processing time (Cycle Time) for each production step.
- **Summary Metrics (Right-hand Box)**:
    - **Production Lead Time**: The total cumulative time (sum of all steps) a product takes to travel through the entire value stream ($23.5\ \text{days}$ in the example).
    - **Value-Added Time**: The total sum of only the processing times where value is actively added to the product ($184\ \text{sec}$ in the example).

# 1.Process flow identification (Data box)

# Identification and mapping of the main phases

### Visual Diagram: VSM Process Mapping and Data Collection Example
- **Overall Layout**: A horizontal sequence showing the main production phases, associated inventory, physical distances, and the technical Data Boxes for each process.

#### 1. Main Phases and Inventory
- **Inventory Points (Triangles)**:
    - **Storage (Start)**: Labeled "coils" with a lead time of "4 days".
    - **Shipping (End)**: Labeled with quantities "2700L" and "1440R".
- **Production Processes (Process Boxes)**:
    - **Stamping**: 1 operator.
    - **Welding (1)**: 1 operator.
    - **Welding (2)**: 1 operator.
    - **Assembly 1**: 1 operator.
    - **Assembly 2**: 1 operator.
- **Distances**: Physical distances are indicated between phases (120m, 80m, 30m, 180m, 20m, 60m).

#### 2. Information Collection (Data Boxes)
- **Structure**: Vertical tables placed under each production process box to collect operational KPIs.
- **Common Metrics and Sample Values**:
    - **C/T (Cycle Time)**: Ranges from 1s (Stamping) to 62s (Assembly 1).
    - **C/O (Changeover Time)**: Varies from 60 min (Stamping) to 0 min (Assembly).
    - **Uptime**: Availability percentages (e.g., 80%, 90%, 95%).
    - **FTY (First Time Yield)**: Quality rate (e.g., 0.9, 0.85, 0.95).
    - **Shifts**: Indicates the work schedule (e.g., "2 shift").

#### 3. Functional Meaning
- **Identification**: The top row defines the flow and sequence of the main value-adding activities and storage points.
- **Data Collection**: The Data Boxes provide the quantitative foundation needed to calculate the total Processing Time and identify bottlenecks or quality issues (FTY).

# 2.Material flow identification

>Material flow from supplier to customer

### Visual Diagram: VSM Material Flow Identification
- **Overall Layout**: A complete end-to-end representation of the physical material movement from the supplier to the final customer, incorporating inbound/outbound logistics, internal processing steps, and intermediate buffer points.

#### 1. External Logistics (Inbound & Outbound)
- **Supplier to Plant**: Material is transported via truck on a **Mo + We** (Monday and Wednesday) schedule.
- **Plant to Customer**: Finished goods are delivered via truck on a **daily** schedule.

#### 2. Internal Material Flow (Push System)
- **Flow Type**: Represented by striped horizontal arrows between every internal process, signifying a **Push** system where material is moved based on a schedule rather than actual downstream demand.
- **Process Sequence**:
    1.  **Stamping**
    2.  **Welding** (first station)
    3.  **Welding** (second station)
    4.  **Assembly 1**
    5.  **Assembly 2**
    6.  **Shipping**

#### 3. Inventory and Work-in-Progress (WIP)
- **Raw Material Storage**: 4 days of **coils** inventory held at the start.
- **Intermediate Buffers**: Inventory accumulation points (triangles) between processes with specific quantities tracked:
    - **Post-Storage**: 1 day of coils.
    - **Post-Stamping**: 4600L / 2400R units.
    - **Post-Welding 1**: 1100L / 600R units.
    - **Post-Welding 2**: 1600L / 850R units.
    - **Post-Assembly 1**: 1200L / 640R units.
- **Finished Goods**: 2700L / 1440R units stored in the **Shipping** area before final delivery.

# 3.Time information

Timeline Design   
>Cycle Time, Waiting Time e Lead time

### Visual Diagram: VSM Time Information and Lead Time Ladder
- **Overall Layout**: A lead time ladder positioned at the bottom of the VSM to differentiate between value-added activity and non-value-added waiting periods.

#### 1. Non-Value-Added Time (Upper Steps)
- **Definition**: Represents the time materials spend as inventory between processes.
- **Values (Left to Right)**:
    - **5 days** (Initial storage)
    - **7.6 days** (WIP post-stamping)
    - **1.8 days** (WIP post-welding 1)
    - **2.7 days** (WIP post-welding 2)
    - **2.0 days** (WIP post-assembly 1)
    - **4.5 days** (Final storage before shipping)

#### 2. Value-Added Time (Lower Steps)
- **Definition**: Represents the actual processing time or Cycle Time ($C/T$) for each manufacturing step.
- **Values (Left to Right)**:
    - **1 s** (Stamping)
    - **39 s** (Welding 1)
    - **46 s** (Welding 2)
    - **62 s** (Assembly 1)
    - **40 s** (Assembly 2)

#### 3. Total Performance Metrics (Summary Boxes)
- **Total Lead Time ($W/T$)**: **23.6 d** (Sum of all inventory/waiting periods).
- **Total Processing Time ($P/T$)**: **188 s** (Sum of all individual cycle times).

# 4. Add Information Flows

### Visual Diagram: VSM Information Flow Integration 
- **Overall Layout**: The top section of the VSM detailing the communication network between the central control hub, external partners, and the production floor.

#### 1. Centralized Control Hub
- **Production Planning & Control**: The main rectangular box coordinating all activities.
- **MRP**: An internal sub-system (computer-assisted process icon) within planning used for resource calculations.
- **Weekly Production Plan**: A secondary scheduling box that disseminates operational instructions to the shop floor.

#### 2. External Communication Links
- **Customer-to-Plant**:
    - **Forecast**: Electronic information flow (lightning arrow).
    - **Daily Order**: Electronic information flow (lightning arrow).
- **Plant-to-Supplier**:
    - **Forecast**: Electronic information flow (lightning arrow).
    - **Faxback**: Manual information flow (straight arrow).

#### 3. Internal Scheduling and Directives
- **Directives**: Manual information flow arrows (straight lines) originating from the **weekly production plan** box.
- **Targets**: These arrows point to every stage of the value stream, including **storage**, **stamping**, **welding** (both stations), **assembly** (both stations), and **shipping**.

#### 4. Functional Meaning
- **Centralized Coordination**: These flows represent the "brain" of the operation, ensuring that customer demand is translated into actionable supplier orders and internal schedules.
- **Push Logic**: Information is pushed directly to each workstation from a central source, which typically characterizes a system where processes are managed via a master schedule rather than a pull signal.

# FIRM

Acme Spa pressed steel steering arms   
>The firm produces 2 types of products → L (left side) and R (right side)   
>Each month has 20 working days,in 2 shifts of 8 hours each and two breaks of 10 minutes for each shift

# CLIENT

Client demand18.400 p/month:

> L→ 12.000 [p/month]   
>R →6.400 [p/month]

Shipments to customers are made 1 time per day

# PRODUCTION CONTROL

>The production control is carried out by MRP which provides forecasts at 90, 60 and 30 days   
>Every day the customer provides orders with the desired quantities   
? The production is managed through a weekly schedule   
>The MRP forecasts with 6-month horizon sent to the supplier   
>Acme sends orders to the supplier weekly

# SUPPLIER

>The supplier supplies 500 feet long steel coils twice a week,transporting them by truck   
>The coils supplied allow you to have material in the initial warehouse for 5 day

# PROCESSES

>The flow between the various phases of production are of push type   
>6 processes:

# Stamping

> Process time= 1 s   
Setup time = 1 h   
> Uptime = 85%   
> Observed warehouse= 4600 L e 2400 R

# Welding 1

> Process time= 38 s   
> Setup time = 10 m   
>Uptime = 100%   
> Observed warehouse= 1100 L e 600 R

# Welding 2

> Process time = 45 s   
> Setup time = 10 m   
> Uptime = 80%   
V Observed warehouse = 1600 L e 850 R

# Assembly 1

> Process time = 61 s   
Setup time = 10 m   
>Uptime = 100%   
V Observed warehouse = 1200 L e 640 R

# Assembly 2

> Process Time = 39 s   
> Setup time = 0   
>Uptime = 100%   
> Observed Warehouse = 2700 Le 1440 R

# Shipment

> after assembly the product is shipped to the customer

# Example solution

# Operator Availability

Each month has 20 working days,consisting of 2 shifts of 8 hours each, with two breaks of 10 minutes for each shift.

Time available for each process (available working time):

1 shift 8*60*60 = 28,800 [s/shift]

two breaks per shift 2*10*60 = 1,200[s/shift]

Therefore, the available time is 28,800 - 1,200 = 27,600 s/shift

# Example solution

### Visual Diagram: VSM External Entities - Supplier and Customer
- **Component Type**: Value Stream Boundary Notation.
- **Visual Layout**: Standard VSM factory icons representing the starting point (Supplier) and ending point (Customer) of the value stream.

#### 1. Supplier Symbol (Left)
- **Visual Shape**: Factory icon with a sawtooth-style roof.
- **Internal Label**: "Michigan Steel Co."
- **Attached Data Box**: A separate rectangle positioned below the icon.
- **Data Box Content**: "**500 ft coils**"
- **Functional Meaning**: Represents the raw material source and the specific procurement unit (steel coils).

#### 2. Customer Symbol (Right)
- **Visual Shape**: Factory icon with a sawtooth-style roof.
- **Internal Label**: "State Street Assembly"
- **Attached Data Box**: A vertical table connected to the base of the icon, divided into five horizontal rows.
- **Data Box Content**:
    - **Row 1**: "18,400 pcs/mo" (Total monthly demand volume).
    - **Row 2**: "- 12,400 'L'" (Specific demand for the Left-side product variant).
    - **Row 3**: "- 6,400 'R'" (Specific demand for the Right-side product variant).
    - **Row 4**: "Tray = 20 pieces" (Load unit/packaging standard).
    - **Row 5**: "2 Shifts" (Customer operational requirement).
- **Functional Meaning**: Defines the final customer requirements and the mix of product types (L and R) that drive the production schedule.

Insert the Supplier and Customer icons,with the relative Data Boxes containing the total quantities to be supplied for a given period and calculate the necessary daily production and the load unit type/characteristics

# Example solution

### Visual Diagram: VSM Internal Production Flow (image_fe969e.png)
- **Component Type**: Internal Process and Material Flow Notation.
- **Visual Layout**: A horizontal sequence of six process stations and six intermediate inventory points, representing the internal operations of Acme Spa.

#### 1. Initial Storage and Stamping
- **Initial Inventory**: Triangle labeled "Coils" and "5 days".
- **Process Box 1**: Labeled "**STAMPING**" with internal text "**200 T**".
- **Data Box 1**:
    - **C/T**: 1 second
    - **C/O**: 1 hour
    - **Uptime**: 85%
    - **Available time**: 27,000 sec.
    - **EPE**: 2 weeks
- **Post-Process Inventory**: Triangle labeled "4600 L" and "2400 R".

#### 2. Welding Stations
- **Process Box 2**: Labeled "**S. WELD #1**".
- **Data Box 2**: C/T = 38 seconds, C/O = 10 minutes, Uptime = 100%, 2 Shifts, 27,000 sec. avail.
- **Intermediate Inventory**: Triangle labeled "1100 L" and "600 R".
- **Process Box 3**: Labeled "**S. WELD #2**".
- **Data Box 3**: C/T = 45 seconds, C/O = 10 minutes, Uptime = 80%, 2 Shifts, 27,000 sec. avail.
- **Post-Process Inventory**: Triangle labeled "1600 L" and "850 R".

#### 3. Assembly Stations
- **Process Box 4**: Labeled "**ASSEMBLY #1**".
- **Data Box 4**: C/T = 61 seconds, C/O = 0, Uptime = 100%, 2 Shifts, 27,000 sec. avail.
- **Intermediate Inventory**: Triangle labeled "1200 L" and "640 R".
- **Process Box 5**: Labeled "**ASSEMBLY #2**".
- **Data Box 5**: C/T = 39 seconds, C/O = 0, Uptime = 100%, 2 Shifts, 27,000 sec. avail.
- **Final WIP Inventory**: Triangle labeled "2700 L" and "1440 R".

#### 4. Final Stage
- **Process Box 6**: Labeled "**SHIPPING**" with internal text "**Staging**".
- **Functional Meaning**: Represents the movement of steering arms through sequential manufacturing phases, quantifying the performance (Data Box) and inventory accumulation (Triangles) at each workstation.

Draw, from left to right, the Process boxes and the corresponding Data Boxes related to the internal operations/stations of the component under analysis (e.g., the production flow of the component)

# Example solution

### Visual Diagram: Integrated Current State Value Stream Map
- **Component Type**: Comprehensive Current State Value Stream Map (VSM).
- **Visual Layout**: A top-down orchestration of centralized production control, material process flow, and lead time analysis.

#### 1. External Supply and Demand (Boundary Entities)
- **Supplier (Michigan Steel Co.)**:
    - **Inbound Logistics**: Delivery of **500 ft coils** via truck scheduled on a "**Tues. + Thurs.**" basis.
    - **Communication**: Receives a "**6-week Forecast**" (Electronic/Lightning arrow) and a "**weekly fax**" (Manual/Straight arrow) from Production Control.
- **Customer (State Street Assembly)**:
    - **Demand Requirements**: Monthly volume of **18,400 pieces**, comprising **12,400 'L'** and **6,400 'R'** units, packaged in trays of 20 pieces.
    - **Outbound Logistics**: Final product shipment via truck scheduled "**1x Daily**".
    - **Communication**: Transmits "**90/60/30 day Forecasts**" and "**Daily Orders**" (Electronic/Lightning arrows) to Production Control.

#### 2. Centralized Information Control Hub
- **Production Management**: Handled by "**PRODUCTION CONTROL**" utilizing an internal **MRP** system.
- **Scheduling Output**: Coordinates a "**Weekly Schedule**" which provides manual instructions (straight arrows) to each internal manufacturing station.
- **Logistics Instruction**: Issues a "**Daily Ship Schedule**" (Electronic/Lightning arrow) directly to the Shipping/Staging area.

#### 3. Internal Material Flow (Push Logic)
- **Flow Control**: Internal movement between all processes is governed by a **Push system**, indicated by striped horizontal arrows.
- **Process Sequence and Technical Data**:
    - **Stamping**: 200T press operation; C/T = 1 second, C/O = 1 hour, Uptime = 85%, EPE = 2 weeks.
    - **S. Weld #1**: Welding station; C/T = 38 seconds, C/O = 10 minutes, Uptime = 100%, 2 Shifts.
    - **S. Weld #2**: Welding station; C/T = 45 seconds, C/O = 10 minutes, Uptime = 80%, 2 Shifts.
    - **Assembly #1**: First assembly stage; C/T = 61 seconds, C/O = 0, Uptime = 100%, 2 Shifts.
    - **Assembly #2**: Second assembly stage; C/T = 39 seconds, C/O = 0, Uptime = 100%, 2 Shifts.
    - **Shipping**: Final staging area for goods prior to external dispatch.
- **Resource Constraints**: Every data box indicates a standard **27,000 sec. avail.** per shift.

#### 4. Inventory Buffers (Triangles)
- **Stock Levels**: Buffers quantify Work-in-Progress (WIP) accumulation between processing steps:
    - **Raw Material**: Coils (5 days).
    - **Post-Stamping**: 4600 L / 2400 R.
    - **Post-Weld #1**: 1100 L / 600 R.
    - **Post-Weld #2**: 1600 L / 850 R.
    - **Post-Assembly 1**: 1200 L / 640 R.
    - **Finished Goods**: 2700 L / 1440 R (Staging area).

#### 5. Lead Time Ladder
- **Visual Shape**: A stepped timeline at the map base quantifying time distribution.
- **Non-Value-Added Time (Crests)**: 5 days, 7,6 days, 1,8 days, 2,7 days, 2,0 days, and 4,5 days.
- **Value-Added Time (Troughs)**: 1 s, 39 s, 46 s, 62 s, and 40 s.
- **Performance Summary**:
    - **D/T (Delivery Time)**: **23,6 d**.
    - **P/T (Processing Time)**: **188 s**.

Draw the icons for the external handling connections (raw material and finished products) from the warehouse to the Customer and from the Supplier. Represent the mode of transport used (e.g.,Truck shipment) and indicate the frequency of shipments (daily, etc.). Draw the icons representing manual and/or electronic information and communication flow, describing the function/content with the Information icon.

# Warehouse related time

Stock time = Quantity of stock pieces / daily customer demand   
>Customer question = 18,400 [pcs/month]/20 [working days] = 920 pcs/day   
>Warehouse after stamping: (4600+2400)/920 = 7.6 days   
>Warehouse after welding 1: (1100+600)/ 920 = 1.8 days   
>Warehouse after welding 2: (1600+850)/ 920 = 2.7 days   
>Warehouse after assembly 1: (1200+640)/920 = 2 days   
>Warehouse after assembly 2: (2700+1400)/920 = 4.5 days

# Example solution

### Visual Diagram: Final VSM Performance Summary
- **Component Type**: Time Analysis and Lead Time Calculation Summary.
- **Visual Layout**: An integrated lead time ladder at the base of the map with a summary results box in the bottom right corner.

#### 1. Lead Time Ladder Analysis
- **Non-Value-Added Time (Wait Times)**: Represented by the upper horizontal segments of the ladder, totaling the inventory holding periods:
    - **5 days** (Initial inventory)
    - **7.6 days** (Post-Tamping inventory)
    - **1.8 days** (Post-Weld #1 inventory)
    - **2.6 days** (Post-Weld #2 inventory)
    - **2 days** (Post-Assembly #1 inventory)
    - **4.5 days** (Final Shipping/Staging inventory)
- **Value-Added Time (Processing Times)**: Represented by the lower horizontal segments of the ladder, totaling the actual production cycle times ($C/T$):
    - **1 second** (Tamping process)
    - **38 seconds** (Weld #1 process)
    - **45 seconds** (Weld #2 process)
    - **61 seconds** (Assembly #1 process)
    - **39 seconds** (Assembly #2 process)

#### 2. Summary Metrics Calculation
- **Production Lead Time**: Aggregated waiting time shown in the final summary box as **23.5 days**.
- **Value-Added Time**: Aggregated processing time shown in the final summary box as **184 sec.**.

#### 3. Functional Meaning
- **Current State Assessment**: Provides the final quantitative summary of the value stream's efficiency, comparing the total time the product spends in the system (Lead Time) against the actual time spent in production (Value-Added Time).
Compute the total Value Added Time and Production Lead Time

# FIRM

TWI produces components for tractors, in particular steering arms   
>Each month has 20 working days, consisting of 2 shifts of 8 hours each, with two breaks of 15 minutes for each shift.

# CUSTOMER

>Demand of 24,000 pcs/month   
>2 working shifts each day   
> Shipments to customers are made 1 time a day by trucks

# PRODUCTION CONTROL

The customer provides a 60 day purchase forecast, and a precise order schedule two weeks before delivery   
The production is managed through a weekly schedule   
Orders to the suppliers are done weekly   
> Every day a delivery plan is generated for the shipping department

# SUPPLIER

The company purchases steel bars and raw joints from two suppliers, Michigan Steel and Indiana Castings   
Both suppliers make deliveries 2 times a month and guarantee an initial stock for 20 days   
V The bar cutting and the joint finishing processes are done in parallel, then the two components are welded and continue the production process

# PROCESS DATA

# Bar cutting

V 1 operator   
CT= 15s, C/O = 1h   
Reliability = 100%   
Warehouse: 5 days of cutted bars

# > Joint finishing

1 operator   
CT = 30s, C/O = 2h   
V Reliability = 100%   
V Warehouse: 5 days of finished bars

# >1° Welding

V 1 operator   
CT = 30s, C/O = 1h   
Reliability = 90%   
V Warehouse: 3 days of welded arms

# >2° Welding

V 1 operator   
V CT = 30s, C/O = 1h   
Reliability = 80%   
Warehouse: 3 days of welded arms

# Deburring

>1operator   
V CT = 30s, C/O = 1h   
Reliability = 100%   
Warehouse: 5 days of welded arms

# Painting (outsourcing)

Lead-Time = 2 days   
Warehouse: 6 days of painted arms (TWI)

# >Assembly

V 6 operators   
V CT = 195s, C/O = 10 min   
Reliability = 100%   
Warehouse: 4 days of finished arms

# Shipping

# Solution

# Operator availability

>Each month has 20 working days, consisting of 2 shifts of 8 hours each,with two breaks of 15 minutes for each shift   
>Time available for each process (available working time):   
>1 shift 8*60*60 = 28,800 [s/shift].   
>two breaks per shift 2*15*60= 1,800[s/shift]

> Therefore, the available time is 28,800 - 1,800 = 27,000 s/shift

# Solution

### Visual Diagram: TWI Steering Arms VSM
- **Component Type**: Current State Value Stream Map with parallel processing.
- **Process Highlights**: 
    - Parallel paths for Bar Cutting and Joint Finishing.
    - Outsourced Painting phase (2-day Lead Time).
    - Multi-operator Assembly station (6 operators).
- **Summary Results**:
    - **VAT**: 315 s
    - **Lead Time**: 48 days
# IDEF diagram

V ICAM project (Integrated Computer Aided Manufacturing)

IDEFO for the generation of functional models   
IDEF1 for the generation of information models   
IDEF1X for the semantic modelling of data   
IDEF2 for the generation of dynamic models

# IDEFO diagrams

V Method designed to represent the activities of an organization or system   
>Constraints and controls between activities   
Based on the organic and systematic combination of graphic and textual components   
V The components are related through a multilevel hierarchical structure

# Diagram layout

"Box and arrow” graphics   
Y Function represented by a box whose sides enter or exit arrows with different meanings   
Node: identification of the represented node

> A-0 overview   
Y AO general activity   
>A1, A2, A3, .. First level of details   
> A11, A12.,.. A21, A22.,.. Second level of detais

Title of the diagram   
Number of the diagram   
Short description of the diagram

### Visual Diagram: IDEF0 Functional Block and ICOM Architecture
- **Component Type**: Basic Functional Modeling Unit.
- **Logic**: The diagram follows the ICOM (Input, Control, Output, Mechanism) convention to define a specific activity or function within a system.

#### 1. Central Activity Box
- **Visual Shape**: A rectangular box centered in the diagram.
- **Internal Content**: 
    - "**Activity name**": A verb-phrase label describing the function performed.
    - "**A0**": The node identifier (index) located in the bottom right corner of the box.

#### 2. Interface Arrows (ICOM)
- **Input (Left side)**: Arrows entering the left face of the box represent the objects or data consumed or transformed by the activity.
- **Controls (Top side)**: Arrows entering the top face represent the conditions, rules, or standards that govern the performance of the activity.
- **Resources / Mechanisms (Bottom side)**: Arrows entering the bottom face represent the means (personnel, tools, machines, or systems) used to perform the activity.
- **Output (Right side)**: Arrows exiting the right face represent the objects or data produced by the completion of the activity.

#### 3. Diagram Metadata (Footer)
- **Node**: Identified as "A-0" (Top-level context diagram).
- **Title**: Placeholder for the process name.
- **Project Label**: "IDEF0 Diagram".
- **Numbering**: Designated as "N.: 1".

#### 4. Functional Meaning
- This layout establishes the context and boundaries of a process, identifying exactly what triggers it, what regulates it, what resources it requires, and what result it provides to the next stage of the system.

# Hierarchy of diagrams

### Visual Diagram: IDEF0 Functional Decomposition and Hierarchy
- **Overall Layout**: A multi-level schematic illustrating the top-down decomposition of functional blocks within an IDEF0 model, moving from a general context to specific details.

**1. Level A-0: Context Diagram (Top Right)**
- **Visual Elements**: A single activity box labeled "**0**" with node index "**A0**".
- **Functional Meaning**: Represents the highest level of the system, defining the overall scope, boundaries, and high-level interface (Global Inputs, Controls, Outputs, and Mechanisms).

**2. Level A0: First Decomposition (Middle Left)**
- **Visual Elements**: The parent "**A0**" box is expanded into a detailed diagram containing four sub-activity boxes numbered **1, 2, 3, and 4**.
- **Hierarchy Link**: Dotted lines show the parent-child relationship between the A0 context box and this diagram.
- **Reference Node**: Box **4** is marked with node ID "**A4**" in its lower right corner, identifying it for further decomposition.

**3. Level A4: Second Decomposition (Bottom Right)**
- **Visual Elements**: The parent "**A4**" box from the previous level is further expanded into a granular diagram containing three sub-activity boxes numbered **1, 2, and 3**.
- **Hierarchy Link**: Dotted lines indicate that this diagram represents the internal functional detail of the A4 activity.

**4. Core IDEF0 Principles**
- **Functional Decomposition**: The process of breaking a complex parent activity into more manageable and specific sub-activities.
- **ICOM Consistency**: Arrows (Inputs, Controls, Outputs, Mechanisms) entering or exiting a parent box must be consistently represented at the boundary of the child diagram to ensure model integrity.
- **Granularity**: The level of technical detail increases as the hierarchy progresses from the context diagram down to subordinate levels.
# Activity

The main component of the diagram is the activity

Represented by a rectangle   
> Labeled with a noun or verb that describes it   
>Identified by a number in the lower right corner

For reasons of readability，a maximum of 6 activities can be entered in a diagram

> If more activities are needed, an additional level of detail must be introduced

# Arrows

The meaning of the arrows depends on their position with respect to the activity

> the arrows entering from the left side represent the inputs entered (the one that is processed during the activity)   
>the arrows coming out from the right side represent the outputs produced (the results of the activity)   
>the arrows entering from the top represent the constraints (controls) that regulate or affect the execution of the activity   
>the arrows entering from below indicate the resources (physical tools or people) that make it possible to carry out the activity

### Visual Diagram: IDEF0 Arrow Syntax and Positioning
- **Component Type**: Standard syntax for functional modeling blocks.
- **Logic**: The meaning of each arrow is determined by its specific position relative to the activity box.

#### 1. Input (Left Side)
- **Visual Shape**: A horizontal arrow entering the activity box from the left.
- **Functional Meaning**: Represents the objects or data that are processed or transformed during the activity.
- **Annotation**: Includes a "LABEL" linked to the arrow via a zigzag line to identify the specific input.

#### 2. Control (Top Side)
- **Visual Shape**: A vertical arrow entering the box from the top.
- **Functional Meaning**: Represents the constraints or controls that regulate and affect how the activity is executed.

#### 3. Output (Right Side)
- **Visual Shape**: A horizontal arrow exiting the box from the right.
- **Functional Meaning**: Represents the results or products generated by the completion of the activity.

#### 4. Mechanism (Bottom Side, Upward)
- **Visual Shape**: A vertical arrow entering the box from the bottom, pointing up.
- **Functional Meaning**: Indicates the resources, such as people or physical tools, that make it possible to perform the activity.

#### 5. Call (Bottom Side, Downward)
- **Visual Shape**: A vertical arrow exiting the box from the bottom, pointing down.
- **Annotation**: Specifically labeled as "CALL" with an associated "LABEL" for reference.
- **Functional Meaning**: Used to indicate a reference to another diagram or a specialized system element.

# Parallel operations

### Visual Diagram: IDEF0 Parallel Operations
- **Component Type**: Control-driven functional branching.
- **Operational Logic**: Concurrent execution of downstream activities based on a shared dependency.

#### 1. Primary Process (Node 1)
- Process 1 serves as the prerequisite activity in the sequence.
- Upon completion, Process 1 generates an output that functions as a synchronization point for the rest of the flow.

#### 2. Control Branching
- The output arrow exiting Process 1 branches into two distinct paths.
- Both branched arrows enter the top faces of the subsequent boxes, acting as "Controls" for Process 2 and Process 3.
- This configuration dictates that once the output of Process 1 is available, both activities 2 and 3 can start simultaneously.

#### 3. Parallel Execution (Nodes 2 and 3)
- Process 2 and Process 3 are executed in parallel rather than in a serial sequence.
- Each parallel process generates its own independent output flowing to the right.
- This structure is used to model system functions that happen at the same time once specific conditions (the output of Node 1) are met.

# Difference between input and control

### Visual Diagram: IDEF0 Functional Flows - Input vs. Control (image_fe3118.png)
- **Component Type**: Comparative analysis of functional dependencies.
- **Logic**: This diagram illustrates how the same output from a parent process can function as either a physical input or a logical control for a subsequent process.

#### 1. Physical Flow: Input (Top Diagram)
- **Context**: Focuses on the transformation of a physical object.
- **Process A1 (Drilling)**:
    - **Input**: "Blank plate" (raw material enters from the left).
    - **Control**: "Work cycle" (governs the drilling).
    - **Mechanism**: "Drilling machine".
    - **Output**: "Drilled plate".
- **Process A2 (Polishing)**:
    - **Input**: "Drilled plate" (The output of A1 enters from the **left** side of A2).
    - **Mechanism**: "Polisher".
    - **Output**: "Polished plate".
- **Functional Meaning**: The output of the first stage is the **subject** of the second stage; it is physically processed/transformed further.

#### 2. Logical Flow: Control (Bottom Diagram)
- **Context**: Focuses on the governance of a production activity.
- **Process A1 (Design)**:
    - **Input**: "Template".
    - **Control**: "Requirements".
    - **Output**: "Work plan".
- **Process A2 (Production)**:
    - **Input**: "Raw materials".
    - **Control**: "Work plan" (The output of A1 enters from the **top** side of A2).
    - **Mechanism**: "Equipments".
    - **Output**: "Finished product".
- **Functional Meaning**: The output of the first stage acts as a **directive** for the second stage; it dictates *how* the production is executed without being physically incorporated into the product.

#### 3. Key Distinction Summary
- **Input Connection (Left)**: Represents a material/data dependency where the item is "consumed" or "modified".
- **Control Connection (Top)**: Represents a logical dependency where the item "constrains" or "regulates" the activity.

Physical flow: input

Logical flow: control

# Example: production management

### Visual Diagram: IDEF0 Production Management Context
- **Node**: A1
- **Title**: Production
- **Focus**: Coordination of manufacturing stages from raw material receipt to final delivery.

#### A11: Raw material inventory
- **Input**: Current warehouse inventory (starting state).
- **Control**: Transport document, Customer order (regulatory triggers).
- **Mechanism**: Warehouse department (responsible resource).
- **Output**: Updated warehouse inventory (flows to A12 and exits as a record).

#### A12: Production planning
- **Input**: Updated warehouse inventory, Current employee load.
- **Control**: Customer production plan (strategic constraint).
- **Mechanism**: Planning department.
- **Output**:
    - **Logical Control**: A shared planning signal that governs A13, A14, and A15.
    - **Physical Record**: Update employee load.

#### A13: Assembly
- **Input**: (Implicit material flow from inventory).
- **Control**: 
    - Technical documents: Drawings, BOMs, Assembly/Control plans, Tuning procedure.
    - Planning directive (from A12).
- **Mechanism**: Production department.
- **Output**: 
    - Assembly report.
    - Physical flow (Assembled components) to Quality Check and Packaging.

#### A14: Quality check
- **Input**: Assembled components (from A13).
- **Control**: 
    - Test procedure.
    - Planning directive (from A12).
- **Mechanism**: Quality department.
- **Output**: Certificate of conformance (validation result).

#### A15: Packaging and delivery
- **Input**: Verified product (from A14).
- **Control**: Planning directive (from A12).
- **Mechanism**: Warehouse department.
- **Output**: Delivery note (final shipping document).

#### Summary of Flows
- **Material Path**: Flows linearly from A11 through A15 via internal inputs.
- **Control Path**: A12 acts as the "brain," providing the necessary constraints for all subsequent manufacturing steps.
- **Shared Resources**: The Warehouse department supports both the initial (A11) and final (A15) stages of the value chain.

# Observation

In IDEFO there are no decisions,only flows

### Visual Diagram: IDEF0 vs. Flow Charts - Absence of Decisions
- **Component Type**: Comparison of process modeling logic.
- **Core Observation**: IDEF0 models do not use decision nodes (diamonds); they represent logic through the differentiation of functional flows.

#### 1. Traditional Flow Chart / Activity Diagram (Top)
- **Visual Elements**: Sequential boxes connected by arrows, including a diamond-shaped decision node.
- **Logic**: 
    - The process starts with "Receive shipment" and proceeds to "Compare shipment with purchase order."
    - A binary decision point "**Shipment OK?**" explicitly branches the path.
    - Path **Yes**: Leads to "Catalogue book."
    - Path **No**: Leads to "Return to vendor."
- **Meaning**: Represents the temporal sequence and the specific "if-then" choices made during execution.

#### 2. IDEF0 Functional Model (Bottom)
- **Visual Elements**: Functional blocks with ICOM arrows; no decision symbols are present.
- **Activity "Receive each book"**:
    - **Input (Left)**: "Receipt of book" (the physical object to be processed).
    - **Control (Top)**: "Books ordered" (the rule or reference used to verify the receipt).
    - **Outputs (Right)**: Two distinct output arrows represent the different results of the activity's internal logic:
        1. "**Returned book**": Flow for items that do not meet the criteria.
        2. "**Book, book information**": Flow for items that pass verification, which then becomes an input for the next activity, "**Catalogue book**."
- **Meaning**: Represents the function's transformation and its possible outcomes. The "decision" is embedded within the function "Receive each book," and the results are expressed simply as different output flows.

#### 3. Key Distinction
- **Flow Charts**: Focus on the **sequence of steps** and the explicit gates (decisions) that control the flow.
- **IDEF0**: Focuses on **what the function does** and the data/objects it produces. Logic is handled by having multiple inputs or outputs that represent the different conditions or states of the objects being processed.

# Characteristics

V Provides a reference architecture for business analysis, information engineering and resource management   
Allows the management of large and complex projects   
V The cost of a function can be computed based on the costs attributed to its component activities   
Diagrams are easy to read even by non-technical people

V Top-down decomposition, elimination of choices

# Example: breakfast distribution

V A breakfast is served every morning in a hospital department. Breakfast consists of liquid food (milk, tea,coffee)，dry food (cookies,croissants, etc.), jams and sugar packets.   
Breakfast is brought to the patients using special wheeled cabinets. The preparation of the cabinets takes place in two phases: in the evening, the workers fill the cabinets with dry food, sugar and jams; in the morning, they heat the hot food using the tools in the kitchen and place them into the thermos on the cabinets.   
V Breakfast is distributed by the distribution staff. The cabinets are transported from the kitchen to the departments using an elevator. The staff deliver the breakfasts to the patients and then bring the cabinets back to the kitchen.In the kitchen the cabinets are washed to be ready for a new use.   
V Represent the process using the IDEFO diagram using no more than two levels of detail.

# Solution (A-0)

### Visual Diagram: IDEF0 Context Diagram (A-0) - Breakfast Distribution
- **Component Type**: Top-level Context Diagram (A-0).
- **Logic**: Defines the global boundaries and primary interfaces for the hospital breakfast process before further decomposition.

#### 1. Central Activity Box (A0)
- **Internal Label**: "Breakfast preparation".
- **Node Identifier**: A0.

#### 2. Interface Arrows (ICOM Architecture)
- **Input (Left side)**: Represents the raw materials to be processed: "Dry food", "Liquid food", "Jams", and "Sugar packets".
- **Controls (Top side)**: Represents the regulatory constraints: "Preparation, transportation and delivery instruction".
- **Output (Right side)**: Represents the final results of the process: "Breakfasts served, clean cabinets".
- **Mechanisms / Resources (Bottom side)**: Represents the tools and personnel required: "Wheeled cabinets", "Hospital workers", "Kitchen tools", "Freight elevator", and "Dishwasher".

#### 3. Model Metadata
- **Node**: A-0.
- **Title**: Breakfast distribution process.
- **Purpose**: Hospital breakfast distribution process.
- **Viewpoint**: Responsible for managing hospital meals.

#### 4. Functional Meaning
- This diagram establishes that the process transforms food supplies into served meals using hospital staff and infrastructure, under specific delivery instructions, and concludes when cabinets are cleaned for the next cycle.

PURPOSE: Hospital breakfast distribution process

VIEWPOlNT: Responsible for managing hospital meals

# Solution (A0)

### Visual Diagram: IDEF0 Functional Decomposition (A0) - Breakfast Distribution
- **Node**: A0
- **Title**: Breakfast distribution
- **Logic**: Decomposes the high-level process into three sequential activities, showing the internal flow of materials and information.

#### A1: Preparation
- **Inputs**: Raw materials entering from the left: "Dry food", "Liquid food", "Jams", and "Sugar packets".
- **Control**: "Preparation instructions" (Top).
- **Mechanisms**: "Wheeled cabinets", "Preparation staff", and "Kitchen tools" (Bottom).
- **Output**: "Cabinets with breakfast", which functions as the physical input for the next stage (A2).

#### A2: Distribution
- **Input**: "Cabinets with breakfast" (from A1).
- **Control**: "Distribution instructions" (Top).
- **Mechanisms**: "Freight elevator" and "Distribution Staff" (Bottom).
- **Outputs**: 
    - "**Breakfasts served**": The primary goal of the process, exiting the diagram.
    - "**Cabinets to clean**": The byproduct (dirty equipment) which becomes the input for the final stage (A3).

#### A3: Washing
- **Input**: "Cabinets to clean" (from A2).
- **Control**: "Washing instruction" (Top).
- **Mechanisms**: "Dishwasher" and "Washing staff" (Bottom).
- **Output**: "**Clean cabinets**", exiting the diagram to indicate the completion of the cycle.

#### Summary of the Internal Flow
- **Sequential Dependency**: The diagram uses a "staircase" layout to show a clear linear sequence where the output of one function is the necessary input for the next.
- **Resource Specialization**: The mechanisms change across the activities, moving from kitchen tools (A1) to transport infrastructure (A2) and finally cleaning equipment (A3).
- **Control Specificity**: Each stage is governed by a specific set of instructions, ensuring quality and safety throughout the transformation from raw ingredients to cleaned assets.

# Solution (A1)

### Visual Diagram: IDEF0 Functional Decomposition (A1) - Preparation Detail
- **Node**: A1
- **Title**: Preparation
- **Logic**: This diagram breaks down the "Preparation" phase into two distinct sub-activities based on the nature of the food items and the specific timing constraints (evening vs. morning) described in the process.

#### A11: Dry food arrangement
- **Inputs**: "Dry foods", "Sugar packets", and "Jams".
- **Control**: "Preparation instructions".
- **Mechanisms**: "Wheeled cabinets" (acting as the physical base) and "Preparation Staff".
- **Output**: "**Cabinets with dry food**", which serves as the primary internal input for the next stage.

#### A12: Liquid food arrangement
- **Inputs**: 
    - "Cabinets with dry food" (internal flow from A11).
    - "Liquid food" (new raw material entered during this phase, typically in the morning).
- **Control**: "Preparation instructions".
- **Mechanisms**: "Preparation Staff" and "Kitchen tools" (required for heating liquid items).
- **Output**: "**Cabinets with breakfasts**", representing the completed units ready for distribution (A2).

#### Process Logic
- **Sequential Dependency**: The diagram illustrates that cabinets must first be staged with dry goods before hot liquids can be added, adhering to the evening/morning schedule constraint.
- **Shared Resources**: The "Preparation Staff" is a constant resource across both sub-activities, while "Kitchen tools" are specifically allocated to A12 for the thermal processing of liquid foods.

# Exercise: Car repair shop

V The customer requests an offer for the production of a specific mechanical component. The formulation of the offer involves two company functions: the technical sector and the administrative sector. The technical sector provides a general description of the manufacturing process,from which the administrative sector defines the costs and define the amount of the offer. The customer evaluates the ofer received and if he considers it valid, sends an explicit order to activates the production.   
From this moment the company is formally engaged in the fulfillment of the order and starts the appropriate administrative and technical procedures. In particular, the technical sector define the process plan with the list of operations that must be performed to transform the raw material into a finished product. On the basis of the process plan,the administration arranges to order the raw materials. Production planning is also carried out from the information contained in the process plan, giving rise to the production plan.   
> Once the raw materials have been received and the production plan is ready, processing is carried out. At the end of the processing, a quality control of the product is carried out with which the compliance with the project specifications is established. The process ends with the invoice emission and the payment of the customer.

# Solution (A-0)

### Visual Diagram: IDEF0 Context Diagram (A-0) - Order Fulfillment
- **Node**: A-0
- **Title**: Order Fulfillment
- **Logic**: Defines the overall system boundary for the mechanical component production request.

#### 1. Interface Arrows (ICOM)
- **Input (Left)**: "Raw Materials" (The base resources required for production).
- **Control (Top)**: "Customer Request" and "Customer Order" (The triggers and regulatory documents).
- **Mechanisms (Bottom)**: "Technical Department", "Administrative Department", and "Equipments" (The resources executing the process).
- **Output (Right)**: "Finished Product" and "Invoice" (The final results provided to the customer).

#### 2. Functional Meaning
- Represents the high-level transformation of raw materials into a finished product and invoice based on customer requirements and orders, utilizing specialized company departments.

# Solution (A0)

### Visual Diagram: IDEF0 First-Level Decomposition (A0)
- **Node**: A0
- **Title**: Order Fulfillment
- **Logic**: Splits the process into two primary phases: Commercial (Offer) and Operational (Production).

#### A1: Offer Formulation
- **Control**: "Customer Request".
- **Mechanisms**: Technical and Administrative Departments.
- **Output**: "Offer" (This flows forward to act as a control for the next phase).

#### A2: Production
- **Input**: "Raw Materials".
- **Control**: "Offer" (from A1) and "Customer Order" (external).
- **Mechanisms**: Technical/Administrative Departments and Equipment.
- **Output**: "Finish Product" and "Invoice".

#### Functional Meaning
- This level establishes that production cannot legally or technically begin until an "Offer" is formulated and a "Customer Order" is received.

# Solution (A1)

### Visual Diagram: IDEF0 Decomposition of A1 - Offer Formulation
- **Node**: A1
- **Title**: Offer Formulation
- **Logic**: Details the internal collaboration between technical and administrative sectors to generate a quote.

#### A11: Process Definition
- **Control**: "Customer Request".
- **Mechanism**: Technical Department.
- **Output**: "**Process Plan**" (A general description of manufacturing steps).

#### A12: Cost Definition
- **Input**: "Process Plan" (from A11).
- **Mechanism**: Administrative Department.
- **Output**: "**Cost Plan**" (Financial valuation of the process).

#### A13: Offer Formulation
- **Input**: "Cost Plan" (from A12).
- **Mechanism**: Administrative Department.
- **Output**: "**Offer**" (The final document sent to the customer).

#### Functional Meaning
- Shows a linear dependency: costs cannot be defined without a technical process plan, and the offer cannot be finalized without a cost plan.

# Solution (A2)

### Visual Diagram: IDEF0 Decomposition of A2 - Production
- **Node**: A2
- **Title**: Production
- **Logic**: Represents the operational flow from detailed planning to quality control and invoicing.

#### A21: Process Definition
- **Control**: "Offer" and "Customer Order".
- **Mechanism**: Technical Dept.
- **Output**: "**Process Plan**" (Detailed list of operations).

#### A22: Production Planning
- **Input**: "Process Plan" (from A21).
- **Output**: "**Production Plan**".

#### A23: Raw Materials Order
- **Input**: "Process Plan" (from A21).
- **Mechanism**: Administrative Dept.
- **Output**: "Raw Materials" (Procured for processing).

#### A24: Processing
- **Inputs**: "Raw Materials" (from A23) and "Production Plan" (from A22).
- **Mechanism**: Equipment.
- **Output**: "**Product**".

#### A25: Quality Controls
- **Input**: "Product" (from A24).
- **Control**: "Process Plan" (Used as a reference for specifications from A21).
- **Output**: "**Finished Product**".

#### A26: Invoicing
- **Control**: "Finished Product" (The trigger for billing).
- **Mechanism**: Administrative Dept.
- **Output**: "**Invoice**".

#### Functional Meaning
- This diagram highlights the "Process Plan" as a central control hub that dictates material ordering, scheduling, and quality standards.
