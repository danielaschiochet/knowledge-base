# Analysis and Management of Production System

# Lesson 6: Multiple Product Factory Models

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Introduction

> Most manufacturing facilities are setup to produce more than a single product   
Even in the case of single product facilities,if the product visits a workstation more than once with different processing times at each visit, then the workstation sees the equivalent of multiple products   
V Such revisiting production schemes are called re-entrant flow systems   
V Modeling multiple product facilities is not significantly more difficult than modeling single product systems

# Flow conservation

Job flow needs to be maintained by product type   
The number of visits to each workstation by product class is needed   
V Different products can have different probabilistic flows through the production facility as well as diferent processing time characteristics   
> The number of visits to each workstation by product needs to be developed   
V This analysis requires the solution of a network flow system of equations by product   
The processing time is assumed to follow the same distribution for each product on each visit to a given workstation

# Product flow rates

V To compute the workload on the workstation, the number of visits to the workstation by each product is computed first   
> It is necessary to distinguish between products visiting the same workstation

> Xi,k = arrival rate of product type i to workstation k   
> Xi= vector giving the total arrival rates of product type iinto each station   
Y Yi,k= external arrival rate of product i into workstation k   
>pjk = probabilitythat an individualitem of product ileaving workstation j goes to workstation k   
> pi= matrix of these probabilites for product i

# Product flow rates

> Consider a factory of n workstations where product type ifollows the switching rule defined by routing matrix Pi and assume that the sum of at least one row of Pi is stictly less than one (i.e., jobs exit the network from at least one workstation)   
Let yi=(Yi,1.., Yi,n) denote a vector consisting of the mean arval rate of type i jobs from an external source to the workstation   
> Let λi=(i,1..,λi,n) be te (unknown) vector denoting mean arrval rate of all type i jobs to the workstations   
V The vector 𝜆i is given by: λ=(I-(Pi)T)-1γi where l is an n × n identity matrix and (Pi)T is the transpose of pi

# Product flow rates

The total arrival rate of jobs to workstation k is given by the sum of the different product types:

$$
\lambda_ {k} = \sum_ {i = 1} ^ {m} \lambda_ {i, k}
$$

where m is the total number of product types within the factory

Consider a four-workstation facility that processes two products with each product arriving to the first workstation according to individual Poisson arrival streams, each at a rate of 5 per hour   
> Product 1 uses only the first three workstations with the routing structure displayed in the firstfigure   
V Product 2 uses allfour workstations with the routing structure displayed in the second figure

![](images/8bc0bdf759372ed27aa807e5be2c101c4d9040027f61c9c4371ae6857a1685f8.jpg)

![](images/de047f00c4fd8afe54fe372950b801cdeb4c7b64755191b689e52944cf761b3a.jpg)

# Example

V Assume that there is one machine at each workstation and that the processing time data for the two products are:

![](images/ec7c665f76589ebc89a852b67cf8100cc38b694573512cefe5e7370896522e0d.jpg)

# Example

V To determine the mean arrval rate to each workstation of Type 1 and Type 2 jobs is simply to repeat the steps of previous examples

$$
\boldsymbol {\lambda} ^ {1} = (5. 6 9 0, 4. 2 6 7, 5. 2 6 3, 0)
$$

$$
\boldsymbol {\lambda} ^ {2} = (6. 2 5, 6. 6 6 7, 5. 8 3 3, 1 2. 5)
$$

> The total rate into each workstation is the sum of the individual product inflows

$$
\boldsymbol {\lambda} = (1 1. 9 4 0, 1 0. 9 3 4, 1 1. 0 9 6, 1 2. 5)
$$

# Workstation workload

V Once the workstation arrival rates by product type have been determined, the workload for each workstation can be computed   
V The workload is the total amount of work required by a workstation per unit of time   
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

Y Since there is one machine per workstation, the workload and utilization factors are the same at each workstation so that

$$
u = (0. 8 2 3 1, 0. 7 9 7 1, 0. 8 3 6 9, 0. 7 5)
$$

With utiization factors alless than 1.0,the factory can achieve steadystate and further analysis is possible

# Service time characteristics

> For workstation k the service time will be the random variable Ts(i,k), whenever Product i is being processed   
The service time for an arbitrary job is the random variable Ts(k).   
> In the long-run, the probability that a given machine at Workstation k will be processing a Type ijob is λ,k^k   
Ts(k) is a mixture of random variables

$$
T _ {s} (k) = \left\{ \begin{array}{l l} T _ {s} (1, k) & \text {w i t h p r o b a b i l i t y} \frac {\lambda_ {1 , k}}{\lambda_ {k}} \\ \vdots \\ T _ {s} (m, k) & \text {w i t h p r o b a b i l i t y} \frac {\lambda_ {m , k}}{\lambda_ {k}} \end{array} \right.
$$

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

Since E[X2]=E[X]2(1+C²[X]), then

$$
\mathrm {C} ^ {2} [ \mathrm {X} ] = \mathrm {E} [ \mathrm {X} ^ {2} ] / \mathrm {E} [ \mathrm {X} ] ^ {2} - 1
$$

V Coefficient of variation for the service time at workstation k:

$$
C _ {s} ^ {2} (k) = \frac {\sum_ {i = 1} ^ {m} \left(\frac {\lambda_ {i , k}}{\lambda_ {k}}\right) E [ T _ {s} (i , k) ] ^ {2} \left(1 + C _ {s} ^ {2} (i , k)\right)}{(\sum_ {i = 1} ^ {m} \left(\frac {\lambda_ {i , k}}{\lambda_ {k}}\right) E [ T _ {s} (i , k) ]) ^ {2}} - 1
$$

# Example

V Using the arrival rate and the service time data, the service time for the first workstation is:

$$
E [ T _ {s} (1) ] = \left(\frac {5 . 6 9 0}{1 1 . 9 4}\right) \frac {1}{1 4} + \left(\frac {6 . 2 5 0}{1 1 . 9 4}\right) \frac {1}{1 5} = 0. 0 6 8 9 h r
$$

The squared coeficient of variation is:

$$
C _ {s} ^ {2} (1) = \frac {\left(\frac {5 . 6 9 0}{1 1 . 9 4}\right) \left(\frac {1}{1 4}\right) ^ {2} (1 + 0 . 8) + \left(\frac {6 . 2 5 0}{1 1 . 9 4}\right) \left(\frac {1}{1 5}\right) ^ {2} (1 + 1 . 3 3)}{(0 . 0 6 8 9) ^ {2}} - 1 = 1. 0 6 1 6
$$

# Example

Service time parameters for all the workstations:

![](images/2dae3a311c26a4fda42c541297f359aa56a5a682af9dabe5264f289bc508f801.jpg)

# Workstation performance measures

The multiple product facility problem is now reduced to a problem similar to the single product analysis since the workstation composite service time data are now known   
Consider a factory of n workstations with m diferent job types   
V Assume that the total arrival rate of job type i to workstation k is given by 𝜆i,k,and the probability that a job of type i leaving workstation j will be routed to workstation k is given by pj,k   
V The composite routing matrix,P=(pjk) gives the switching probabilities of an arbitrary job and is determined by:

$$
p _ {j k} = \frac {\sum_ {i = 1} ^ {m} \lambda_ {i j} p _ {j k} ^ {i}}{\lambda_ {j}} \quad \mathrm {f o r j , k = 1 , \ldots , n}
$$

# Example

We now complete the analysis of the factory   
V The matrix of probabilities are obtained

>For example, the probability of going from Workstation 2 to Workstation 1 is determined as:

$$
p _ {2 1} = \frac {\lambda_ {1 2} p _ {2 1} ^ {1} + \lambda_ {2 2} p _ {2 1} ^ {2}}{\lambda_ {2}} = \frac {4 . 2 6 7 (0 . 1) + 6 . 6 6 7 (0)}{1 0 . 9 3 4} = 0. 0 3 9
$$

Continuing with the other workstations

$$
P = \left[ \begin{array}{c c c c} 0 & 0. 7 0 6 & 0. 2 9 4 & 0 \\ 0. 0 3 9 & 0 & 0. 3 5 1 & 0. 6 1 0 \\ 0. 0 2 4 & 0 & 0 & 0. 5 2 6 \\ 0. 1 0 0 & 0. 2 0 0 & 0. 3 0 0 & 0 \end{array} \right]
$$

V The analysis required to obtain the mean waiting times in the workstations is the same procedure as for individual product systems once the composite product data and transition probability matrix Phave been developed   
V The squared coefficient of variation for the arrival streams into each workstation is again obtained by solving the Ca² system of equations

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

》 The cycle time by workstation is given as the composite time for all products visiting that workstation

![](images/7f9db1caef94b381f32672121d6cf82e411316ee5210e02435d6e2021cc4f96f.jpg)

V The total facility performance measures are for the total work in the facility and are not distinguishable by product type   
> The total system work-in-process is the sum of the workstation WiP's and equals 19.238   
The total inflow and, hence, throughput for the system is 10/hr   
V Thus,the average cycle time in te system for allitems by Little's Law is 19.238/10 = 1.9238 hours

# Mean time spent within the factory

Consider a factory of n workstations with m different job types   
V Assume that the external arival rate of jobs of type i to workstation k is given by Yi,k,and the total arival rate of Job Type i to workstation is given byi,k   
> Furthermore assume that the mean time spent waiting for processing in workstation k by an arbitrary job (namely, CTq(k)) has been determined   
The mean time spent within the factory by a type i job is given by:

$$
C T _ {s} ^ {i} = \frac {\sum_ {k = 1} ^ {n} \lambda_ {i k} \big (C T _ {q} (k) \big) + E [ T _ {s} (i , k) ] \big)}{\sum_ {j = 1} ^ {n} \gamma_ {i j}} \mathrm {f o r i = 1 , \ldots , m}
$$

# Example

System mean cycle times by individual product type   
V For this example these computations are

$$
\begin{array}{l} C T ^ {1} = [ 5. 6 9 0 (0. 3 3 0 7 + 0. 0 7 1 4) + 4. 2 6 7 4 (0. 3 8 7 0 + 0. 1) \\ + 5. 2 6 3 2 (0. 5 0 1 5 + 0. 0 6 6 7) ] / 5 = 1. 4 7 1 4 \mathrm {h r} \\ \end{array}
$$

$$
\begin{array}{l} C T ^ {2} = [ 6. 2 5 (0. 3 3 0 7 + 0. 0 6 6 7) + 6. 6 6 6 7 (0. 3 8 7 0 + 0. 0 5 5 6) \\ + 5. 8 3 3 3 (0. 5 0 1 5 + 0. 0 8 3 3) + 1 2. 5 (0. 1 8 2 8 + 0. 0 6) ] / 5 = 2. 3 7 6 3 \mathrm {h r} \\ \end{array}
$$

D These two products are produced in equal quantities, so the average cycle time for the factory is the average of these two individual product cycle times or 1.9238 hours

# Example

V To demonstrate that this modeling approach is adequate for most decision making situations, these analytical results are compared with simulation results   
Y Allthe critical parameters are close enough for the analytical model to be a usable tool for decision purposes

![](images/d70c5a36fdd7fc1ae8d116a319ce47781055036426c1cce1972b81cf6fbf4e7e.jpg)

# Exercise 1

> Afactory is composed by three workstations in series,and produces two types of products   
> The first two workstations have the same processing time for both types of product, both exponentially distributed

E[Ts(1,1)]= E[Ts(2,1)]= 0.20 h   
E[Ts(1,2)]= E[Ts(2,2)]= 0.15 h

> The third workstation has two diferent processing times E[Ts(1,3)]=0.14 h and E[Ts(2,3)]=0.25 h, both exponentially distributed   
V The inter-arrival times of both product types are exponentially distributed: type 1 with average rate of 3,and type 2 with average rate of 1   
Find the system work in process and cycle time

# Solution

![](images/d0c67164f3047e999448c172df71a2e13936197b0a41f4f022b4f591652c21b3.jpg)

>11 = 3j/h,λ21 = 1 j/h   
^12 = 3j/h, ^22 = 1 j/h   
^13 = 3j/h, λ23= 1 j/h

λ1 = 4 j/h, λ2 = 4 j/h,λ3 = 4 j/h

# Solution

![](images/25a8653b4680d03883d54440d6f46584666afce719c6fbe4fcc4c96a0cf740df.jpg)

WL1 = u1 = λ, E[Ts(1)]= 4*0.20 = 0.8   
WL2 = u2= ^ E[Ts(2)]= 4*0.15 = 0.6   
V WL3 = u3= ^13 E[Ts(1,3)] + ^23 E[Ts(2,3)] = 3*0.14+1*0.25= 0.67   
V E[Ts(3)]=3/4 *0.14 + 1/4*0.25 = 0.1675 h   
V C²s(3)= [3/4 *0.14² (1+1) + 1/4*0.252 (1+1)/0.1675² -1 = 1.16   
C²a(1)=C²(2)=C²a(3)=3/*1 + 4*1 = 1

# Solution

![](images/e6922c4e9d529863dbd3a4ec9ad55bc1e10ddb97811789e7784f55f0eb71d501.jpg)

CT(1)=u1/(1-u1)*E[Ts(1)] + E[Ts(1)] = 0.8/0.2 * 0.2 + 0.2 = 1 h   
V WIP(1)= TH*CT(1)=4*1=4 j

V CT(2)=u2/(1-u2) * E[Ts(2)] + E[Ts(2)]= 0.6/0.4 * 0.15 + 0.15= 0.375 h   
WIP(2)= TH*CT(1) = 4*0.375 = 1.5 j

V CT(3)= (C²(3) +C2(3)/2 *u3/(1-u3)*E[Ts(3)) + E[Ts(3)]=(1+1.16)/2*0.67/0.33*0.1675+0.1675=0.535h   
V WIP(3)= TH*CT(3)= 4*0.535= 2.14 j

V CT = 1 + 0.375 + 0.535= 1.91 h   
V WIP = 4 + 1.5 + 2.14 = 7.64 j

# Solution

![](images/0e20b78a41c3bfb22002d9f2e60682fdf559df816afa99cd9da925252c9a0507.jpg)

V CT1 = [3(0,8+0,2) + 3(0,225+0,15) + 3(0,3675+0,14)/3 = 1.88 h   
CT² = (0,8+0,2) + (0,225+0,15) + (0,3675+0,25) = 1.99 h   
V CT =  CT1 + 4 CT² = 1.91 h

# Exercise 2

V A facility is composed by 3 workstations and produces 2 types of products.   
V The first product type is processed by WS1 and WS3. Processing times are exponentially distributed, and the average values are O.3 h and O.1 h, respectively. In the 10% of the cases, the product need to be reworked by WS3.   
The second product type is processed by WS2 and WS3. Processing times are exponentially distributed, and the average values are 0.4 h and 0.2 h, respectively.   
V The inter-arrival times of product types are exponentially distributed: type 1 with average rate of 2 j/h, and type 2 with average rate of 1 j/h.   
V Find the system performance measures.

# Network topology

![](images/a9dbcc79dbf41b90491b07373c5898ea5afc1c5ef11ea8506b6f727b6899cf76.jpg)

![](images/c83d9bc1c7a8137eb13971bc6a17ac50be7a945fd359a80b4614e644dc923561.jpg)

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

![](images/c1dcf6ec36194dc0e81076e8f8d6d7d2fb9380f134eca53aced2d9aca85a9f5e.jpg)

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

![](images/711e6ec066c1836926be67498fe1c48f6f45cc05e3c6cb7a32817e2fb77c85fc.jpg)

# WS3 analysis

![](images/530255ba4294c0dae1912f4098e8a9a2d6fa2c2f02703291c3c9f43a171360c8.jpg)

$$
\lambda_ {3} = \lambda_ {1} + \lambda_ {2} + 0. 1 \lambda_ {1} = 3. 2 \frac {j o b s}{h}
$$

P=

![](images/6bba7c0fbf2bbe81c17f4c7e651c48f37afd2fd1d6041062638e2cb5d2cd65e7.jpg)

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
V Establish sub-factories dedicated to the production of a subset of the total number of part types produced by the factory, where the part types have been grouped by common characteristics   
V Thus,the machines of the factory are grouped into cels of machines needed to produce the job type family assigned to that sub-factory   
V The concept of organizing the factory into sub-factories with the capability to produce a technology group is called cellular manufacturing

# Types of layout

Best layout for combinations of product quantity and variety   
V Initial step in identifying the possible facility layout configurations   
Many other parameters are considered, such as the relationships between the workstations,problems in their proximity, etc.

![](images/e8b38b44e1ce3b1fde99dde784df53be27fc86c7104d8aacfcb065e577534ee6.jpg)

# Types of layout

Fixed position layout

![](images/b20b5bcf79f972abb6287f2a68bfcf7e69c86a83b590a2bd42a35e62d3d10949.jpg)

![](images/950b0a16f18e789ec99179043f81e7ba9a8ccd0e43ed32887b4d4f00cac59103.jpg)

![](images/58aa6a067fbd543d5a6344057fc3cfa615417ac0f1bc21f8cb0145ebb53fcc64.jpg)

Process/Functional layout

![](images/f4ba2cc94b1f1b5cbfc629a58373123d74e018e400e990a16baa64df2e9cfaaa.jpg)

# Types of layout

Cellular/Group layout

![](images/7f6ff8b23913f35e66bc1ab6311cdd220ac38f6fe6aab9d192342e1214fa0e04.jpg)

Product/Line layout

![](images/33c0bc6de94b2f2a0f13df61baf3157b44f1d38031d578b78af1c662d0f7c741.jpg)

# Functional layout vs Cellular layout

Functional layout: traditional plant organized according to the function of the machines   
? Chaotic movement of the pieces in the plant

![](images/f0b0edfc59c2c7f3ab369366e1f2db2147b56b2e06c661b53e0362a09d51fe7f.jpg)

Cellular layout: Plant organized by processing cells   
Pieces divided into families   
V Simplification of planning and scheduling

![](images/6515782737329fd8bc92267981de85e8e65def322d6882a066b000f9a819bf27.jpg)

# Cellular manufacturing

# Advantages

More efficient processing by specializing in a smaller set of parts with as similar as possible processing operations (reduced setup times between part types due to their production similarities and from the learning-curve effects of part specialization)   
Reduced WIP in each sub-factory since parts only encounter other parts from the same technology group as well as due to a reduction in the service time squared coefficient of variation (C²s)   
V Reduced material handling requirements since distances the jobs must travel between machines within a cell are usually much smaller than the length of the routes needed within a traditional setting

V Material handling and facility layout issues are not addressed

# Cellular manufacturing

# Disadvantages

> No economy of scale with respect to the total number of machines needed to produce all technology groups   
V When a machine goes down there is a greater disruptive effect because there are fewer machines available with which to continue processing   
V Utilization of machines is not balanced (some groups might have too high a utilization factor and others too low)

V The standard production organization is to have one large production facility with similar machines/operations located together in workstations

V Modeling paradigm followed up to this point

# Example: traditional vs. cellular factory

V Consider a manufacturing facility with 4 products and 5 machine types   
Machine usage by job type

![](images/360f8b1e2c48b5776a877de411007b998c1377f04c888e10d5f7a77da6405447.jpg)

Each job type requires 4 processing steps   
V Mean arrival rate for each job type, sequence in which the workstations must be visited, and mean processing time at each step

![](images/9539048f1fd65a15ced93899050a9f464a2054a32b676b1455445e5244bf170f.jpg)

# Example: traditional vs. cellular factory

Arrival processes exponentially distributed (C²a = 1)   
Total average rate of of 0.34 j/h

V Processing times follow Erlang-2 distributions (C2 = 1/2)   
V The number of machines at each workstation are 2,1, 3,1, and 1, respectively   
> Compare the performances of the traditional model and the cellular model

# Traditional factory model

![](images/5c14fa35dbe7d5daf651748912118b83e43037302c6573499b2ca341a47eca80.jpg)

$$
\angle 1 = 0. 0 6 5 \cdot 6 + 0. 0 6 4 \cdot 6 + 0. 0 9 6 \cdot 5 + 0. 0 3 6 \cdot 4 = 1, 6 3 2
$$

$$
u _ {1} = \frac {W L _ {2}}{2} = 0. 8 1 6
$$

$$
E [ T _ {S} (4) ] = \frac {W L _ {1}}{\lambda_ {1}} = \frac {1 . 6 3 2}{0 . 3 2} = 5. 1 h
$$

$$
C _ {3} ^ {2} (1) = \frac {\sum_ {i = 1} ^ {\infty} \left(\frac {\lambda_ {i , 4}}{\lambda_ {i}} (C [ T _ {3} (i , i) ] ^ {2} \cdot (1 + C _ {5} ^ {2} (i , 4))}{\in [ i s (4) ] ^ {2}} - 1\right){5 . 1 ^ {2}} = \frac {0 . 0 6 9 \cdot C ^ {2} (1 + \frac {1}{2}) \cdot 2 + \frac {0 . 0 9 6}{0 . 3 2} \cdot S ^ {2} (1 + \frac {1}{2}) + \frac {0 . 0 9 6}{0 . 3 2} \cdot C ^ {2} (1 + \frac {1}{2})}{1} - 1 = 0. 5 4
$$

$$
\begin{array}{r l} & {1 \left( \begin{array}{l l l l l} 1 & 2 & 3 & 4 & 5 \\ 0 & 0. 0 6 5 + 0. 0 8 & 0 & 0 & 0 \\ \frac {0 . 0 6 5}{0 . 1 6} & 0 & \frac {0 . 0 9 5}{0 . 1 6} & 0 & 0 \\ \frac {0 . 0 6 5 + 0 . 0 8}{0 . 3 3} & 0 & 0 & \frac {0 . 1}{0 . 4 4} & \frac {0 . 0 8}{0 . 4 4} \\ 0 & 0 & \frac {0 . 0 8}{0 . 2 6} & 0 & \frac {0 . 1}{0 . 2 6} \\ 0 & 0 & \frac {0 . 1}{0 . 1 8} & \frac {0 . 0 8}{0 . 1 8} & 0 \end{array} \right)} \end{array}
$$

![](images/b257706165a67e97fabc92f33e6ffa84650473d621ff19dc6e4dac5af1bc1b22.jpg)

# Traditional factory model

Workload computation for each workstation   
V Workstation 1 is visited twice by Job Type 1 (6 hours processing on visit 1 and 6 hours processing on visit 2) twice by Job Type 2 (5 hours processing on visit 1 and 4 hours processing on visit 2)   
V The arival rate is 0.064 jobs/hour for Type 1 and 0.096 jobs/hour for Type 2   
V Hence the workload of Workstation 1 is

$$
\mathrm {W L} _ {1} = (6 ^ {*} 0. 0 6 4 + 6 ^ {*} 0. 0 6 4) + (5 ^ {*} 0. 0 9 6 + 4 ^ {*} 0. 0 9 6) = 1. 6 3 2
$$

V The utlization factor for Workstation 1,u1, is the workload divided by the number of machines at the workstation

$$
\mathrm {u} _ {1} = 1. 6 3 2 / 2 = 0. 8 1 6
$$

# Traditional factory model

Y A similar analysis for the other four workstations yields these results

![](images/fa2655d4d0f009f0bba20de43f0411302c904f6eaa2e1db9657f97f41615e7a9.jpg)

# Traditional factory model

The expected processing time for Workstation 1 is a function of the three distinct processing times and the relative frequencies of these visits   
Y Job Type 1 uses the machine twice but has the same processing time for each visit   
For Workstation 1, the total arrival rate of jobs is 0.32 per hour (two inflows of Job Type 1 at a rate of O.064 per hour and two inflows of Job Type 2 at a rate of O.096 per hour)   
Thus, the mean processing time and SCV are computed as

$$
\begin{array}{l} E \left[ S _ {1} \right] = \left(\frac {0 . 0 6 4}{0 . 3 2}\right) 6 + \left(\frac {0 . 0 6 4}{0 . 3 2}\right) 6 + \left(\frac {0 . 0 9 6}{0 . 3 2}\right) 5 + \left(\frac {0 . 0 9 6}{0 . 3 2}\right) 4 = 5. 1 0 0 \mathrm {h r} \\ E \left[ S _ {1} ^ {2} \right] = 2 \left(\frac {0 . 0 6 4}{0 . 3 2}\right) 6 ^ {2} (1 + 1 / 2) + \left(\frac {0 . 0 9 6}{0 . 3 2}\right) 5 ^ {2} (1 + 1 / 2) + \left(\frac {0 . 0 9 6}{0 . 3 2}\right) 4 ^ {2} (1 + 1 / 2) = 4 0. 0 5 \mathrm {h r} ^ {2} \\ C _ {s} ^ {2} (1) = \frac {E \left[ S _ {1} ^ {2} \right] - E \left[ S _ {1} \right] ^ {2}}{E \left[ S _ {1} \right] ^ {2}} = \frac {4 0 . 0 5 - 2 6 . 0 1}{2 6 . 0 1} = 0. 5 4 0 \\ \end{array}
$$

# Traditional factory model

Y A similar analysis for the other four workstations yields these results

![](images/dc55e2f21e363fcf3b34a9cca0f2b54ee0f79a5c98bead4d2eb92cdc1a769736.jpg)

# Traditional factory model

V Definition of the Routing matrix to compute the SCV of arrivals in each workstation

$$
P = \left[ \begin{array}{c c c c c} 0 & \frac {0 . 0 6 4 + 0 . 0 9 6}{0 . 3 2} & 0 & 0 & 0 \\ \frac {0 . 0 6 4}{0 . 1 6} & 0 & \frac {0 . 0 9 6}{0 . 1 6} & 0 & 0 \\ \frac {0 . 0 6 4 + 0 . 0 9 6}{0 . 4 4} & 0 & 0 & \frac {0 . 1}{0 . 4 4} & \frac {0 . 0 8}{0 . 4 4} \\ 0 & 0 & \frac {0 . 0 8}{0 . 2 6} & 0 & \frac {0 . 1}{0 . 2 6} \\ 0 & 0 & \frac {0 . 1}{0 . 1 8} & \frac {0 . 0 8}{0 . 1 8} & 0 \end{array} \right] = \left[ \begin{array}{c c c c c} 0 & 0. 5 & 0 & 0 & 0 \\ 0. 4 & 0 & 0. 6 & 0 & 0 \\ 0. 3 6 3 6 & 0 & 0 & 0. 2 2 7 3 & 0. 1 8 1 8 \\ 0 & 0 & 0. 3 0 7 7 & 0 & 0. 3 8 4 6 \\ 0 & 0 & 0. 5 5 5 6 & 0. 4 4 4 4 & 0 \end{array} \right]
$$

# Traditional factory model

V Computation of SCV of arrivals in each workstation

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

V Performance for Workstation 1

$$
\begin{array}{l} C T (1) = \left(\frac {C _ {a} ^ {2} (1) + C _ {s} ^ {2} (1)}{2}\right) \left(\frac {u _ {1} ^ {\sqrt {6} - 1}}{2 \left(1 - u _ {1}\right)}\right) E \left[ T _ {s} (1) \right] + E \left[ T _ {s} (1) \right] \\ = \left(\frac {0 . 9 3 6 + 0 . 5 4 0}{2}\right) \left(\frac {0 . 8 1 6 ^ {1 . 4 4 9}}{0 . 3 6 8}\right) 5. 1 0 0 + 5. 1 0 0 = 1 2. 7 2 \mathrm {h r}. \\ \end{array}
$$

> By using Little's law, the WIP is 0.32*12.714 = 4.068 jobs

# Traditional factory model

Same analysis for the other workstations

![](images/ff24f6750579741dba4fd0ee0e6ce724c9e4b129f54f0b8f9ff17cb633bb4ca9.jpg)

The total WIP is 25.67 jobs   
> The total CT is 25.67/0.34 = 75.5 hours

# Cellular factory model

![](images/d84a2e76cb4996163e09578566e54487d554e986fcd3ab8b3ca611ec0aebb7a5.jpg)

> From the first table,it is easy to see that a two-group partitioning of the products is possible

>Job Types 1 and 2 in Group 1 produced by Cell 1   
>Job Types 3 and 4 in Group 2 produced in Cell 2

Both groups have Machine 3 requirements with workloads by group of 1.280 and 1.420, respectively, for Groups 1 and 2

> Since both of these cells require at least two machines of Type 3,an additional machine must be purchased to implement the disjoint cellular manufacturing approach

# Cellular factory model

V Obtained performance measures by repeating the computations of the traditional factory model

![](images/60db2a5d73ffab2317a1ce516451272516de5a3ce9653e910a895515fe7c3a52.jpg)

These results seem better, but the comparison is not fair since an extra machine had to be purchased to establish the cellular organization   
To appropriately compare the two factory organizational schemes, the performance measures of the traditional factory layout are recalculated using an additional machine for Workstation 3   
The recalculation yields a total system WiP of 20.578 for the traditional factory as compared to the total system WIP of 21.486 for the cellular factory

# Cellular factory model

One of the keys for cellular manufacturing is the reduction in processing times due to the similarities of jobs being processed on a machine   
》 For this example, we assume a 25% decrease in the processing time for Machine 3 for both technology groups   
The resulting performance measures for the cellular factory are

![](images/7ddcb466e2d5a51d088ca3a5a9f44d9877326905d72177b8fb20e47dfd66f03e.jpg)

V Total WIP = 19.633

# Conclusion

V This example illstrates that a group technology/cellular manufacturing organization of the factory can yield a cycle time reduction when implemented in a logical fashion only if there are resulting reductions in the setup and/or processing times   
The partitioning of the factory into several non-overlapping production cells is not the actual phenomena from which the improvements in the performance measures are gained

V The gains are mainly due to the improvements in production that can be associated with specialization: setup reductions, learning curve effects (reduced processing times), processing simplifications,and improved quality due to specialization

> In addition, the material handling/part transportation aspects of the factory may also be more specialized and certainly less travel distance will be realized in a cellular organization
