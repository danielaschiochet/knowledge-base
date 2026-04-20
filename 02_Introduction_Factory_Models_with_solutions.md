# Analysis and Management of Production System

# Lesson 2: Introduction to Factory Models

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Factory model

V Analytical approach for the modeling and analysis of manufacturing and production systems

>Firstly, extremely simple models (single machine models)are developed to show the necessary mechanics and concepts needed   
>Then, more complex models are developed by connecting simple models into networks of workstations with the appropriate interconnections

Overall approach

1． decompose a system into small components   
2． model components   
3． reintegrate the general system by appropriate combination of submodels

# Factory model

Decomposition approach is an approximation   
> Produces acceptable results in a wide variety of manufacturing applications   
> Any analytical model (exact or approximate) is an approximation of the real world environment   
Question to be answered: whether or not the model yields accurate enough results to be used as an analysis tool in support of design and operational decision making

# Factory model

> Modelled system doesn't take into account where or why jobs arrive or how they are transported to customers   
>modeling the order creation or completed job delivery systems is not within the scope of our analysis   
> Arriving job is a physical entity to be processed through the various processing steps or an order to begin the processing of raw material into a newly manufactured entity

![](images/2971f1b3aa5db439ac8f94cfceb2e03feb9138518cd5fa1bb4b56e0d6d113bd0.jpg)

# Notations and definitions

> Factory composed by several machines grouped together by type (called workstations) and series of jobs to be produced on the machines   
> Processing steps for a job consists of several processing operations to be performed by different machines in a specified sequence   
Jobs move through the factory, waiting in line at a workstation until their turn for being processed by the machine,then proceeding to the next workstation to repeat this sequence until all required operations have been completed   
V Jobs arrive at the factory either individually or in batches based on some distribution of the time between arrivals

# Workstation

> Collection of one or more identical machines or resources (i.e. machines which perform the same function)

![](images/2baad854133f5564b1c305bcfdd84d29481a24afdab6d5247e1fa5bdbf6d1f9c.jpg)

# Routing

Sequence of processing steps for a job   
> Jobs with identical routings are said to be of the same job type

different job types are jobs with different routings

![](images/283272d24052ad399b4b1c600a8b394c3529f88fda3258178bc43ee5dee56f7b.jpg)  
Routing

# Performance measures

Cycle time: time a job spends in a system

> Average cycle time of the line is denoted as CT   
> Sometimes called Lead Time, even if LT identifies the a priori evaluation of the cycle time (time allocated to a operation sequence to produce a certain job)

Work in process: number of jobs within a system (from the beginning to the end of the operations sequence) which are either undergoing processing or waiting in a queue for processing   
>Average work-in-process is denoted as WIP

V Throughput rate: number of completed jobs leaving the system per unit of time

>Throughput rate averaged over many jobs is denoted by TH

# Cycle time

Notational distinction

>average factory cycle time denoted as CTs   
>average cycle time at workstation i, denoted as CT(i)

> CTs: average time that a job spends within the factory, either being processed at a workstation or waiting in a workstation queue;   
CT(i): average time jobs spend being processed by workstation i plus the average time spend in the workstation i queue (or buffer)   
CT: used for general properties related to the average cycle time will be developed

# Cycle time

> Processing time often known or can be determined without much effort   
Queue time not easily estimated for a given job

>it depends on the number and processng times of the various types of jobs that are waiting in the queue ahead of the designated job   
V Average cycle time at workstation i given as the sum of two components:

$$
\mathsf {C T} (\mathsf {i}) = \mathsf {C T} _ {\mathsf {q}} (\mathsf {i}) + \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {i}) ]
$$

where Ts(i) denotes the service time (or processing time) at workstation i

# Factory analysis

> For most analyzed systems, long-run throughput rate is equal to the input rate of jobs   
> Main issue: estimation of the total length of time for the manufacturing process (CTs)   
The higher the factory capacity, the faster jobs are completed

>Cycle time increases as the factory becomes busier

# Factory analysis

Time dependent measures such as CTs(t) and WIPs(t) are very difficult to develop

>Focus restricted to the “steady-state" measures i.e., the limiting value of the time dependent measures   
>By a property called the ergodic property, steady-state values can also be considered to be time-averaged values as time becomes very large

> Steady-state measures are independent of the initial conditions of the system   
> In the queueing theory, results are for steady-state system measures

# Factory analysis

> System's performance measures CT and WIP can be estimated from the arrival and departure streams of the system   
Define Tai as the arrival time of the in job,and the function A(t) for t ≥ O as the total number of arrivals during the timeinterval [0, f]   
> Define Tai as the departure time of the injob,and the function D(t) for t ≥Oas the total number of departures during the interval [0, f]

![](images/cae86e2d3f0f2da4151d585ce0454d24f8269fc4c9011ce97e7644525d8efbdc.jpg)

# Factory analysis

> Consider a time interval (a,b) such that the system starts empty and returns to empty   
> Let Nab be the number of jobs that arrive to the system during the interval (a, b)   
> Number these jobs from 1 to N,with index i representing specific jobs.   
Then the average waiting time, CT(a,b), for jobs during this interval is given by

$$
C T (a, b) = \frac {1}{N _ {a b}} \sum_ {i = 1} ^ {N _ {a b}} (T _ {i} ^ {d} - T _ {i} ^ {a})
$$

# Factory analysis

The area, AB, between the curves A(t) and D(t) for a < t < b is merely the summation given in the above equation. This area can also be obtained by standard integration methods as

$$
A B = \int_ {a} ^ {b} (A (t) - D (t)) d t
$$

The area represents the integral of the number of jobs in the system at time t, since N(t) = A(t)-D(t) is the number of jobs in the system at t. So the time-averaged number of jobs waiting in the system during the time interval (a, b) is given by

$$
W I P (a, b) = \frac {1}{b - a} \int_ {a} ^ {b} (A (t) - D (t)) d t
$$

# Factory analysis

There is a relationship between the average number in the system during the interval (a, b) and the average waiting time or cycle time in the system during this interval. Since the area between A(·)and D( -) (namely AB) is constant regardless of the method used to measure it, we have

$$
C T (a, b) = \frac {1}{N _ {a b}} A B \quad W I P (a, b) = \frac {1}{b - a} A B
$$

Thus,the following relationship is obtained

$$
W I P (a, b) = \frac {N}{b - a} C T (a, b)
$$

# Factory analysis

V The mean number of jobs arriving to the system per unit time, normally denoted as λ, is Nab/(b-a), thus

$$
W I P (a, b) = \lambda C T (a, b)
$$

>This result is valid for any interval that starts with an empty system and ends with an empty system   
> In fact this relationship is the limiting behavior result,or long run average result, for stationary queueing systems,and is known as Little's Law   
> The result holds for individual workstations as wellas the system as a whole

# Factory analysis

> For a system that satisfies steady-state conditions, the following equation holds

$$
\mathrm {W I P} = \lambda \times \mathrm {C T}
$$

where WIP is the long-run average number of jobs in the system, CT is the long-run average cycle time and λ is the long-run input rate of jobs to the server

> Since the average input rate is usually equal to the average throughput rate, Litle's Law can also be written as

$$
W I P = t h \times C T
$$

# Factory analysis

> The formula estimates mean values, but the actual underlying random variables of the systems can be quite variable   
> In most single workstation system models, the average number in the system,WIP, can be easily obtained. However, the behavior of the random variable representing the number in the system at any one point in time can be highly variable

![](images/7e0392c0b1fc29ea66b1a75b6a411923877421c42cb5bfe7454d39b21b79e4db.jpg)

# Factory analysis

Term steady-state implies that the mean reaches a limiting value and thus ceases to change with respect to time

>lt does not imply that the system itself ceases to change

Variability continues forever

>fluctuations within the system never cease

> Steady-state does imply that the entire distribution reaches a limiting value

>not only the mean but also the standard deviation, skewness,and other such measures will have limiting values

# Exercise 1

A workstation with a single machine for processing has a long-run average inventory level (WiP) of 25 jobs. The average rate at which jobs enter the workstation is 4 per hour, and the average processing time is 14.5 minutes per job. What is the average time that a job spends in the queue?

# Exercise 1 Solution

# DATA

WIP = 25 pcs   
rate =>= 4 pcs/hr   
E[Ts]= 14.5 min = 14.5 14.5= 0.24 hrs   
CTq =？

![](images/0c73b0df2393b079c9b2abb1fb202fa115ea751ec008e6046ecf62a602a07152.jpg)

# Exercise 1 Solution

According to the Little's Law: WIP = TH × CT

Supposing to have no losses or reworks,we can say that TH = λ and the equations becomes:

$$
W I P = \lambda \times C T
$$

Thanks to this,we can find out the Cycle Time of the station:

$$
C T = \frac {W I P}{\lambda} = \frac {2 5}{4} = 6. 2 5 h r s
$$

We also know that CT = CTa +E[TS]

So,

$$
C T _ {q} = C T - E [ T _ {S} ] = 6. 2 5 - 0. 2 4 = 6. 0 1 h r s
$$

![](images/da39955c67c44a9c78ccb7ff4f430907c43f5a5f83ab4ebc2f2c6f85eafaaa4d.jpg)

# Exercise 2

Consider a factory operating 24 hours per day consisting of two workstations. Arrivals to the first station occur at a rate of 10 per day. The long-run average time that a job spends at the first workstation is 4.2 hours. After processing at the first workstation,a job is sent directly to the second workstation where it spends an average of 5.3 hours. After processing at the second workstation, the job leaves the system.What is the average work-in-process within the factory?

# Exercise 2 Solution

Shift = 24 hrs/day   
rate(𝜆) = 10 pcs/day = 24 pcs/hr = 0.417 pcs/hr   
CT1 = 4.2 hrs   
CT2 = 5.3 hrs

![](images/d9a790cad50840919fe78b68c2e73e922e1730230f961e78d0597fc2d0c19899.jpg)

# Exercise 2 Solution

Computation of WIP level related to WS1 and WS2 with the Litle's Law:

> WIP1 = λ × CT = 0.417 × 4.2 = 1.75 pcs   
? WIP2 = λ × CT2 = 0.417 × 5.3 = 2.21 pcs

Total WIP given by the sum of the two WIP related to the single stations:

WIPtot = WIP1 +WIP2 = 1.75 + 2.21= 3.96 pcS

# Penny Fab model

Factory that makes only one type of product   
Four processing steps to be performed in sequence   
Each processing operation performed on a separate machine   
V Machines process only one unit of the product at a time (a job)   
Constant processing times: 1, 2, 1 and 1 hour(s) respectively   
Constant WIPs

>when a job has completed its four processing steps, it is immediately removed from thefactory and a new job is started at Machine 1 to keep the total factory WIPs at the specified level

![](images/3400c2b2855652fffd982b5f09896944915085c48cfb99904b1882be9a5cdc25.jpg)

# Penny Fab model

![](images/b245ca59c34eba7aaffeae1fef0e84a1156a8e3e71c7e7b41cb5edfca038d8b7.jpg)

Constant WIPs level fixed at 10 jobs decided by the Management   
> Result a th= O.5 job/h (one finished job every two hours on the average is produced)   
V Equal to the maximum throughput rate for this factory because its slowest processing step (at Machine 2) takes two hours per job   
> Jobs can be completed no faster than this single machine completes its own processing

# Penny Fab model

![](images/f9c00f558c025117cc6967a662e345ee16a2a078012c5248eb29a6d181142586.jpg)

Y Management pleased with the throughput of the factory since it is at its maximum capacity, but concerned with the cycle time (20 hours per job)   
Very high since it only takes 5 hours of processing to complete each job   
V The x-factor for a factory is the ratio of CTs to the average total processing time per job   
X-factor = 4   
From literature analysis the x-factor for this sector is 2.6   
Y Management is worried about the ability to keep customers when the industry on average produces the same product with a considerably shorter lead-time from order placement to receipt

# Penny Fab model

![](images/bbeb736bce1eb22d5806987556db195438b4d672c838346a34f89e55a48a9e63.jpg)

Y Possible solution to address the cycle time problem: purchase a 25% faster machine (1.5 hours) for processing step two   
> This purchase would be made expressly for the purpose of reducing the x-factor for the factory to be more in line with the industry average   
The company selling the machine says that this investment will bring the x-factor down to 3.33 and the additional throughput of 0.166 units per hour would pay for the cost of the new machine in three years

# Penny Fab model

![](images/3469c3abc0824041182ee439b3284bca93b6624e4d4c3bef3e78dc65a4c4353a.jpg)

V Management decided that investment is not worthwhile just based on increased throughput   
V Funds needed to buy the machine are needed for other aspects of the company (e.g., research and development)   
> Hiring of a consulting team from the manufacturing engineering department of a local university to perform a short term factory flow analysis study   
First activity to devise a method of predicting the long-term factory performance measures of cycle time and throughput

# Penny Fab model

![](images/536a4385c5aaad48dcab866174d3142b1b0aba2158b790bfa7677aedf8f94f0f.jpg)

Hand simulation procedure of the factory flow   
V Beginning: 10 jobs al placed at Machine 1, then hourly updates to each job's status   
V Jobs soon distributed themselves throughout the factory and after a short period of time a two-hour cyclic pattern emerged   
V Every cycle of this pattern produced one completed job and the factory returned to the identical state for each machine and associated queue

>This set of conditions is referred to as the factory status

All the job cycle times had identical values after the system reached the cyclic behavior pattern (20 h,agreed with the company)

# Penny Fab model

![](images/504d53e7f06bc92e9b05c96ee3a1a3cc340b7375d99e39d0066d475b9052bf25.jpg)

Factory simulation with WIP = 10 for one 24-hour day   
Status (X,Y)

> X: number of jobs at the WS (queue + processing)   
Y: number of hours already completed for the job in processing

After hour 15 the factory status repeats every two hours (factory status at the start of hours 15, 17, 19, 21, etc. are identical)

![](images/8c176d4b779f78337236e85ec3eb32b4f613b5e3e53bfcd7ba5b27d92a7d02d2.jpg)

# Penny Fab model

![](images/ea0b7502941ae9c8051286bb89857a35f53fd52b6776c97413618514a3fb525a.jpg)

V The consulting team decided to estimate the x-factor for various numbers of jobs in the system (WIP)   
From Little's Law: CT=WIP/th   
> In this case, th=0.5 j/h, then CT=2*WIP   
Processing time = 5h, then x=CT/5=WIP/2.5   
> In order to have the desired x-factor (2.6), the WIP must be 6.5   
How the th change by varying WIP?

# Penny Fab manual simulation

![](images/6e7c1e5efa166ba964edee29bfe8b348b467a707de92df4ff9a1ea42159535c3.jpg)

![](images/ce2b889dcaafd3d09190363aec0a7f6f518928c1af9fe497f5f42276404faee7.jpg)

![](images/006cfcc0acd2abe82839de3cc74828bee9e34e06ee6037c7d5d50c4abb1dc57b.jpg)

![](images/cfb5b34c3d1722d46d0b4970c50d77ae4b31db8d8b4fa2a7b691647b1a60761a.jpg)

![](images/a727a2d116f2b76d5395b30ab692dd940a86757c58699fa3005d34173f51c64f.jpg)

![](images/9357ea849ca2fd0ce3a80abaf6f132551a1f22f8b4e778858f0b9680232611e8.jpg)

![](images/52bbd9468428a3bde1901f40c1f9cb4ca6e88167830e0ef6e846b534cf984592.jpg)

1 item every 5 hours comes out of the line (TH = 1/5 pcs/h)

Each item stays on the line for 5 hours (CT = 5 h)

# Penny Fab manual simulation

![](images/271385109998d2c877bf56725e165004155898a29f1a8beb00301b39fd327566.jpg)

![](images/f5d2892569279d6110e9a443a128adc97cfae8d67be405d3cc649857d41d96e7.jpg)

![](images/3b15b4a4ca7f90114d5c0a54848c9aaaf9ef3853e71dbc32bb395734e8ccf095.jpg)

![](images/82b7f3d568f566697a1261ed9e52ea8afca9f108572bef91d32c95e3418aa417.jpg)

![](images/9f47bc38e1c65105e160000f6c1b4d2add036aaa57f62c6cd1ebd7be55a396ac.jpg)

![](images/9e7dfa091187aedeb87d78c9955684bacf657657e9955f18e1d0396e560f0990.jpg)

![](images/baca75cee38358beb142c67c903a6f437f9a2352f36d8f780f5902832d115e95.jpg)

2 item every 5 hours comes out of the line (TH = 2/5 pcs/h)

Each item stays on the line for 5 hours (CT = 5 h)

# Penny Fab manual simulation

![](images/1464709ab514d4f9f64b5140d92ac48cc3063e3f818fad7283eaf6e8fab7d2d0.jpg)

![](images/ae9be1bdfa52e6fd42d76a93c1bb587f3fb4e3f8403b2b34f0291cb09027bf8b.jpg)

![](images/8fb3d5a6c3913e42ebacb5dc8fd97943984b7c5956766db17165f0858f760980.jpg)

![](images/76be7e06314bb7e32e4dae1ebcea1766e3adb64b0beacd29d642759f7b5701dc.jpg)

![](images/e48a5d9b15eb196d722b8082702868a8425eb95f91de294d3fa48cb4001a2884.jpg)

![](images/a27d090cbdeb4533da85137479ac093513ca5ea2878b37546f39e6a1fcac3e48.jpg)

![](images/9a6198a1b37093e01bc3286059fd45bf7abcef6d3cc659d0916c1db419359e96.jpg)

![](images/f2476e073fa8075cbc3886f73236961b2f39f386085debe83e2fbd2818ec96ea.jpg)

3 item every 6 hours comes out of the line (TH = 3/6 pcs/h)

Each item stays on the line for 6 hours (CT = 6 h)

# Penny Fab manual simulation

![](images/75bb9da7ab58e370820ebbdecb0b4487bd005bed2efe4217ca2ab786bb8e57b9.jpg)

![](images/a316a3bc4e3057161c7d82a1b8ae51bb14dce6b8a2fa844faf832043bfaf2e61.jpg)

![](images/492e003a0c63ff9a895fc56358ff108734bae442f0b128595a8c8b96ea524da2.jpg)

# Penny Fab manual simulation

![](images/cfb426a16acc52f6fd940c9015f1c610dc025d17fde4d950532fb30972f1ab7b.jpg)

![](images/7e6d980e4669e982e307a6e70aab96f965a0baf5c445b7bbffacf05179b51a61.jpg)

> The WiP level in the factory can be reduced to 3 jobs while maintaining the factory throughput rate of /2   
The cycle time reduces to 2xWiP= 6 hours with an x-factor of 1.2   
V Thus at no expense, the factory can maintain its current throughput rate and reduce its cycle time from 20 to 6 hours

# Conclusion

$$
C T _ {\text {b e s t}} (w) = \left\{ \begin{array}{l l} T _ {0}, & \text {i f} w \leq W _ {0} \\ w / r _ {b}, & \text {o t h e r w i s e .} \end{array} \right.
$$

$$
\mathrm {T H} _ {\text {b e s t}} (w) = \left\{ \begin{array}{l l} w / T _ {0}, & \text {i f} w \leq W _ {0} \\ r _ {b}, & \text {o t h e r w i s e .} \end{array} \right.
$$

> CT remains constant at the minimum CT (To) as WIP increases and it increases to infinity once the maximum WIP (rb) is reached   
TH increases as WIP level increases, until the WIP level reaches the maximum WIP (rb); after that TH stabilizes,remaining constant   
The best case (min CT and max TH) is when with WIP = 3

# Line critical parameters

1. Bottleneck Rate (rb): TH of the workstation which is the bottleneck of a line (maximum TH obtained from the line)   
2. Raw process time (To): sum of the long-term average process times of each station in the line (minimum possible CT)   
3. Critical WIP (Wo= rb To): WIP level which allows a line to achieve the maximum TH (rb) with the minimum cycle time (To)

# Example: balanced production line

> Line composed of 4 machines in series   
? Each machine has a 2 hours per piece process time   
Capacity of each machine (inverse of process time) = 1 pcs/2h   
> Once an operation on a machine is completed, the product goes immediately to the next machine   
Machines work continuously, with no stops   
No discarded pieces

![](images/97ef2783e84b25d189e136aa3611626c24c933323868740211409b2edd79ff08.jpg)

# Example: balanced production line

# Critical parameters:

rb = 1 pcs/2h = 0.5 pcs/g   
(max utilization 三 min capacity)  
To= 2h*4 = 8h   
(sum of process times on machines)   
W = rb*To= 0.5*8 = 4 pcs

Wo is the critical value of WIP, which allows to reach rb = 0.5 pcs/h and To= 8 h

# Example: not balanced production line

1 Line composed of workstations in series   
Each WS is composed of a different number of machines   
> Each WS is composed of identical machines (with the same process time) in parallel   
WS capacity = single machine capacity * number of machines

![](images/5f9765f298093f6c735e4954af4ca612dad4758ae65e62872a0bd85bdc67e225.jpg)

# Example: not balanced production line

Line composed of work stations in series   
Each WS is composed of a different number of machines   
V Each WS is composed of identical machines (with the same process time) in parallel   
> WS capacity = single machine capacity * number of machines

![](images/e00c1fa776e16d0b37ede6b95fdae99ee7abb0f69157359e83249e22da25fc0e.jpg)

# Example: not balanced production line

# Critical parameters:

> rb = 0.4 pcs/h (WS2 capacity: not WS3 with slower machines and not WS1 with smaller number of machines)   
To = 20 h (sum of process times)   
> Wo= 0.4*20 = 8 pcs (it is smaller than the number of machines, because some station won’t be completely used)

# HAL - Large Panel Line Processes

# Data:

Average process rate (number of panels/h)   
Average process time (h) at each station

![](images/eeaad8cb8d792ef449a7dca89ab623b07045332e09149c0512c02742c2b88102.jpg)

![](images/f1e1d1b941f382dedcc6c33ae6284eecd7959c326db4631c702bf0847d65700b.jpg)

![](images/b7b6248649ee98fc1a1b3483d975977c179374edf0193a10991d0c8fa15b1142.jpg)

Batches and parallel machines are present, so rate is different from 1/time

# HAL - Large Panel Line Processes

Large Panel Line: produces printed circuit boards   
Line runs 24 hr/day (only 19.5 hrs of productive time)   
Recent Performance (last 7 months):

>TH = 1,400 panels per day (71.8 panels/hr)   
WIP = 47,600 panels   
>CT = 34 days (663 hr at 19.5 hr/day)   
>Customer service= 75% on-time delivery

How HAL is performing?

Which data we need to evaluate?

![](images/4b7801fc45d2ba20c5e9183e023ae21acdb83d4e412ffca64629a89893a09c57.jpg)

# HAL - Large Panel Line Processes

Critical WIP: rbT。= 144 x 33.9 = 3,869   
Actual Values:

>CT= 34 days = 663 hours (at 19.5 hr/day)   
>WIP = 47,600 panels   
>TH = 71.8 panels/hour

Conclusions:

>TH is 63% of capacity   
>WIP is 12.3 times critical WIP   
>CT is 24.1 times raw process time

The factory is not performing well!

# Exercise 1

Consider a production line composed of four workstations,each consisting of a single machine,except the second station which consists of two identical machines in parallel

Each machine has mean process time equal to two hours per job

a) Determine the botleneck rate rb, the raw process time T。and the critical WIP of the line   
b) Compute CT and TH for values of WIP going from 1 to 10

# Solution

![](images/606874615b7b8ecf8764f21656e80aee7c883ce86e5ef2acb758f4789db8eefa.jpg)

Data   
![](images/76d701d31155f2f48c949cbab76da91f68ca5cc1406f897c5df0d9938aef9eea.jpg)

Parameters   
![](images/ccddbe2d4fde1b1961770ffd1149852cc6ef05f81e3cd3d5b14fec1ab51fe6e0.jpg)

![](images/f0222b39e2b1dd5716f21d94e79a63edcec5c5a66858fa5c440c50b167a04ee2.jpg)

# Exercise 2

Consider a production line composed by three workstations in series.The characteristics of the workstations are reported in the table.

Compute the botleneck rate rb, the raw process time T。 and the critical WIP W。 of the system.

What happen to the TH and CT values when the WIP exceeds Wo?

![](images/44082cfb07a2495e0aa41a9b9476a211af6584a1ea4c69e1c18c640ee26cab77.jpg)

# Solution

![](images/d2c639df5eeed9e59ab49ca3396e08c2691aae0588a1dd1e7465ed67e369770c.jpg)

TO

9 min

rb LAAA

0.5 j/min

WO

4.5j

# Solution

$$
\mathrm {C T} = \left\{ \begin{array}{l l} T _ {0}, & \text {i f} w \leq W _ {0} \\ w / r _ {b}, & \text {o t h e r w i s e .} \end{array} \right. \quad \mathrm {T H} = \left\{ \begin{array}{l l} w / T _ {0}, & \text {i f} w \leq W _ {0} \\ r _ {b}, & \text {o t h e r w i s e .} \end{array} \right.
$$

If the WIP exceeds WO, the TH remains constant at value of 0.5 j/min and the CT increases at a rate of WIP/0.5
