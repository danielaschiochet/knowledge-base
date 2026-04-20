# Analysis and Management of Production Systems

# Lesson 01: Formalisms for manufacturing process modeling

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Importance of formalism

Problem of making customers/colleagues with different backgrounds to understand the process to reach the solution of a problem   
Everyone reasons and expresses concepts according to their own cultural background   
V distance of languages

![](images/6fc5b824762183715ab5da253a4d01947f56d7af351c498723a75c2cb890d919.jpg)

![](images/817d22f6ddc4c9fcb158f4ad03ca81555fe18c1cfca3d6af142a1649423febfb.jpg)

# Communication problem

Metaphor of the swing   
Problem of using words to describe processes   
Importance of being able to formalize a process to have an effective communication

![](images/225d52996811bb411cb2429aad0e9b5914424cb50769b481d6441b7f46eb9483.jpg)  
As proposed by the project sponsor (propostadal committente)

![](images/afc285ef82b49d97a54928b53a1e5cd55b8fb129054750c85a00e974b18265e1.jpg)  
As produced by the programmers (prodottadaiprogrammatori)

![](images/30a24fab0ae25bc99cae2a6c98e1e506a00cbb33cf89d96a4cd1ee5f5a005d0e.jpg)  
As specified in the project request (specificata nei requisiti)

![](images/2116effbd6e926073eaf478f10a0ca7097fad5f3fcca33a4e2464aa33da42a84.jpg)  
As installed at the user's site (installatapressof'utente)

![](images/85b3ee3dec008364ed7899e4b081e8d6eb6564496991779d1e0d23731f091f78.jpg)  
As designed by the senior analyst (progettatadall'analista)

![](images/b0b6a13361b448f68767746836e9138a6209529547492e0e6a35a9a6836e2c21.jpg)  
What the user wanted   
(cio chef'utentevoleva)

# Importance of processes in production systems

Processes are used to manage a product during its whole Product Lifecycle

Plan   
Design   
Implement   
Support   
Disposal

![](images/7d721492f9d7c6775931b419b6fcf922718d7abd68776fb5b1a3c167a4dbd591.jpg)

# Process definition

A process is characterized by a series of activities linked together to provide a certain output given a certain input

![](images/f369de232db3e730a6190f2e461896ea70ed35f78fdd9e92b4bb6f20aedf9d11.jpg)

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

![](images/793c5aba4185bdfc75d103e9a3a397d982aae7853be581f769e4cbdcce7b287b.jpg)

Start and End

![](images/dc52557947df7ae3eb9ad08b8e6c620cb1fbaf20c523fe218667938a08e6a86e.jpg)

Activity

![](images/6624660e11cc1e21400de932bd1fe7618fc0ad9f77adebed04bbdb500f6f0326.jpg)

Decision

![](images/4e72e32d02f9fb37d0cb773628bcb9ea13379766a67a5703979eda570549a796.jpg)

Input/output data

![](images/c0b7d3e9e201ee3526eba5d6c7792c8a11ec7e8076989c0e8c4961bf233890fa.jpg)

Flow control

# Example: Customer support service

![](images/aa6a00b793c206c7651ea7922b0bc13525627ecb67be87a13bcd9115f29ab0c2.jpg)

# UML Activity Diagram

![](images/80f1fa0bdaaa6ed4e888c9f95daede98b450cdfe7b32798fa73195333ace6dd8.jpg)

Initial state

![](images/e7e5975375cb18bf6b8566cd7ef3caf9ea356884a113f1ec7b07412675f31925.jpg)

End state

![](images/2f1e031f1e9b3e21375e51e240d1cea0d2f7720bf76a994468b264805128c1f0.jpg)

Activity

![](images/2acefb96c3abbc6cb0ebc00ff2fa6eae24a2b00ab387985105c0518361c2b63a.jpg)

Decision

![](images/fb36934457634881bb4a5ba7c84b0e08e82c719c070947cf1b88b7f0a30beb9a.jpg)

Fork and Join

![](images/61e20d3695dbee92f46fc847c0cc6d765cd3c29ed4d77b28fa9cb0e13d18f372.jpg)

Flow control

# Example: order management

![](images/47198cf0c56dcbaa78c67a9183e5c1119aefd31fa5f67ad0ef55902bf64ec936.jpg)

# Business process model and notation

Based on popular graphical flowcharts:

Core set of notation elements   
Each core element has various subtypes

![](images/f6987c41d2ae908f569d232df5babf67e284d8adeaf68cae6eed324379f8b979.jpg)  
activity

Activities capture work performed in a process

![](images/df402f1a51922bd78408afe765c0fb8647ad967c3f047350edd18a577897c993.jpg)  
event

Events represent the process' triggers (start event) and outcomes (end event)

![](images/7e247ff621f581aceb4c2e8ca034610db163ba00f24040ba6db47a47bc612a60.jpg)

![](images/bca067349814232fc8e81df08600d3f3b93330e05f503f9b53ca58ae23e4964c.jpg)  
gateway

Gateways capture forking and joining paths in the control flow

![](images/eaf037dd9a18259c5cd4cae3a989fb8b634776c5d28e1a68c8a26b65c7124e37.jpg)  
sequence flow

Sequence flows represent the order in which activities and events will be performed

# Example Order-to-cash

![](images/158d362438dcd8a6efb4c84f661f0ce4162e56ac3a74c50b9d677c90dd1372f9.jpg)

# Flow process chart

V Many physical and manual processes consist of a sequence of simple actions, such as transport, waiting or inspection   
> ldentifying these simple activities makes it easier to find ways to improve the process   
When to use it:

>To provide a detailed description of a physical process by representing the individual activities in sequence   
>To analyze processes to identify and eliminate waste   
>To represent process with few decision blocks

> Uses the American Society of Mechanical Engineers (ASME) symbols

# ASME symbols

Activity, changes physical or chemical material characteristics   
Transport, movement of people or material (distance measures could be included)   
Waiting, for material arrivals or machines availability   
Warehouse, for material storage   
Inspection,material quality and quantity control

# Example: Baking Cookies Factory

> A cookie factory decides to analyze how to improve its process   
> In the current process the cookies are formed after introducing the dough into the mould, then they are baked in the oven,cooled on a cooling belt and inspected on an inspection line   
>8.2% of the cookies do not pass the shape control and are discarded,the rest of them are packed for shipping

# Flow process chart

The main flow follows a vertical line from the top to the bottom   
Alternative flows representedon parallel lines   
Numbers for counting the symbols of the same type   
Description at the right side of the activity

![](images/0c58775dbc6a634463c45134af6091da690674859a2fe7fd460de7a20a67e327.jpg)

# Observations

Analyzing the material flow,you can see that the shape quality rejection rate is very high   
V A simple improvement could be to introduce an inspection immediately after the manufacture of the cookies,before baking, since the raw dough is easier to re-mix   
V With a successive intervention, the mixing and molding processes can be improved to further reduce the rejection rate

# Example: reengineering comparison

![](images/f6306e34710313df6ccaa9b313b440bb63517259ebce8e721cd969db200bd2b9.jpg)  
Present State

![](images/2f54f8db461ac724f962fc7899efd8fe690fc21ee3aab1bc1d23aba20b751ac6.jpg)  
Future State

# Example: packaging process

![](images/15088f822d98f32ea545de7e21edea7af48d810b5dd240d990b81ca70e27b8bf.jpg)

Store of waste paper

Convey to mixer

Pulping and mixing

Convey to forming machine

Forming (Moulding)

Drying

![](images/8df70ca9bc8adb24f29e56cdcbb569e564dd2e134bf7b561e48f3a8e7a8bc600.jpg)

Inspecting&counting

Stacking

Packing

Convey to warehouse

Store at warehouse

# Example: chair assembly

![](images/a9fd4474db5b6d0611d7c75068d0a1405579cb904313ba0b483f70ffa625628e.jpg)

Flow Process Chart   
![](images/2f4e4ccbd05f03b9ae2395efa6d77612f5dc0d76399a0cd7bba9a66d8e541ece.jpg)

# Exercise: paper factory

V The wood is partly purchased from a supplier and partly produced in the company's own forests. The wood is conveyed through an artificial channel to the covered storage area. From there,it is taken to be cut in the chipper, where the dimensions are made uniform to the standard size of 1x1/4 inch. Wood chips that are too large are returned to the previous station,and those that are too small are removed. The chips are then stored in silos.   
V Lignin is removed from wood chips by boiling them in caustic soda and sodium sulphide solution. Then the chips pass into a low-pressure discharge vat which physically separates the fibres.The wood fibres are then centrifuged and pressed. The pulp produced in this process is finally subjected to bleaching and then put to rest in the warehouse.   
The paper is produced starting from the pulp in a dedicated machine,in which the pulp is deprived of part of its content in water and compressed in steam-heated cylinders. Then it is wrapped in large reels and stored. When delivered to the customer it is cut and rewound into smaller reels.

# Solution

![](images/8cb29e0d1ce32f12f936e0c23031698895f8597f2212841687c7e6d16563508e.jpg)

![](images/5fa179c2c52bfeeb1164ef3f2fe1fcf54de52c531916196a2a153deee258ff2e.jpg)

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

![](images/4959f9073151ea975b7de961f410e01c8efbeb5b93d6eb1df61ebb66f9a19885.jpg)

![](images/ea143be3fc191f1bb9b7709c316e6df3e538e08c609419853918c2d9ca93edfb.jpg)  
Lead time ladder

# Formalism

The manufacturing process mapping is performed using a series of simple unified icons

These icons can represent both physical flows and information flows of the production planning system (e.g., an MRP system)

# SIMBOLI RELATIVI AL FLUSSO(FISICO,INFORMATIVO,TEMPORALE)

![](images/a6f7c22c5334d56e37d1f1e5a349e166c69d4add9e19ec10245fe1b7b89a506a.jpg)

Flusso fisico

![](images/6c78326f642afdc7d92b9ddfdb18aa213d399b7f9c62ccfca983d578e0cb8d09.jpg)

Informazioneelettronica

![](images/4b18c44f4c1d539b59c369c3be97453703cbc1d8c32040fcf4ce19638c61c3cc.jpg)

Informazione manuale

![](images/b53edd15de1549927e595081324dc6b9a7745c8cecd2eec73bc97892574444f3.jpg)

Flusso fisico in ingresso/uscita dall'azienda

![](images/8f71d5e3ebbbb4d220a98396b6cc446c995f4ca1897635b8383270f599722fa9.jpg)

Time Line

# SIMBOLIRELATIVIAI PROCESSI INTERNI ED ESTERNI

![](images/a99387012b636148d4cf89c5e1b29dee4b700917bdd15c9400a738379aa051e8.jpg)

Process Box

![](images/49fbf55f188450d34b69ea789b8d4049bffca728cbdfc87932ef9745c654b776.jpg)

Process Box (processi multipli)

![](images/5e14a8ae47bc76e6cac06e872d9b76184a2f2b5a52d9e04055d6da54e6b27a0c.jpg)

Process Box（generico）

![](images/70c801118eb818cea92a8b8a29505cb14da8481294b0f7560b81ddad71a13449.jpg)

Fornitore esterno,cliente esterno

![](images/40fe1503618b9c43eabb7292e0e6eda2a248b09546dc54c2970d51c3f15c8b8f.jpg)

Informazioni relative al Process Box

![](images/622fe06a51236bb976d1f96b761d9321f6ed2202b354d1ab9181bd71f30a0c1e.jpg)

Magazzino

![](images/5aa23a10f18c411998bf71beec0b35705109c3be16ca4cf8b75b10e52856dbec.jpg)

Operatore

![](images/18f106386d0cc70188529097cd8633a800d4cb14b4a0174efcf2631f4f4575e2.jpg)

Processo assistito dacomputer(MRP)

# SIMBOLIRELATIVIALMIGLIORAMENTO DEIPROCESSI

![](images/b635a7d5b3d3fb53ad3e3672eae88e825eb73d908c6bcc884d0558b4fa7c8e5a.jpg)

Obiettivo kaizen

![](images/8ccff41a3cdffcd885c06caad8c7778385a5359e0afe56466f8a562b69e3ce9c.jpg)

"Supermarket"

![](images/965b763dafd4f12252121e6e7fc0b4b331ee9db3517f928375fcea1a42351f86.jpg)

Postazione kanban

![](images/7d1b29b9612a1bb3da71dbaf5238bad7f868519cc3ba4766ebd3f2c048151243.jpg)

Flusso kanban

![](images/acdf459fb9d75d8129b977b7e21e079fd09612e45a5c923408ec9ac446d789ec.jpg)

Kanban"ordine di produzione"(Production)

![](images/77b5cf255cbdbfed5ce98ea79ee47d67c955cb170b119cf29f75ab6f75e746f6.jpg)

Kanban"prelievo"(Withdrawal)

![](images/0eb00ea3e880e02cd87a1ebbf1282370b7800d114cb99f9c9cb89bf00657b67b.jpg)

Kanban"segnale"（Signal)

![](images/cd9f487e18c0b004113cfac1fb6fd67a09852bf4c943f1f6510aec7cf33840ee.jpg)

"corsia FIFO"

![](images/3f96a36b0666b8305c68b9fc4b2f044e96cd97d400b184033888fcdc619bd370.jpg)

Cella produttivaa forma di“U"

![](images/ee2865bf0f877910073df29f66e631313e2a8c2e4d478ae1de00072a16572f8b.jpg)

Magazzino"buffer"

![](images/f0d787a638578e840cccaf9f7e1e294132096b3ae753f55902cc506ba4bab048.jpg)

Scorte di sicurezza

# Formalism

The manufacturing process mapping is performed using a series of simple unified icons   
> These icons can represent both physical flows and information flows of the production planning system (e.g., an MRP system)

![](images/6f716347908b840408d096e90df66496d85388158848074aba0ee9028953a8ce.jpg)

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

![](images/1b75a2e110312be550221c7b83bf583fede9c04b73888ee86ee845fb3017c38f.jpg)

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

![](images/29bd8a4f7027c25b34c93f2aa50e896e3720bac16fc4ae700aff2ca4ed78f6b0.jpg)

![](images/9405652db932f974e58b0128093c3869f74d609e46c0211b3759ea9265a7985b.jpg)

![](images/ad0424bfdbe63229c1a8d5514eb4856955385cc6d8b69f85803ea73acb5fb778.jpg)

# Inventory

> It shows the accumulation of products between processes   
> It can be expressed in terms of WIP or time,while in the services and offices it can be understood as pending files, emails to be processed, etc   
V Traditionally the icon is a triangle, as it represents a significant danger in terms of waste.

![](images/e81546645dc5893151cb18c67d2c37cf3b3efc254d1f021c87b847861797a48e.jpg)

300 pezzi   
2 Giorni

# Striped arrow

>Represents the material flow between two stations   
>Indicates a "Push" type flow

![](images/804cb7f34539bd2fb23e42a73f33cb3471eb68f0ac76ec3b1119e9b5e60455ba.jpg)

# White arrow

> Represents the movement of raw materials from suppliers   
>Represents the movement of finished products towards customers

# Way of transport

Icon to represents the transportation adopted

>Truck   
Rail   
>Ship   
V Plane

Frequency of supplying and/or delivery is indicated

![](images/1edf5433047f74b5d937f8d17eb58dbe360e5be1c0dd5235770651e4c942d3a8.jpg)  
Daily

![](images/7cf206c0b8ea2c5a027a29244f0dacae59f4276c5b2b567bc7e8f230c9597878.jpg)  
Weekly

![](images/e43a6a869bf0fda968013bb1385da7ae31300800c623e6c8c9d5dfad73b67a95.jpg)  
Montly

![](images/adcd53a9a44c1e012db453e4836fa80ee5dc2ddef6547cbb06e2dff565703615.jpg)  
Twice x week

# Information Flow

Straight arrow

>Manual information flows (fax,e-mail, telephone, etc.)

Lightning arrow

Electronic information flows

Information Label

> Specify the type of information   
> It is shown above the arrows of the information flow

![](images/2755351d4f6cf24d78370669ef78e803aa85d60a386943a811b477aa2bcd19eb.jpg)

![](images/6ae1924a9640eec58e2da8f40e40d0824aff5820ce303339321f69d7c364c77e.jpg)

Schedulazione settimanale

# Timeline

> The Timeline shows the overall Lead Time given by the sum of the processing, handling and waiting times.

>The low line means that the product is within the process, and it will be worked for different time (it is the time in which the product is processed on the machine)   
>ln the high part of the line are indicated the waiting times

![](images/943aa031c7f99af8dd21ef4ccd16bc1a3cbfad4f884ebaa1621dffba472d127c.jpg)

# 1.Process flow identification (Data box)

# Identification and mapping of the main phases

![](images/ad90fde4794f0b39361d073b6feb2b5f9288de8e749a4d3eaae4d1a745ca965c.jpg)

# 2.Material flow identification

>Material flow from supplier to customer

![](images/6aaf56a8ef7989e593fcd1ce54d9e5241f79334100ea0483def5c607e0565752.jpg)

# 3.Time information

Timeline Design   
>Cycle Time, Waiting Time e Lead time

![](images/b6cf32dc15820fa8d183464cbe01975dd089f433ffca92c6bf2d8cfcbff3ed9a.jpg)

# 4. Add Information Flows

![](images/d4db4ddd657f15c1ceea86223e54e5de0cf0096386c32182eb9b0b5753123497.jpg)

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

![](images/24aa6489c94c9977d052f16701b7104205b72bd85465092e9429b1b8eb15672e.jpg)

500ft coils

![](images/efb17a877f25729c91d85083088621d88a66251126546bde5f6f6f8dd77cfbd8.jpg)

Insert the Supplier and Customer icons,with the relative Data Boxes containing the total quantities to be supplied for a given period and calculate the necessary daily production and the load unit type/characteristics

# Example solution

![](images/0a96de4bc9b66a63525e9dd27655b50fc68b0d4e44cdb75edb15d75c63c33966.jpg)

500ft coils

![](images/6691c95d1886cc2396b24c145bd2f64a5dd5461eef4e377d83b4f227bd16221a.jpg)

Draw, from left to right, the Process boxes and the corresponding Data Boxes related to the internal operations/stations of the component under analysis (e.g., the production flow of the component)

![](images/5b48d780e2faa34d03b319230d7667effe41a5d26cb47bd456d8d9b46458d80a.jpg)

Coils 5days

![](images/7d89dc7cb5b5381ece2ce40bd7e7e25d0204f3bc39e3bcd5e31212de171a9d7b.jpg)

![](images/abd23f06877c56e9ef83582a74be793d136c41266d720d4f632be07c76b21ce1.jpg)

![](images/734a813f4d91a0a81e606eaf4dcb366ea09d1b89f8e55f86d0d227097ee061e6.jpg)

![](images/9b6116b1d3c35ba3f8b984c6d23d381036e61e5208a4a0b70a93cfc47236f172.jpg)

![](images/c9bcfe8472b1ac4c9b04a0c72b997211041501da7644479307c28a11d557e823.jpg)

![](images/6514d3a5db81e199b0c3158b86569b04cbce32c2085a4cb8d5f8a74be4505160.jpg)

![](images/2373ee346265cc64ae80c02f3602729146a2a7bb04e08bbbcdd3f4c6b50d599c.jpg)

![](images/6d6b484583dd5e419c317237d728a5d33596e1ca5c4c1e611ba0f952255b945b.jpg)

![](images/36d096c456c037c3b0987f9bc73a806e1a94e8e3907a9594f839fbf35b865972.jpg)

![](images/6de912443f588693fe1d0fe4024501e12914c209cfa6893758474002671a3f77.jpg)

![](images/68e2b8143e7a9229ba5bccdd11c114f957aea7a2ab59ab943c333e5ab9fbc376.jpg)

![](images/bf8859f0188d28a00d8ecb593ac5adb51f5c36d870a0382e5940f570019d3ac9.jpg)

![](images/f2e46cea6c8b771d4120739cb1158ae059e18e52e1aa5ed31086989d85c68770.jpg)

![](images/9e86d055c0b2801d92975d42edee775fd6a5920ed21b915390b80d04c1e77ddb.jpg)

![](images/0f47512492ccc59653ffc6134cfb0fbfa38783d1e83db6432ca840fd5d1b2d94.jpg)

![](images/8c01f8c4a0ac8b283c32f16ca9217c6b42e530ee39c7fa76edd633e3e1f71122.jpg)

# Example solution

![](images/06324c87cff28ef9872a42e2d8b221b42393fd8fd556af43859e2fda09b1e634.jpg)

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

![](images/f227871565647d3615bba7856b19cdbb53957c3665eef0f95064d1e097573171.jpg)  
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

![](images/7beb4543cecdf1966ec51ffb47d6cad0471d49726f1fafbcc4934ac2306e5877.jpg)

![](images/d66bbee1d7761262d07f547af3da0f4753219bc3826b3d969596f9823644f611.jpg)

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

![](images/10f4a6f7237aa5fb16af938e3e11f132fbb725966023e096d0d3bb94a06e32b4.jpg)

# Hierarchy of diagrams

![](images/2e3b36c81782c3ea2061f64d2c286afa3663c963ed7ab2ed410c6fc966151012.jpg)

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

![](images/1c5fcb1063b5c88a16ac4592d157094634ad90c8f511753063e09a06815d8d34.jpg)

# Parallel operations

![](images/571bc6eaf0e69d51aaa397a1a500d1740c1c39a3c6726699a979a88d1f5fac71.jpg)

# Difference between input and control

![](images/6f6af58ed4d88b0b79ad1b0347d9f0af698c7895f7af695ae42117fbdd5db959.jpg)

Physical flow: input

Logical flow: control

![](images/562208eb0a26b1115c56b4aaf8957b06d9df00a6358ae97c2b11e38ec49b88fb.jpg)

# Example: production management

![](images/2ee4f59fb6727b5d0084757b119be92a40484b3f2b710b8848939e649a57ef92.jpg)

# Observation

In IDEFO there are no decisions,only flows

![](images/c7946b8505f17dc7f3460784781af6528010c4ae5d8dc54a19f06721260c4d01.jpg)

![](images/90cc9d0122f725bc472126946bc9cad5666fe0145ccef2deddb9d5dbf3423cf2.jpg)

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

![](images/76c56d64ddd844bba315d29ab00f4008acfc2f9f317161a174eaaa7138375fdc.jpg)

PURPOSE: Hospital breakfast distribution process

VIEWPOlNT: Responsible for managing hospital meals

# Solution (AO)

![](images/2fdb109c91a91b7f340a838e77f4e577042bf3d92544840175666ac3518da5bb.jpg)

# Solution (A1)

![](images/b1a6d4988073ae834336f019a0afdabc2294a1f214e5226b8db7785b60df7109.jpg)

# Exercise: Car repair shop

V The customer requests an offer for the production of a specific mechanical component. The formulation of the offer involves two company functions: the technical sector and the administrative sector. The technical sector provides a general description of the manufacturing process,from which the administrative sector defines the costs and define the amount of the offer. The customer evaluates the ofer received and if he considers it valid, sends an explicit order to activates the production.   
From this moment the company is formally engaged in the fulfillment of the order and starts the appropriate administrative and technical procedures. In particular, the technical sector define the process plan with the list of operations that must be performed to transform the raw material into a finished product. On the basis of the process plan,the administration arranges to order the raw materials. Production planning is also carried out from the information contained in the process plan, giving rise to the production plan.   
> Once the raw materials have been received and the production plan is ready, processing is carried out. At the end of the processing, a quality control of the product is carried out with which the compliance with the project specifications is established. The process ends with the invoice emission and the payment of the customer.

# Solution (A-0)

![](images/19378087cec127ebf20eb3225bd7fde4b2de87ca66c57771ab1f4ccf122aade6.jpg)

# Solution (AO)

![](images/7f5e2017024883046b3bf2be34e0e8d3544ce9a9928cfacac0029da4073281a5.jpg)

# Solution (A1)

![](images/9659498f8dcf18c2b310591b12a71be99809a812d58f8d25d32c55aea5907a8d.jpg)

# Solution (A2)

![](images/71ccf4498b7590c40c58b049f1fb3dbbe1767269e6ad13f4ac9117013b271e69.jpg)  
【Node :A2  
Title: 1   
Production   
N.: 4
