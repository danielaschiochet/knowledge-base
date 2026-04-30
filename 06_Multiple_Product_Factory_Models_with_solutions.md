# Analysis and Management of Production System

# Lesson 6: Multiple Product Factory Models

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Introduction

Most manufacturing facilities are setup to produce more than a single product   
> Even in the case of single product facilities,if the product visits a workstation more than once with different processing times at each visit, then the workstation sees the equivalent of multiple products   
Such revisiting production schemes are called re-entrant flow systems   
Modeling multiple product facilities is not significantly more difficult than modeling single product systems

# Flow conservation

Job flow needs to be maintained by product type   
> The number of visits to each workstation by product class is needed   
Different products can have different probabilistic flows through the production facility as well as diferent processing time characteristics   
> The number of visits to each workstation by product needs to be developed   
This analysis requires the solution of a network flow system of equations by product   
The processing time is assumed to follow the same distribution for each product on each visit to a given workstation

# Product flow rates

To compute the workload on the workstation, the number of visits to the workstation by each product is computed first   
It is necessary to distinguish between products visiting the same workstation

> $λ_{i,k}$ = arrival rate of product type i to workstation k   
> $λ^i$= vector giving the total arrival rates of product type iinto each station   
> $\gamma_{i,k}$= external arrival rate of product i into workstation k   
> $p_{j,k}^i$ = probabilitythat an individualitem of product ileaving workstation j goes to workstation k  
> $P^i$= matrix of these probabilites for product i

# Product flow rates

Consider a factory of n workstations where product type ifollows the switching rule defined by routing matrix Pi and assume that the sum of at least one row of Pi is stictly less than one (i.e., jobs exit the network from at least one workstation)   
> Let $\gamma^i=(\gamma_{i,1},..., \gamma_{i,n})$ denote a vector consisting of the mean arval rate of type i jobs from an external source to the workstation   
> Let $λ^i=(λ_{i,1},...,λ_{i,n})$ be te (unknown) vector denoting mean arrval rate of all type i jobs to the workstations   
> The vector $𝜆^i$ is given by: $λ^i=(I-(P^i)^T)^{-1}γ^i$ where I is an n × n identity matrix and $(P^i)^T$ is the transpose of $P^i$

# Product flow rates

The total arrival rate of jobs to workstation k is given by the sum of the different product types:

$$
\lambda_ {k} = \sum_ {i = 1} ^ {m} \lambda_ {i, k}
$$

where m is the total number of product types within the factory

# Example

Consider a four-workstation facility that processes two products with each product arriving to the first workstation according to individual Poisson arrival streams, each at a rate of 5 per hour   
Product 1 uses only the first three workstations with the routing structure displayed in the firstfigure   
Product 2 uses all four workstations with the routing structure displayed in the second figure

### Figure 1 - Diagram Description: Three-Node Network with Multiple Feedback Loops

**1. External Input:**
*   External arrivals enter the system at **Node 1** with a rate of **5**.

**2. Routing from Node 1 (Splitting):**
*   To Node 2: **3/4**
*   To Node 3: **1/4**

**3. Routing from Node 2:**
*   Forward to Node 3: **9/10**
*   Feedback to Node 1: **1/10**

**4. Routing from Node 3:**
*   Feedback to Node 1: **1/20**
*   System Departure: **19/20** (implicit, calculated as 1 - 1/20)

### Figure 2 - Diagram Description: Four-Node Network with Multiple Feedback Loops

**1. External Input:**
*   External arrivals enter the system at **Node 1** with a rate of **5**.

**2. Routing from Node 1 (Splitting):**
*   To Node 2: **2/3**
*   To Node 3: **1/3**

**3. Routing from Node 2 and Node 3 (Merging):**
*   All processed units from **Node 2** flow into **Node 4** (implicit probability of 1).
*   All processed units from **Node 3** flow into **Node 4** (implicit probability of 1).

**4. Routing from Node 4 (Feedback & Departure):**
*   Feedback to Node 2: **2/10**
*   Feedback to Node 3: **3/10**
*   Feedback to Node 1: **1/10**
*   System Departure: **4/10** (implicit, calculated as 1 - 2/10 - 3/10 - 1/10)

# Example

Assume that there is one machine at each workstation and that the processing time data for the two products are:

| Workstation $k$ | $E[T_s(1, k)]$ | $C_s^2(1, k)$ | $E[T_s(2, k)]$ | $C_s^2(2, k)$ |
| :---: | :---: | :---: | :---: | :---: |
| 1 | 1/14 hr | 0.8 | 1/15 hr | 1.33 |
| 2 | 1/10 hr | 1.2 | 1/18 hr | 2.00 |
| 3 | 1/15 hr | 1.5 | 1/12 hr | 1.50 |
| 4 | - | - | 0.06 hr | 0.75 |

# Example

V To determine the mean arrval rate to each workstation of Type 1 and Type 2 jobs is simply to repeat the steps of previous examples

$$
\boldsymbol {\lambda} ^ {1} = (5. 6 9 0, 4. 2 6 7, 5. 2 6 3, 0)
$$

$$
\boldsymbol {\lambda} ^ {2} = (6. 2 5, 6. 6 6 7, 5. 8 3 3, 1 2. 5)
$$

The total rate into each workstation is the sum of the individual product inflows

$$
\boldsymbol {\lambda} = (1 1. 9 4 0, 1 0. 9 3 4, 1 1. 0 9 6, 1 2. 5)
$$

# Workstation workload

Once the workstation arrival rates by product type have been determined, the workload for each workstation can be computed   
The workload is the total amount of work required by a workstation per unit of time   
> Sum of arrval rate for each product type multiplied by its associated mean processing time

$$
W L _ {k} = \sum_ {i = 1} ^ {m} \lambda_ {i, k} \mathrm {E} [ T _ {s} (i, k) ]
$$

where m is the total number of product types within the factory

# Workstation workload

Utilization factor given by

$$
u _ {k} = W L _ {k} / c _ {k}
$$

where ck is the number of identical processors avaible at workstation k

# Example

Since there is one machine per workstation, the workload and utilization factors are the same at each workstation so that

$$
u = (0. 8 2 3 1, 0. 7 9 7 1, 0. 8 3 6 9, 0. 7 5)
$$

With utilization factors alless than 1.0, the factory can achieve steadystate and further analysis is possible

# Service time characteristics

For workstation k the service time will be the random variable Ts(i,k), whenever Product i is being processed   
The service time for an arbitrary job is the random variable Ts(k).   
In the long-run, the probability that a given machine at Workstation k will be processing a Type i job is $λ_{i,k}$ / $λ_{k}$  
Ts(k) is a mixture of random variables

$$T _ {s} (k) = \begin{cases} T _ {s} (1, k) & \text{with probability } \frac{\lambda _ {1, k}}{\lambda _ {k}} \\ \vdots & \\ T _ {s} (m, k) & \text{with probability } \frac{\lambda _ {m, k}}{\lambda _ {k}} \end{cases}$$

where m is the number of products within the factory

# Service time characteristics

For the property of the mixture of random variables

Mean for the service time at workstation k:

$$
E [ T _ {s} (k) ] = \sum_ {i = 1} ^ {m} \frac {\lambda_ {i , k}}{\lambda_ {k}} E [ T _ {s} (i, k) ] = W L _ {k} / \lambda_ {K}
$$

Second moment:

$$
E [ T _ {s} (k) ^ {2} ] = \sum_ {i = 1} ^ {m} \frac {\lambda_ {i , k}}{\lambda_ {k}} E [ T _ {s} (i, k) ] ^ {2} (1 + C _ {s} ^ {2} (i, k))
$$

# Service time characteristics

Since E[X²]=E[X]²(1+C²[X]), then

$$
\mathrm {C} ^ {2} [ \mathrm {X} ] = \mathrm {E} [ \mathrm {X} ^ {2} ] / \mathrm {E} [ \mathrm {X} ] ^ {2} - 1
$$

Coefficient of variation for the service time at workstation k:

$$
C _ {s} ^ {2} (k) = \frac {\sum_ {i = 1} ^ {m} \left(\frac {\lambda_ {i , k}}{\lambda_ {k}}\right) E [ T _ {s} (i , k) ] ^ {2} \left(1 + C _ {s} ^ {2} (i , k)\right)}{(\sum_ {i = 1} ^ {m} \left(\frac {\lambda_ {i , k}}{\lambda_ {k}}\right) E [ T _ {s} (i , k) ]) ^ {2}} - 1
$$

# Example

Using the arrival rate and the service time data, the service time for the first workstation is:

$$
E [ T _ {s} (1) ] = \left(\frac {5 . 6 9 0}{1 1 . 9 4}\right) \frac {1}{1 4} + \left(\frac {6 . 2 5 0}{1 1 . 9 4}\right) \frac {1}{1 5} = 0. 0 6 8 9 h r
$$

The squared coeficient of variation is:

$$
C _ {s} ^ {2} (1) = \frac {\left(\frac {5 . 6 9 0}{1 1 . 9 4}\right) \left(\frac {1}{1 4}\right) ^ {2} (1 + 0 . 8) + \left(\frac {6 . 2 5 0}{1 1 . 9 4}\right) \left(\frac {1}{1 5}\right) ^ {2} (1 + 1 . 3 3)}{(0 . 0 6 8 9) ^ {2}} - 1 = 1. 0 6 1 6
$$

# Example

Service time parameters for all the workstations:

| Workstation $k$ | $E[T_s(k)]$ | $C_s^2(k)$ |
| :---: | :---: | :---: |
| 1 | 0.069 | 1.062 |
| 2 | 0.073 | 1.678 |
| 3 | 0.075 | 1.530 |
| 4 | 0.060 | 0.750 |

# Workstation performance measures

The multiple product facility problem is now reduced to a problem similar to the single product analysis since the workstation composite service time data are now known   
Consider a factory of n workstations with m diferent job types   
Assume that the total arrival rate of job type i to workstation k is given by $𝜆_{i,k}$,and the probability that a job of type i leaving workstation j will be routed to workstation k is given by $p^i_{j,k}$   
The composite routing matrix, $P=(p_{jk})$ gives the switching probabilities of an arbitrary job and is determined by:

$$
p _ {j k} = \frac {\sum_ {i = 1} ^ {m} \lambda_ {i j} p _ {j k} ^ {i}}{\lambda_ {j}} \quad \mathrm {f o r j , k = 1 , \ldots , n}
$$

# Example

We now complete the analysis of the factory   
The matrix of probabilities are obtained

> For example, the probability of going from Workstation 2 to Workstation 1 is determined as:

$$
p _ {2 1} = \frac {\lambda_ {1 2} p _ {2 1} ^ {1} + \lambda_ {2 2} p _ {2 1} ^ {2}}{\lambda_ {2}} = \frac {4 . 2 6 7 (0 . 1) + 6 . 6 6 7 (0)}{1 0 . 9 3 4} = 0. 0 3 9
$$

> Continuing with the other workstations

$$
P = \left[ \begin{array}{c c c c} 0 & 0. 7 0 6 & 0. 2 9 4 & 0 \\ 0. 0 3 9 & 0 & 0. 3 5 1 & 0. 6 1 0 \\ 0. 0 2 4 & 0 & 0 & 0. 5 2 6 \\ 0. 1 0 0 & 0. 2 0 0 & 0. 3 0 0 & 0 \end{array} \right]
$$

The analysis required to obtain the mean waiting times in the workstations is the same procedure as for individual product systems once the composite product data and transition probability matrix Phave been developed   
The squared coefficient of variation for the arrival streams into each workstation is again obtained by solving the Ca² system of equations

$$
C _ {a} ^ {2} (1) = 0. 0 0 0 5 1 C _ {a} ^ {2} (2) + 0. 0 0 0 1 6 C _ {a} ^ {2} (3) + 0. 0 0 4 5 8 C _ {a} ^ {2} (4) + 0. 9 9 4 3
$$

$$
C _ {a} ^ {2} (2) = 0. 1 7 5 5 4 C _ {a} ^ {2} (1) + 0. 0 2 0 0 1 C _ {a} ^ {2} (4) + 0. 8 2 0 5
$$

$$
C _ {a} ^ {2} (3) = 0. 0 3 C _ {a} ^ {2} (1) + 0. 0 4 4 2 7 C _ {a} ^ {2} (2) + 0. 0 4 4 3 6 C _ {a} ^ {2} (4) + 0. 9 2 3 5
$$

$$
C _ {a} ^ {2} (4) = 0. 1 1 8 6 8 C _ {a} ^ {2} (2) + 0. 0 7 3 5 8 C _ {a} ^ {2} (3) + 1. 0 3 9 6.
$$

The solution to this system is

$$
\mathbf {c} _ {a} ^ {2} = (1. 0 0 0 7, 1. 0 2 0 9, 1. 0 5 3 7, 1. 2 3 8 3)
$$

# Workstation performance measures

As long as there is no priority being given to specific job types,all jobs experience the same queue; therefore, the mean cycle time within workstation k by job type i is given as:

$$
C T _ {s} (\mathfrak {i}, \mathsf {k}) = C T _ {q} (\mathsf {k}) + \mathsf {E} [ T _ {s} (\mathfrak {i}, \mathsf {k}) ]
$$

# Example

The cycle time by workstation is given as the composite time for all products visiting that workstation

| Workstation $k$ | $CT_q(k)$ | $CT(k)$ | $WIP(k)$ |
| :---: | :---: | :---: | :---: |
| 1 | 0.331 hr | 0.400 hr | 4.772 |
| 2 | 0.387 hr | 0.460 hr | 5.029 |
| 3 | 0.502 hr | 0.577 hr | 6.402 |
| 4 | 0.183 hr | 0.243 hr | 3.036 |

The total facility performance measures are for the total work in the facility and are not distinguishable by product type   
The total system work-in-process is the sum of the workstation WIP's and equals 19.238   
The total inflow and, hence, throughput for the system is 10/hr   
Thus,the average cycle time in te system for allitems by Little's Law is 19.238/10 = 1.9238 hours

# Mean time spent within the factory

Consider a factory of n workstations with m different job types   
Assume that the external arival rate of jobs of type i to workstation k is given by $\gamma_{i,k}$,and the total arival rate of Job Type i to workstation is given by $\lambda_{i,k}   
Furthermore assume that the mean time spent waiting for processing in workstation k by an arbitrary job (namely, CTq(k)) has been determined   
The mean time spent within the factory by a type i job is given by:

$$
C T _ {s} ^ {i} = \frac {\sum_ {k = 1} ^ {n} \lambda_ {i k} \big (C T _ {q} (k) \big) + E [ T _ {s} (i , k) ] \big)}{\sum_ {j = 1} ^ {n} \gamma_ {i j}} \mathrm {f o r i = 1 , \ldots , m}
$$

# Example

System mean cycle times by individual product type   
For this example these computations are

$$
\begin{array}{l} C T ^ {1} = [ 5. 6 9 0 (0. 3 3 0 7 + 0. 0 7 1 4) + 4. 2 6 7 4 (0. 3 8 7 0 + 0. 1) \\ + 5. 2 6 3 2 (0. 5 0 1 5 + 0. 0 6 6 7) ] / 5 = 1. 4 7 1 4 \mathrm {h r} \\ \end{array}
$$

$$
\begin{array}{l} C T ^ {2} = [ 6. 2 5 (0. 3 3 0 7 + 0. 0 6 6 7) + 6. 6 6 6 7 (0. 3 8 7 0 + 0. 0 5 5 6) \\ + 5. 8 3 3 3 (0. 5 0 1 5 + 0. 0 8 3 3) + 1 2. 5 (0. 1 8 2 8 + 0. 0 6) ] / 5 = 2. 3 7 6 3 \mathrm {h r} \\ \end{array}
$$

These two products are produced in equal quantities, so the average cycle time for the factory is the average of these two individual product cycle times or 1.9238 hours

# Example

To demonstrate that this modeling approach is adequate for most decision making situations, these analytical results are compared with simulation results   
All the critical parameters are close enough for the analytical model to be a usable tool for decision purposes

| Workstation | $CT$ | $WIP$ | $E[T_a]$ | $C^2[T_a]$ | $E[T_d]$ | $C^2[T_d]$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| S 1 | 0.398 | 4.744 | 0.084 | 1.001 | 0.084 | 1.050 |
| A 1 | 0.400 | 4.772 | 0.084 | 1.000 | 0.084 | 1.042 |
| S 2 | 0.427 | 4.677 | 0.091 | 1.028 | 0.091 | 1.443 |
| A 2 | 0.460 | 5.029 | 0.091 | 1.021 | 0.091 | 1.440 |
| S 3 | 0.569 | 6.309 | 0.090 | 1.035 | 0.090 | 1.397 |
| A 3 | 0.577 | 6.402 | 0.090 | 1.053 | 0.090 | 1.389 |
| S 4 | 0.248 | 3.107 | 0.080 | 1.330 | 0.080 | 1.044 |
| A 4 | 0.243 | 3.036 | 0.080 | 1.238 | 0.080 | 0.983 |
| **S sys** | 1.888 | 18.84 | — | — | — | — |
| **A sys** | 1.924 | 19.24 | — | — | — | — |

# Exercise 1

A factory is composed by three workstations in series,and produces two types of products   
The first two workstations have the same processing time for both types of product, both exponentially distributed

E[Ts(1,1)]= E[Ts(2,1)]= 0.20 h   
E[Ts(1,2)]= E[Ts(2,2)]= 0.15 h

The third workstation has two diferent processing times E[Ts(1,3)]=0.14 h and E[Ts(2,3)]=0.25 h, both exponentially distributed   
The inter-arrival times of both product types are exponentially distributed: type 1 with average rate of 3,and type 2 with average rate of 1   
Find the system work in process and cycle time

# Solution

### Diagram Description: 3-Node Tandem Network with Two Traffic Classes

**1. System Inputs (Node 1):**
*   **Class 1 (Blue):** Arrival rate $\gamma_1 = 3$.
*   **Class 2 (Grey):** Arrival rate $\gamma_2 = 1$.

**2. Workstation 1: M/M/1**
*   Mean service time: $E[T_s(1)] = 0.20$ hr.
*   Squared coefficient of variation: $C_s^2(1) = 1$.

**3. Workstation 2: M/M/1**
*   Mean service time: $E[T_s(2)] = 0.15$ hr.
*   Squared coefficient of variation: $C_s^2(2) = 1$.

**4. Workstation 3: M/G/1**
*   **Class 1 (Blue):** $E[T_s(1,3)] = 0.14$ hr, $C_s^2(1,3) = 1$.
*   **Class 2 (Grey):** $E[T_s(2,3)] = 0.25$ hr, $C_s^2(2,3) = 1$.

$$ \lambda_{11} = 3 \text{ j/h}, \quad \lambda_{21} = 1 \text{ j/h} $$
$$ \lambda_{12} = 3 \text{ j/h}, \quad \lambda_{22} = 1 \text{ j/h} $$
$$ \lambda_{13} = 3 \text{ j/h}, \quad \lambda_{23} = 1 \text{ j/h} $$

$$ \lambda_1 = 4 \text{ j/h}, \quad \lambda_2 = 4 \text{ j/h}, \quad \lambda_3 = 4 \text{ j/h} $$

$$ WL_1 = u_1 = \lambda_1 E[T_s(1)] = 4 \cdot 0.20 = 0.8 $$

$$ WL_2 = u_2 = \lambda_2 E[T_s(2)] = 4 \cdot 0.15 = 0.6 $$

$$ WL_3 = u_3 = \lambda_{13} E[T_s(1,3)] + \lambda_{23} E[T_s(2,3)] = 3 \cdot 0.14 + 1 \cdot 0.25 = 0.67 $$

$$ E[T_s(3)] = \frac{3}{4} \cdot 0.14 + \frac{1}{4} \cdot 0.25 = 0.1675 \ \text{h} $$

$$ C_s^2(3) = \frac{\left[ \frac{3}{4} \cdot 0.14^2 (1+1) + \frac{1}{4} \cdot 0.25^2 (1+1) \right]}{0.1675^2} - 1 = 1.16 $$

$$ C_a^2(1) = C_a^2(2) = C_a^2(3) = \frac{3}{4} \cdot 1 + \frac{1}{4} \cdot 1 = 1 $$

$$ CT(1) = \frac{u_1}{1-u_1} \cdot E[T_s(1)] + E[T_s(1)] = \frac{0.8}{0.2} \cdot 0.2 + 0.2 = 1 \ \text{h} $$

$$ WIP(1) = TH \cdot CT(1) = 4 \cdot 1 = 4 \ \text{j} $$

$$ CT(2) = \frac{u_2}{1-u_2} \cdot E[T_s(2)] + E[T_s(2)] = \frac{0.6}{0.4} \cdot 0.15 + 0.15 = 0.375 \ \text{h} $$

$$ WIP(2) = TH \cdot CT(2) = 4 \cdot 0.375 = 1.5 \ \text{j} $$

$$ CT(3) = \frac{C_a^2(3) + C_s^2(3)}{2} \cdot \frac{u_3}{1-u_3} \cdot E[T_s(3)] + E[T_s(3)] = \frac{1+1.16}{2} \cdot \frac{0.67}{0.33} \cdot 0.1675 + 0.1675 = 0.535 \ \text{h} $$

$$ WIP(3) = TH \cdot CT(3) = 4 \cdot 0.535 = 2.14 \ \text{j} $$

$$ CT = 1 + 0.375 + 0.535 = 1.91 \ \text{h} $$

$$ WIP = 4 + 1.5 + 2.14 = 7.64 \ \text{j} $$

$$ CT^1 = [3(0,8+0,2) + 3(0,225+0,15) + 3(0,3675+0,14)]/3 = 1.88 \ \text{h} $$

$$ CT^2 = (0,8+0,2) + (0,225+0,15) + (0,3675+0,25) = 1.99 \ \text{h} $$

$$ CT = \frac{3}{4} CT^1 + \frac{1}{4} CT^2 = 1.91 \ \text{h} $$

# Exercise 2

A facility is composed by 3 workstations and produces 2 types of products.   
The first product type is processed by WS1 and WS3. Processing times are exponentially distributed, and the average values are O.3 h and O.1 h, respectively. In the 10% of the cases, the product need to be reworked by WS3.   
The second product type is processed by WS2 and WS3. Processing times are exponentially distributed, and the average values are 0.4 h and 0.2 h, respectively.   
The inter-arrival times of product types are exponentially distributed: type 1 with average rate of 2 j/h, and type 2 with average rate of 1 j/h.   
Find the system performance measures.

# Network topology

### Diagram Description: Queueing Network with Multiple Traffic Types and Feedback

**1. External Arrivals:**
*   **Type 1 (Blue):** External arrival rate $\gamma_1 = 2$ j/h.
*   **Type 2 (Grey):** External arrival rate $\gamma_2 = 1$ j/h.

**2. Node 1 (Upper Left - Type 1 only):**
*   Mean service time: $E[T_s] = 0.3$ h.
*   Squared coefficient of variation: $c_s^2 = 1$.

**3. Node 2 (Lower Left - Type 2 only):**
*   Mean service time: $E[T_s] = 0.4$ h.
*   Squared coefficient of variation: $c_s^2 = 1$.

**4. Node 3 (Right - Merging and Feedback):**
*   This node receives processed flow from both Node 1 and Node 2.
*   **Differentiated Service:**
    *   For Type 1: $E[T_s(1,3)] = 0.1$ h, $c_s^2(1,3) = 1$.
    *   For Type 2: $E[T_s(2,3)] = 0.2$ h, $c_s^2(2,3) = 1$.
*   **Feedback Loop:** A fraction of **0.1** of Type 1 flow is fed back into Node 3 after processing.
*   **System Departure:** Both flows eventually exit the system after Node 3.

# WS1 analysis

$$
u = \lambda \cdot E [ T s ] = 2 \cdot 0. 3 = 0. 6
$$

$$
\begin{array}{l} C T = \left(\frac {c _ {a} ^ {2} + c _ {s} ^ {2}}{2}\right) \left(\frac {u}{1 - u}\right) \cdot E [ T s ] + E [ T s ] = \left(\frac {1 + 1}{2}\right) \left(\frac {0 . 6}{1 - 0 . 6}\right) \cdot 0. 3 + 0. 3 \\ = 0. 7 5 h \\ \end{array}
$$

$$
W I P = C T \cdot \lambda = 0. 7 5 \cdot 2 = 1. 5 j o b s
$$

$$
c _ {d} ^ {2} = 1
$$

# WS2 analysis

$$
u = \lambda \cdot E [ T s ] = 1 \cdot 0. 4 = 0. 4
$$

$$
\begin{array}{l} C T = \left(\frac {c _ {a} ^ {2} + c _ {s} ^ {2}}{2}\right) \left(\frac {u}{1 - u}\right) \cdot E [ T s ] + E [ T s ] = \left(\frac {1 + 1}{2}\right) \left(\frac {0 . 4}{1 - 0 . 4}\right) \cdot 0. 4 + 0. 4 \\ = 0. 6 7 h \\ \end{array}
$$

$$
W I P = C T \cdot \lambda = 0. 6 7 \cdot 1 = 0. 6 7 j o b s
$$

$$
c _ {d} ^ {2} = 1
$$


# WS3 analysis

$$
\lambda_ {3} = \lambda_ {1} + \lambda_ {2} + 0. 1 \lambda_ {1} = 3. 2 \frac {j o b s}{h}
$$

P=

| | Node 1 | Node 2 | Node 3 |
| :--- | :---: | :---: | :---: |
| **Node 1** | 0 | 0 | 1 |
| **Node 2** | 0 | 0 | 1 |
| **Node 3** | 0 | 0 | 0.2/3.2 = 0.0625 |

$$
W L = \lambda_ {1} E [ T s 1 ] + \lambda_ {2} E [ T s 2 ] + 0. 1 \lambda_ {1} E [ T s 1 ] = 2 \cdot 0. 1 + 1 \cdot 0. 2 + 0. 2 \cdot 0. 1 = 0. 4 2
$$

$$
u = \frac {W L}{c} = \frac {0 . 4 2}{1} = 0. 4 2
$$

$$
E [ T s ] = \frac {W L}{\lambda} = \frac {0 . 4 2}{3 . 2} = 0. 1 3 h
$$

$$
\begin{array}{l} c _ {s} ^ {2} = \frac {\sum \frac {\lambda_ {i}}{\lambda} \cdot E [ T s _ {i} ] ^ {2} \cdot (1 + c _ {s i} ^ {2})}{\left(\sum \frac {\lambda_ {i}}{\lambda} \cdot E [ T s _ {i} ]\right) ^ {2}} - 1 = \\ = \frac {\frac {2 . 2}{3 . 2} \cdot 0 . 1 ^ {2} \cdot (1 + 1) + \frac {1}{3 . 2} \cdot 0 . 2 ^ {2} \cdot (1 + 1)}{\left(\frac {2 . 2}{3 . 2} \cdot 0 . 1 + \frac {1}{3 . 2} \cdot 0 . 2\right) ^ {2}} - 1 = 1. 3 \\ \end{array}
$$

# WS3 analysis

$$
\begin{array}{l} c _ {a 3} ^ {2} = \frac {\lambda_ {1}}{\lambda_ {3}} \cdot c _ {d 1} ^ {2} + \frac {\lambda_ {2}}{\lambda_ {3}} \cdot c _ {d 2} ^ {2} + \frac {p _ {3 3} \lambda_ {3}}{\lambda_ {3}} \cdot (p _ {3 3} \cdot c _ {d 3} ^ {2} + 1 - p _ {3 3}) = \\ = \frac {\lambda_ {1}}{\lambda_ {3}} \cdot 1 + \frac {\lambda_ {2}}{\lambda_ {3}} \cdot 1 + p _ {3 3} \cdot \left(p _ {3 3} \left(\left(1 - u _ {3} ^ {2}\right) \cdot c _ {a 3} ^ {2} + u _ {3} ^ {2} \cdot c _ {s 3} ^ {2}\right) + 1 - p _ {3 3}\right) \\ = \frac {2}{3 . 2} \cdot 1 + \frac {1}{3 . 2} \cdot 1 + 0. 0 6 2 5 \cdot \left(0. 0 6 2 5 \cdot \left(\left(1 - 0. 4 2 ^ {2}\right) \cdot c _ {a 3} ^ {2} + 0. 4 2 ^ {2} \cdot 1. 3\right) + 1 - 0. 0 6 2 5\right) = \\ = 0. 9 9 7 + 0. 0 0 3 2 \cdot c _ {a 3} ^ {2} \\ \end{array}
$$

$$
c _ {a 3} ^ {2} = 1. 0 0 0 2 2
$$

# WS3 analysis

$$
C T = \left(\frac {c _ {a} ^ {2} + c _ {s} ^ {2}}{2}\right) \left(\frac {u}{1 - u}\right) \cdot E [ T s ] + E [ T s ] = \left(\frac {1 + 1 . 3}{2}\right) \left(\frac {0 . 4 2}{1 - 0 . 4 2}\right) \cdot 0. 1 3 + 0. 1 3 = 0. 2 4 h
$$

$$
W I P = C T \cdot \lambda = 0. 2 4 \cdot 3. 2 = 0. 7 6 j o b s
$$

# System performance measures

$$
W I P = \sum W I P _ {i} = 1. 5 + 0. 6 7 + 0. 7 6 = 2. 9 3 j o b s
$$

$$
C T = \frac {W I P}{\lambda} = \frac {2 . 9 3}{3} = 0. 9 7 7 h
$$

# Cellular manufacturing

Group technology is the analysis of processing operations with the goal of determining the similarity of the processing functions and, hence, the grouping of the associated parts for production purposes   
> Establish sub-factories dedicated to the production of a subset of the total number of part types produced by the factory, where the part types have been grouped by common characteristics   
V Thus,the machines of the factory are grouped into cels of machines needed to produce the job type family assigned to that sub-factory   
The concept of organizing the factory into sub-factories with the capability to produce a technology group is called cellular manufacturing

# Types of layout

Best layout for combinations of product quantity and variety   
Initial step in identifying the possible facility layout configurations   
Many other parameters are considered, such as the relationships between the workstations,problems in their proximity, etc.

### Diagram Description: Product-Process Matrix (Variety vs. Quantity)

This diagram illustrates the classic trade-off between **Production Variety** (y-axis) and **Production Quantity** (x-axis), identifying the optimal manufacturing layout for different volume-variety combinations.

**1. Fixed Position Layout:**
*   **Characteristics:** Highest variety, lowest quantity (typically $\approx 1$ unit).
*   **Context:** Used for unique, large-scale projects where the product remains stationary (e.g., shipbuilding, construction).

**2. Process Layout (Job-shop):**
*   **Characteristics:** High variety, low quantity (ranging from 1 to 100 units).
*   **Context:** Organized by function or process; ideal for customized orders with intermittent flow.

**3. Cellular Layout (Batch Production):**
*   **Characteristics:** Medium variety, medium quantity (ranging from 100 to 10,000 units).
*   **Context:** Groups dissimilar machines into "cells" to process families of similar parts, balancing flexibility and efficiency.

**4. Product Layout (Mass Production):**
*   **Characteristics:** Lowest variety, highest quantity (from 10,000 to over 1,000,000 units).
*   **Categories:**
    *   **Quantity-based:** Standardized production in large volumes.
    *   **Flow line:** Continuous or semi-continuous assembly lines.
*   **Context:** Highly specialized equipment arranged according to the sequence of operations for a specific product.

# Types of layout

Fixed position layout

### Diagram Description: Fixed Position Layout

In a **Fixed Position Layout**, the product remains stationary due to its size, weight, or fragility. Instead of the product moving through different workstations, all necessary resources are brought to the product's location.

**1. Schematic Representation (Left):**
*   **Inputs:** Men (labor), Tools (equipment), and Components (materials) flow into a central **Workplace**.
*   **Output:** Once assembly is complete, the **Finished product** is moved directly to the store or customer site.

**2. Practical Example: Aircraft Assembly (Right):**
*   **The Product:** An airplane fuselage remains in a fixed position on the shop floor.
*   **The Resources:** Workers and mobile equipment are stationed around the product, moving as needed to perform specific tasks in different sections.

**Key Characteristics:**
*   **Variety:** Highest possible variety (unique projects).
*   **Quantity:** Lowest volume (typically 1 unit per project).
*   **Labor:** Highly skilled, decentralized workforce.
*   **Equipment:** General-purpose and mobile.

Process/Functional layout

### Diagram Description: Process / Functional Layout (Job Shop)

In a **Process Layout**, equipment and workstations are grouped together based on the specific function they perform or the process they represent, rather than the sequence of operations needed to make a specific product.

**1. Functional Grouping (Departments):**
The facility is divided into specialized departments:
*   **S:** Shaping (6 machines)
*   **M:** Milling (5 machines)
*   **D:** Drilling (4 machines)
*   **G:** Grinding (5 machines)
*   **A:** Assembly (4 workstations)

**2. Material Flow ("Spaghetti Flow"):**
*   The arrows trace the routing of different jobs through the factory. 
*   Because each customized product requires a unique sequence of operations, the material flow is highly complex, non-linear, and crisscrosses between departments. This creates a classic "spaghetti diagram" effect.
*   All jobs start from and return to a central **Receiving and shipping store**.

**Key Characteristics:**
*   **Flexibility:** Extremely high. The system can easily handle a wide variety of products and is robust against machine breakdowns (if one milling machine fails, another in the same department can take the load).
*   **Efficiency:** Lower. It involves high material handling costs, long setup times, complex scheduling, and high Work-In-Process (WIP) inventory.

# Types of layout

Cellular/Group layout

### Diagram Description: Cellular / Group Layout

In a **Cellular Layout**, machines are grouped into autonomous units called "cells" designed to process families of parts with similar manufacturing requirements.

**1. Cell Configurations:**
The facility is organized into three distinct cells, each following a compact flow:
*   **Cell 1:** Optimized for a specific sequence (L → L → M → M → D → L → L → A).
*   **Cell 2:** A larger cell incorporating Grinding (G) and Assembly (A), with designated "floor space available for marketing" or future expansion.
*   **Cell 3:** A streamlined cell for parts requiring a shorter processing cycle (L → L → M → D → G → G → A).

**2. Resource Legend:**
*   **L:** Lathe (Tornitura)
*   **M:** Milling (Fresatura)
*   **D:** Drilling (Foratura)
*   **G:** Grinding (Rettifica)
*   **A:** Assembly (Assemblaggio)

**3. Material Logistics:**
*   All materials originate from and return to the central **Receiving and shipping** area.
*   The U-shaped or circular flow within cells minimizes travel distance and material handling compared to a functional layout.

**Key Benefits:**
*   **Quantity:** Ideal for medium volumes (100–10,000 units).
*   **Efficiency:** Significant reduction in Work-In-Process (WIP) and setup times.
*   **Flexibility:** Combines the efficiency of a product line with the variety handling of a process layout.

Product/Line layout

### Diagram Description: Product / Line Layout

In a **Product Layout**, resources are arranged in a fixed sequence based on the specific processing needs of the product. This configuration is the hallmark of **Mass Production**.

**1. Dedicated Production Lines:**
The image depicts four separate flow lines, each with a standardized, unidirectional path:
*   **Line 1:** L $\rightarrow$ M $\rightarrow$ D $\rightarrow$ G $\rightarrow$ A
*   **Line 2:** L $\rightarrow$ L $\rightarrow$ M $\rightarrow$ G $\rightarrow$ A
*   **Line 3:** L $\rightarrow$ M $\rightarrow$ M $\rightarrow$ D $\rightarrow$ G
*   **Line 4:** L $\rightarrow$ M $\rightarrow$ G $\rightarrow$ G $\rightarrow$ A

**2. Operations Legend:**
*   **L:** Lathe (Tornitura)
*   **M:** Milling (Fresatura)
*   **D:** Drilling (Foratura)
*   **G:** Grinding (Rettifica)
*   **A:** Assembly (Assemblaggio)

**Key Metrics:**
*   **Quantity:** Very High (Mass Production).
*   **Variety:** Very Low (Standardized products).
*   **WIP:** Minimal, as the material flows continuously without intermediate storage.

# Functional layout vs Cellular layout

Functional layout: traditional plant organized according to the function of the machines   
Chaotic movement of the pieces in the plant

Cellular layout: Plant organized by processing cells   
Pieces divided into families   
Simplification of planning and scheduling

# Cellular manufacturing

# Advantages

More efficient processing by specializing in a smaller set of parts with as similar as possible processing operations (reduced setup times between part types due to their production similarities and from the learning-curve effects of part specialization)   
Reduced WIP in each sub-factory since parts only encounter other parts from the same technology group as well as due to a reduction in the service time squared coefficient of variation (C²s)   
Reduced material handling requirements since distances the jobs must travel between machines within a cell are usually much smaller than the length of the routes needed within a traditional setting

Material handling and facility layout issues are not addressed

# Cellular manufacturing

# Disadvantages

No economy of scale with respect to the total number of machines needed to produce all technology groups   
When a machine goes down there is a greater disruptive effect because there are fewer machines available with which to continue processing   
Utilization of machines is not balanced (some groups might have too high a utilization factor and others too low)

The standard production organization is to have one large production facility with similar machines/operations located together in workstations
> Modeling paradigm followed up to this point

# Example: traditional vs. cellular factory

Consider a manufacturing facility with 4 products and 5 machine types   
Machine usage by job type

| Job Type | Workstation 1 | Workstation 2 | Workstation 3 | Workstation 4 | Workstation 5 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| 1 | 1 | 1 | 1 | 0 | 0 |
| 2 | 1 | 1 | 1 | 0 | 0 |
| 3 | 0 | 0 | 1 | 1 | 1 |
| 4 | 0 | 0 | 1 | 1 | 1 |

Each job type requires 4 processing steps   
Mean arrival rate for each job type, sequence in which the workstations must be visited, and mean processing time at each step

| Job Type | Arrival Rate | WS Seq. (1) | WS Seq. (2) | WS Seq. (3) | WS Seq. (4) | Service T. (1) | Service T. (2) | Service T. (3) | Service T. (4) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **1** | 0.064/hr | 3 | 1 | 2 | 1 | 8 hr | 6 hr | 4.5 hr | 6 hr |
| **2** | 0.096/hr | 1 | 2 | 3 | 1 | 5 hr | 6 hr | 8 hr | 4 hr |
| **3** | 0.080/hr | 4 | 3 | 5 | 4 | 2 hr | 4 hr | 8 hr | 4 hr |
| **4** | 0.100/hr | 3 | 4 | 5 | 3 | 7 hr | 3 hr | 2 hr | 4 hr |

# Example: traditional vs. cellular factory

Arrival processes exponentially distributed (C²a = 1)   
> Total average rate of of 0.34 j/h

Processing times follow Erlang-2 distributions (C²s = 1/2)   
The number of machines at each workstation are 2,1, 3,1, and 1, respectively   
Compare the performances of the traditional model and the cellular model

# Traditional factory model

### Diagram Description: Queueing Network and Job Routing

This diagram graphically represents the routing paths for four different job types within a system composed of 5 workstations. Each line style identifies the specific flow of a traffic class, consistent with the arrival rates and sequences analyzed in the routing table.

**1. External Arrivals (Arrival Rates $\gamma$):**
*   **Job Type 1:** Arrives at Node 3 with $\gamma_1 = 0.064$.
*   **Job Type 2:** Arrives at Node 1 with $\gamma_2 = 0.096$.
*   **Job Type 3:** Arrives at Node 4 with $\gamma_3 = 0.08$.
*   **Job Type 4:** Arrives at Node 3 with $\gamma_4 = 0.1$.

**2. Traffic Class Routing Paths:**
*   **Class 1 (Solid Line):** Starts at Node 3 and follows the sequence $3 \rightarrow 1 \rightarrow 2 \rightarrow 1$.
*   **Class 2 (Dashed Line):** Starts at Node 1 and follows the sequence $1 \rightarrow 2 \rightarrow 3 \rightarrow 1$.
*   **Class 3 (Upper Dotted/Dashed Line):** Starts at Node 4 and follows the sequence $4 \rightarrow 3 \rightarrow 5 \rightarrow 4$.
*   **Class 4 (Lower Dot-Dash Line):** Starts at Node 3 and follows the sequence $3 \rightarrow 4 \rightarrow 5 \rightarrow 3$.

**3. Node Interaction and Topology:**
*   **Node 3 (Central Hub):** Functions as the primary distribution point, receiving external inputs for Job Types 1 and 4, while managing transit flows for Job Types 2 and 3.
*   **Interaction 1-2:** There is a strong interchange between Nodes 1 and 2 for "Family A" traffic classes (Jobs 1 and 2).
*   **Interaction 4-5:** Nodes 4 and 5 primarily handle the flows for "Family B" traffic classes (Jobs 3 and 4).

P =

$$
P = \begin{pmatrix}
0 & \frac{0,064 + 0,096}{0,32} & 0 & 0 & 0 \\
\frac{0,064}{0,16} & 0 & \frac{0,096}{0,16} & 0 & 0 \\
\frac{0,064 + 0,096}{0,44} & 0 & 0 & \frac{0,1}{0,44} & \frac{0,08}{0,44} \\
0 & 0 & \frac{0,08}{0,26} & 0 & \frac{0,1}{0,26} \\
0 & 0 & \frac{0,1}{0,18} & \frac{0,08}{0,18} & 0
\end{pmatrix}
$$

$$ \lambda_1 = \gamma_1 + \gamma_1 + \gamma_2 + \gamma_2 = 0,32 $$

$$ WL_1 = 0,064 \cdot 6 + 0,064 \cdot 6 + 0,096 \cdot 5 + 0,096 \cdot 4 = 1,632 $$

$$ u_1 = \frac{WL_1}{2} = 0,816 $$

$$ E[T_s(1)] = \frac{WL_1}{\lambda_1} = \frac{1,632}{0,32} = 5,1 \text{ h} $$

$$ C_s^2(1) = \frac{\sum_{i=1}^m \left( \frac{\lambda_{i,1}}{\lambda_1} (E[T_s(i,1)])^2 \cdot (1 + C_s^2(i,1)) \right)}{E[T_s(1)]^2} - 1 $$

$$ C_s^2(1) = \frac{\frac{0,064}{0,32} \cdot 6^2 (1 + \frac{1}{2}) \cdot 2 + \frac{0,096}{0,32} \cdot 5^2 (1 + \frac{1}{2}) + \frac{0,096}{0,32} \cdot 4^2 (1 + \frac{1}{2})}{5,1^2} - 1 = 0,54 $$

# Traditional factory model

Workload computation for each workstation   
Workstation 1 is visited twice by Job Type 1 (6 hours processing on visit 1 and 6 hours processing on visit 2) twice by Job Type 2 (5 hours processing on visit 1 and 4 hours processing on visit 2)   
The arival rate is 0.064 jobs/hour for Type 1 and 0.096 jobs/hour for Type 2   
Hence the workload of Workstation 1 is

$$ WL_1 = (6 \cdot 0.064 + 6 \cdot 0.064) + (5 \cdot 0.096 + 4 \cdot 0.096) = 1,632 $$

The utlization factor for Workstation 1,u1, is the workload divided by the number of machines at the workstation

$$
\mathrm {u} _ {1} = 1. 6 3 2 / 2 = 0. 8 1 6
$$

# Traditional factory model

A similar analysis for the other four workstations yields these results

| Workstation # | Num Machines | Workload | Utilization |
| :---: | :---: | :---: | :---: |
| 1 | 2 | 1.632 | 0.816 |
| 2 | 1 | 0.864 | 0.864 |
| 3 | 3 | 2.700 | 0.900 |
| 4 | 1 | 0.780 | 0.780 |
| 5 | 1 | 0.840 | 0.840 |


# Traditional factory model

The expected processing time for Workstation 1 is a function of the three distinct processing times and the relative frequencies of these visits   
Y Job Type 1 uses the machine twice but has the same processing time for each visit   
For Workstation 1, the total arrival rate of jobs is 0.32 per hour (two inflows of Job Type 1 at a rate of O.064 per hour and two inflows of Job Type 2 at a rate of O.096 per hour)   
Thus, the mean processing time and SCV are computed as

$$ E[S_1] = \left(\frac{0.064}{0.32}\right)6 + \left(\frac{0.064}{0.32}\right)6 + \left(\frac{0.096}{0.32}\right)5 + \left(\frac{0.096}{0.32}\right)4 = 5.100 \text{ hr} $$

$$ E[S_1^2] = 2\left(\frac{0.064}{0.32}\right)6^2(1+1/2) + \left(\frac{0.096}{0.32}\right)5^2(1+1/2) + \left(\frac{0.096}{0.32}\right)4^2(1+1/2) = 40.05 \text{ hr}^2 $$

$$ C_s^2(1) = \frac{E[S_1^2] - E[S_1]^2}{E[S_1]^2} = \frac{40.05 - 26.01}{26.01} = 0.540 $$

# Traditional factory model

A similar analysis for the other four workstations yields these results

| Workstation $k$ | $\lambda_k$ | $E[S_k]$ | $C_s^2(k)$ |
| :---: | :---: | :---: | :---: |
| 1 | 0.32/hr | 5.100 hr | 0.540 |
| 2 | 0.16/hr | 5.400 hr | 0.528 |
| 3 | 0.44/hr | 6.136 hr | 0.631 |
| 4 | 0.26/hr | 3.000 hr | 0.603 |
| 5 | 0.18/hr | 4.667 hr | 1.112 |

# Traditional factory model

Definition of the Routing matrix to compute the SCV of arrivals in each workstation

$$
P = \begin{bmatrix} 
0 & \frac{0.064 + 0.096}{0.32} & 0 & 0 & 0 \\ 
\frac{0.064}{0.16} & 0 & \frac{0.096}{0.16} & 0 & 0 \\ 
\frac{0.064 + 0.096}{0.44} & 0 & 0 & \frac{0.1}{0.44} & \frac{0.08}{0.44} \\ 
0 & 0 & \frac{0.08}{0.26} & 0 & \frac{0.1}{0.26} \\ 
0 & 0 & \frac{0.1}{0.18} & \frac{0.08}{0.18} & 0 
\end{bmatrix} 
$$ 

=

$$
\begin{bmatrix} 
0 & 0.5 & 0 & 0 & 0 \\ 
0.4 & 0 & 0.6 & 0 & 0 \\ 
0.3636 & 0 & 0 & 0.2273 & 0.1818 \\ 
0 & 0 & 0.3077 & 0 & 0.3846 \\ 
0 & 0 & 0.5556 & 0.4444 & 0 
\end{bmatrix}
$$

# Traditional factory model

Computation of SCV of arrivals in each workstation

$$
C _ {a} ^ {2} (1) = 0. 0 2 0 3 C _ {a} ^ {2} (2) + 0. 0 3 4 6 C _ {a} ^ {2} (3) + 0. 8 8 5 6
$$

$$
C _ {a} ^ {2} (2) = 0. 1 6 7 1 C _ {a} ^ {2} (1) + 0. 7 2 4 6
$$

$$
C _ {a} ^ {2} (3) = 0. 0 3 3 2 C _ {a} ^ {2} (2) + 0. 0 2 1 9 C _ {a} ^ {2} (4) + 0. 0 3 7 2 C _ {a} ^ {2} (5) + 0. 8 5 8 1
$$

$$
C _ {a} ^ {2} (4) = 0. 0 1 6 6 C _ {a} ^ {2} (3) + 0. 0 4 0 3 C _ {a} ^ {2} (5) + 0. 9 3 8 8
$$

$$
C _ {a} ^ {2} (5) = 0. 0 1 5 4 C _ {a} ^ {2} (3) + 0. 0 8 3 7 C _ {a} ^ {2} (4) + 0. 8 3 5 4.
$$

System solution

$$
\mathbf {c} _ {\alpha} ^ {2} = (0. 9 3 6 1, 0. 8 8 1 0, 0. 9 4 3 7, 0. 9 9 2 1, 0. 9 3 2 9)
$$

# Traditional factory model

Performance for Workstation 1

$$
\begin{array}{l} C T (1) = \left(\frac {C _ {a} ^ {2} (1) + C _ {s} ^ {2} (1)}{2}\right) \left(\frac {u _ {1} ^ {\sqrt {6} - 1}}{2 \left(1 - u _ {1}\right)}\right) E \left[ T _ {s} (1) \right] + E \left[ T _ {s} (1) \right] \\ = \left(\frac {0 . 9 3 6 + 0 . 5 4 0}{2}\right) \left(\frac {0 . 8 1 6 ^ {1 . 4 4 9}}{0 . 3 6 8}\right) 5. 1 0 0 + 5. 1 0 0 = 1 2. 7 2 \mathrm {h r}. \\ \end{array}
$$

> By using Little's law, the WIP is 0.32*12.714 = 4.068 jobs

# Traditional factory model

Same analysis for the other workstations

| Workstation k | Lambda_k | CT(k) | WIP(k) |
| :---: | :---: | :---: | :---: |
| 1 | 0.32/hr | 12.714 hr | 4.068 |
| 2 | 0.16/hr | 29.557 hr | 4.729 |
| 3 | 0.44/hr | 19.408 hr | 8.539 |
| 4 | 0.26/hr | 11.482 hr | 2.985 |
| 5 | 0.18/hr | 29.718 hr | 5.349 |

The total WIP is 25.67 jobs   
The total CT is 25.67/0.34 = 75.5 hours

# Cellular factory model

| Job Type | Workstation 1 | Workstation 2 | Workstation 3 | Workstation 4 | Workstation 5 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **1** | 1 | 1 | 1 | 0 | 0 |
| **2** | 1 | 1 | 1 | 0 | 0 |
| **3** | 0 | 0 | 1 | 1 | 1 |
| **4** | 0 | 0 | 1 | 1 | 1 |

From the first table,it is easy to see that a two-group partitioning of the products is possible

> Job Types 1 and 2 in Group 1 produced by Cell 1   
> Job Types 3 and 4 in Group 2 produced in Cell 2

Both groups have Machine 3 requirements with workloads by group of 1.280 and 1.420, respectively, for Groups 1 and 2

> Since both of these cells require at least two machines of Type 3, an additional machine must be purchased to implement the disjoint cellular manufacturing approach

# Cellular factory model

Obtained performance measures by repeating the computations of the traditional factory model

| | $th$ | $WIP$ | $CT$ |
| :--- | :---: | :---: | :---: |
| **Cell 1** | 0.16/hr | 10.543 | 65.896 hr |
| **Cell 2** | 0.18/hr | 10.943 | 60.792 hr |

These results seem better, but the comparison is not fair since an extra machine had to be purchased to establish the cellular organization   
To appropriately compare the two factory organizational schemes, the performance measures of the traditional factory layout are recalculated using an additional machine for Workstation 3   
The recalculation yields a total system WiP of 20.578 for the traditional factory as compared to the total system WIP of 21.486 for the cellular factory

# Cellular factory model

One of the keys for cellular manufacturing is the reduction in processing times due to the similarities of jobs being processed on a machine   
For this example, we assume a 25% decrease in the processing time for Machine 3 for both technology groups   
The resulting performance measures for the cellular factory are

| | $th$ | $WIP$ | $CT$ |
| :--- | :---: | :---: | :---: |
| **Cell 1** | 0.16/hr | 9.848 | 61.548 hr |
| **Cell 2** | 0.18/hr | 9.785 | 54.359 hr |

Total WIP = 19.633

# Conclusion

This example illstrates that a group technology/cellular manufacturing organization of the factory can yield a cycle time reduction when implemented in a logical fashion only if there are resulting reductions in the setup and/or processing times   
The partitioning of the factory into several non-overlapping production cells is not the actual phenomena from which the improvements in the performance measures are gained

> The gains are mainly due to the improvements in production that can be associated with specialization: setup reductions, learning curve effects (reduced processing times), processing simplifications,and improved quality due to specialization

In addition, the material handling/part transportation aspects of the factory may also be more specialized and certainly less travel distance will be realized in a cellular organization
