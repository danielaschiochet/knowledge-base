# Analysis and Management of Production System

# Lesson 5: Multiple-stage factory models

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Flow Variability

V Till now, our attention was on the analysis of a single workstation   
>The workstation impact on the output flow of jobs from the workstations was not considered as this information was not needed to study the performance of a single workstation   
V But the variability of a station has effects on the behaviour of the next Station on the line and, when the output from a WS becomes the input to the next one, this aspect can be no more neglected: this generates the so-called flow variability   
V Flow: transfer of a job or a part from one machine to the other

# Flow Variability

# Arrivals:

E[Ta] → mean time between two arrivals   
>c²a → squared coefficient of variation of the mean time between two arrivals

# V Process:

E[Tel → effective process time   
V c² → squared coefficient of variation of the effective process time   
E[Te] < E[Ta] → otherwise, the station would be overloaded

# Departures:

E[Td]→ mean time between two departures/releases   
c²d → squared coefficient of variation of the mean time between two departures

# Conservation of flow

> In the long run, the same number of units must depart the workstation as enter the workstation   
Otherwise,there would be a buildup of jobs in the workstation and the queue would grow infinitely as time extends to infinity   
Applying this conservation of flow concept, the mean arrival rate of jobs to a workstation operating under steady-state conditions equals the mean departure rate of jobs

$$
E [ T _ {a} ] = E [ T _ {d} ]
$$

# Variability of departures

V From previous equations, we see that in case of exponential systems (M/M/m model), the output process is probabilistically identical to the input process

$$
\mathbf {c _ {d}} ^ {2} = \mathbf {c _ {a}} ^ {2} = \mathbf {c _ {e}} ^ {2} = 1
$$

> For non-exponential systems, instead,itisa bit more involving toobtain the Cd² value

V If the WS is extremely busy, the distribution of time between departures is expected to be very close to the process time distribution, so that cd² should be similar to ce²   
> If the WS is lightly loaded, instead, the inter-departure time distribution should be similar to the inter-arrival time distribution,so that cd² should be similar to ca2

# Variability of departures

# High-usage station

![](images/467df6fbd6cd0060bcf1bae2daee44c9279706b22a6de777ab9e476932c1c376.jpg)

>Theflow variability out of a high-usage station is mainly determined by the process variability of the station itself

# Variability of departures

# Low-usage station

![](images/89d35bfd37647ace7ea525e85a063ff91ee9cf8c45f3750622e65770b95e601d.jpg)

>The flow variability out of a low-usage station is mainly determined by the arrival variability

# Variability of departures

Whitt equation

$$
C _ {d} ^ {2} (G / G / 1) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} C _ {s} ^ {2}
$$

$$
C _ {d} ^ {2} (G / G / c) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} \frac {C _ {s} ^ {2} + \sqrt {c} - 1}{\sqrt {c}}
$$

> u~1 : the station is almost always busy, thus c²d~c²s   
> u~0 : the station is almost never busy, thus c²d~c²a a

# Example

For a single server workstation, the inter-arrival distribution parameters are E[Ta] = 20 min and C²a = 1/2.The service time distribution parameters are E[T] = 15 min and C²= 1/3   
V Then λ= 3/hr and μ = 4/hr, and the system utilization factor U= ^ / = 3/4   
V The squared coeffcient of variation of the inter-departure times is given by

$$
C _ {d} ^ {2} = \left(1 - \left(\frac {3}{4}\right) ^ {2}\right) \frac {1}{2} + \left(\frac {3}{4}\right) ^ {2} \frac {1}{3} = \frac {1 3}{3 2} = 0. 4 0 6 2 5
$$

# Exercises

> A workstation has a workload that uses 85% of its single machine capacity. Arrivals to the workstation are exponentially distributed and the service time SCV is 1.5. What is the estimated SCV of the departure stream?   
A two-machine workstation has a utilization factor of 8o%. The arrival SCV is 2.0 and the service time follows an Erlang-2 distribution. What is the estimated SCV of the departure stream?

# Solution (1)

Y A workstation has a workload that uses 85% of its single machine capacity. Arrivals to the workstation are exponentially distributed and the service time SCV is 1.5. What is the estimated SCV of the departure stream?

$$
\mathsf {G} / \mathsf {G} / 1
$$

$$
\mathsf {u} = 0, 8 5
$$

$$
c _ {s} ^ {2} = 1, 5
$$

$$
c _ {a} ^ {2} = 1
$$

$$
c _ {d} ^ {2} = \left(1 - u ^ {2}\right) \cdot c _ {a} ^ {2} + u ^ {2} \cdot c _ {s} ^ {2} = \left(1 - 0, 8 5 ^ {2}\right) \cdot 1 + 0, 8 5 ^ {2} \cdot 1, 5 = 1, 3 6
$$

# Solution (2)

A two-machine workstation has a utilization factor of 8o%. The arrival SCV is 2.0 and the service time follows an Erlang-2 distribution. What is the estimated SCV of the departure stream?

$$
\mathrm {G / G / 2}
$$

$$
u = 0, 8 0
$$

$$
c _ {S} ^ {2} = 0, 5
$$

$$
c _ {a} ^ {2} = 2
$$

$$
\mathsf {c} = 2
$$

$$
c _ {d} ^ {2} = \left(1 - u ^ {2}\right) \cdot c _ {a} ^ {2} + u ^ {2} \cdot \frac {c _ {s} ^ {2} + \sqrt {c} - 1}{\sqrt {c}} = \left(1 - 0, 8 ^ {2}\right) \cdot 2 + 0, 8 ^ {2} \cdot \frac {0 , 5 + \sqrt {2} - 1}{\sqrt {2}} = 1, 1 3 4
$$

# Serial system

![](images/e2701c5b20fef6495ba795311d8ab7c61a628bb1ae563663aa0e1251a0d12bea.jpg)

> In a serial ine having a constant flow with no losses or reworks,anything that comes out of a station enters the following one   
V This system is treated as a series of G/G/c queues with specified service parameters (E[T()], C², (), Ci) for each workstation i   
V Because of the serial nature of the system, the arrival stream for workstation iis the departure stream from workstation i-1

$$
\triangleright \mathrm {C} ^ {2} _ {a} (i) = \mathrm {C} ^ {2} _ {d} (i - 1) \text {f o r} i = 2, \dots n
$$

> In addition,the initial workstation inter-arrval time distribution parameters E[Ta(1)], C²a (1) are assumed known

# Serial system

> If we were limited to exponential processes, the system could be modeled using the state-diagram approach   
> But the diagram approach becomes intractable even for small networks because of dimensionality problems of the state space   
The approach to modeling the network composed of M/M/c systems is to model each individual node as if it were independent of all other nodes using as input to each node the same arrival process as to the first node

# Example

> Patients arive to the emergency room according to Poisson process (i.e., with exponential inter-arrival times) with a mean rate of 4 per hour   
V When they arrive, there is a single clerk who takes their information; this process takes an exponentially distributed length of time with an average of 4 minutes per patient   
V There is a triage nurse who next sees the patient; the nurse takes an exponentially distributed length of time averaging 10 minutes per patient   
Finally, one of two doctors sees the patient and each doctor takes an exponentially distributed amount of time with each patient averaging 24 minutes with the doctor   
> We would like to know the average number of patients within the facility at any one time and the average time that a patient spends in the emergency room

# Example

V The emergency room system is composed of an M/M/1 system feding a ·/M/1 system feeding a ·/M/2 system   
V Because of the property that M/M/c systems have exponential inter-departure times,the second and third nodes are an M/M/1 and M/M/2 system with an arrival rate of 4 per hour   
The system can be analyzed as three independent single node systems   
The first node has a utilization factor of u,= 4/15 and thus the average number of patients in the first node is WiP(1) = 4/11.   
The second node has a utilization factor of uz= 2/3 yielding WiP(2) = 2

# Example

> For the third node,we firstfind the time spent waiting for the doctor, i.e., CTq(3)= 42.67 min since U3= 0.8   
> Adding the doctor's time to the wait time yields the time spent in third node as CT(3)= 1.11 hr   
V Applying Litle's Law gives the average number of patients at the node as WIP(3) = 4.44   
> Thus, the total number in the emergency room is WiP = 4/11 + 2 + 4.44 = 6.8   
> Applying Litle's Law one more time, yields the average value for the total time a patient spends in the emergency room as CTs = 1.7 hr

# Generalization

V The analysis approach used in the Example is exact only under the assumptions of infinite capacity nodes and exponential distributions for inter-arrivals and processing times, but it provides the motivation for approximation schemes when these assumptions do not hold   
The analysis approach for general systems is based on the concept that a system's performance can be adequately approximated by separating the system into individual workstations   
The performance characteristics of the individual workstations are computed separately and then these results recombined for the total system behavior   
V This decomposition approach is fundamental to the approximation of general network configurations

# Example

Consider a three-workstation factory with serial flow   
> Each workstation has a single machine with the service time distribution parameters as listed in the table   
The inter-arrival time distribution for jobs to the factory has a mean of 15 minutes or a mean rate of 4 jobs per hour, and a squared coefficient of variation of 0.75   
The system mean work-in-process,cycle time,and throughput are desired

![](images/7d9e2b23cc6e06257d35e573c36d5bfef6a01943d1bafd6a259f3196c87ef223.jpg)

> Since arrivals to the system occur at the first workstation, E[Ta(1)] = 15 min yielding a utilization factor of u = E[Ts(1)]/E[Ta(1)] = 0.8   
V For the first workstation we have the following results

$$
C T (1) = \left(\frac {C _ {a} ^ {2} (1) + C _ {s} ^ {2} (1)}{2}\right) \left(\frac {u _ {1}}{1 - u _ {1}}\right) E [ T _ {s} (1) ] + E [ T _ {s} (1) ]
$$

$$
\begin{array}{l} = \left(\frac {0 . 7 5 + 2 . 0}{2}\right) \frac {0 . 8}{0 . 2} (1 2 \min ) + 1 2 \min \\ = 7 8 \min = 1. 3 \mathrm {h r} \\ \end{array}
$$

$$
\begin{array}{l} C _ {d} ^ {2} (1) = \left(1 - u _ {1} ^ {2}\right) C _ {a} ^ {2} (1) + u _ {1} ^ {2} C _ {s} ^ {2} (1) \\ = (1 - 0. 8 ^ {2}) 0. 7 5 + 0. 8 ^ {2} (2. 0) = 1. 5 5 \\ \end{array}
$$

$$
W I P (1) = C T (1) \times \frac {1}{E \left[ T _ {a} (1) \right]} = \frac {1 . 3 \mathrm {h r}}{0 . 2 5 \mathrm {h r}} = 5. 2
$$

# Example

V Because this is a pure serial network, the arrival rate and throughput rate will be the same for each workstation   
V Thus,the utilization factors for the other two workstations are Uz = E[T(2)/E[T(1)]=0.6 and U3= E[T(3)]/E[Ta(1)]= 0.88

$$
C T (2) = \left(\frac {1 . 5 5 + 0 . 7}{2}\right) \frac {0 . 6}{0 . 4} (0. 1 5 \mathrm {h r}) + 0. 1 5 \mathrm {h r} = 0. 4 0 3 \mathrm {h r}
$$

$$
C _ {d} ^ {2} (2) = \left(1 - 0. 6 ^ {2}\right) 1. 5 5 + 0. 6 ^ {2} (0. 7) = 1. 2 4 4
$$

$$
W I P (2) = C T (2) / E \left[ T _ {a} (1) \right] = 1. 6 1 3 \quad \text {a n d}
$$

$$
C T (3) = \left(\frac {1 . 2 4 4 + 1 . 0}{2}\right) \frac {0 . 8 8}{0 . 1 2} (0. 2 2 \mathrm {h r}) + 0. 2 2 \mathrm {h r} = 2. 0 3 0 \mathrm {h r}
$$

$$
C _ {d} ^ {2} (3) = \left(1 - 0. 8 8 ^ {2}\right) 1. 2 4 4 + 0. 8 8 ^ {2} (1. 0) = 1. 0 5 5
$$

$$
W I P _ {s} (3) = C T (3) / E [ T _ {a} (1) ] = 8. 1 2 1.
$$

# Example

> Finally, the total factory performance characteristics for this serial system are

$$
W I P _ {s} = 5. 2 0 0 + 1. 6 1 3 + 8. 1 2 1 = 1 4. 9 3 3 \mathrm {j o b s}
$$

$$
t h _ {s} = \frac {1}{E [ T _ {a} (1) ]} = 4 / \mathrm {h r}
$$

$$
C T _ {s} = \frac {W I P _ {s}}{t h _ {s}} = 3. 7 3 3 \mathrm {h r}.
$$

# Exercise 1

V Find the system performance measures of CTs,WIPs,and throughput for a pure serial system consisting of three single capacity workstations   
> The arrival rate to the system is 3 jobs per hour, with the inter-arrival time being exponentially distributed   
The processing time data are:

![](images/a0598e8802e092f5966e287845e433f040fe481954ce6f07b9fb7eff7e29b005.jpg)

# Exercise 1 Solution

$$
\begin{array}{l} E \left[ T _ {a} \right] = 1 / 3 \mathrm {h r} \\ c _ {a} ^ {2} = 1 \\ \lambda_ {a} = 3 \mathrm {u / h r} \\ \end{array}
$$

WS1

$$
E [ T _ {e} (1) ] = 0, 2 5 \mathrm {h r}
$$

$$
c _ {e} ^ {2} (1) = 4
$$

$$
u _ {1} = \frac {0 , 2 5}{1 / 3} = 0, 7 5
$$

$$
C T _ {q 1} = \frac {c _ {a} {} ^ {2} + c _ {\mathrm {e} 1} {} ^ {2}}{2} \cdot \frac {u}{1 - u} \cdot \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (1) ] = 1, 8 7 5 \mathrm {h}
$$

$$
\mathrm {C T} _ {1} = \mathrm {C T} _ {\mathrm {q} 1} + \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (1) ] = 2, 1 2 5 \mathrm {h}
$$

$$
\mathrm {W I P} _ {1} = \mathrm {C T} _ {1} \cdot \lambda_ {\mathrm {a}} = 6, 3 7 5
$$

$$
c _ {d} ^ {2} (1) = u ^ {2} \cdot c _ {\mathrm {e}} ^ {2} + (1 - u ^ {2}) \cdot c _ {a} ^ {2} = 2, 6 8 = c _ {a 2} ^ {2}
$$

WS2

$$
E [ T _ {e} (2) ] = 0, 2 9 \mathrm {h r}
$$

$$
c _ {e} ^ {2} (2) = 3
$$

$$
u _ {2} = \frac {0 , 2 9}{1 / 3} = 0, 8 7
$$

$$
C T _ {q 2} = \frac {c _ {a} {} ^ {2} + c _ {e 2} {} ^ {2}}{2} \cdot \frac {u}{1 - u} \cdot \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (2) ] = 5, 5 1 \mathrm {h}
$$

$$
\mathrm {C T} _ {2} = \mathrm {C T} _ {\mathrm {q} 2} + \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (2) ] = 5, 8 0 \mathrm {h}
$$

$$
\mathrm {W I P} _ {2} = \mathrm {C T} _ {2} \cdot \lambda_ {\mathrm {a}} = 1 7, 4
$$

$$
c _ {d} ^ {2} (2) = u ^ {2} \cdot c _ {\mathrm {e}} ^ {2} + (1 - u ^ {2}) \cdot c _ {a} ^ {2} = 2, 9 2 = c _ {a 3} ^ {2}
$$

![](images/8c0da644cf74576c9141ef57bda912082997f470b658d1af1f8a512c58420343.jpg)

WS3

$$
E [ T _ {e} (3) ] = 0, 3 0 \mathrm {h r}
$$

$$
c _ {e} ^ {2} (3) = 2
$$

$$
u _ {3} = \frac {0 , 3 0}{1 / 3} = 0, 9 0
$$

$$
C T _ {q 3} = \frac {c _ {a} ^ {2} + c _ {\mathrm {e 3}} ^ {2}}{2} \cdot \frac {u}{1 - u} \cdot
$$

$$
\operatorname {E} \left[ \mathrm {T} _ {\mathrm {e}} (3) \right] = 6, 6 4 \mathrm {h}
$$

$$
\mathrm {C T} _ {3} = \mathrm {C T} _ {\mathrm {q 3}} + \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (3) ] = 6, 9 4 \mathrm {h}
$$

$$
\mathrm {W I P} _ {3} = \mathrm {C T} _ {3} \cdot \lambda_ {\mathrm {a}} = 2 0, 8 3
$$

$$
C T _ {T O T} = 1 4, 8 6 5
$$

$$
W I P _ {T O T} = 4 7
$$

# Exercise 2

V Find the system performance measures of CTs, WiPs, and throughput for a three-workstation pure serial system   
Y The arrval rate to the system is one job every two hours with an SCV of 2.0.   
V The machine data for the three single-capacity workstations are given below.

![](images/c1b11db2cdfdb13af6eddcf4a424dbbe273d49f566c084a538e7877a94ffc8b2.jpg)

# Exercise 2- Solution (1)

$$
\begin{array}{l} E [ T _ {a} ] = 2 \mathsf {h} \\ c _ {a} ^ {2} = 2 \\ \lambda_ {a} = 0, 5 \mathrm {u / h} \\ \end{array}
$$

WS1

$$
\begin{array}{l} \operatorname {E} \left[ \mathrm {T} _ {\mathrm {s}} (2) \right] = 1, 5 \mathrm {h}. \\ c _ {s 1} ^ {2} = 0, 7 5 \\ \mathbf {a} = 0, 8 5 \\ E _ {1} [ R ] = 2 h \\ c _ {1} ^ {2} [ R ] = 1, 3 \\ \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (1) ] = \frac {\mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (1) ]}{a} = 1, 8 8 \mathrm {h} \\ c _ {\mathrm {e} 1} ^ {2} = c _ {\mathrm {s} 1} ^ {2} + \frac {(1 + c _ {1} ^ {2} [ R ]) a \cdot (1 - a) \cdot E _ {1} [ R ]}{\mathrm {E} [ \mathrm {T} _ {S} (1) ]} = 1, 1 2 \\ u _ {1} = \frac {\mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (1) ]}{E [ T _ {a} ]} = 0, 9 4 \\ \end{array}
$$

$$
\begin{array}{l} c _ {d} ^ {2} (1) = u ^ {2} \cdot c _ {\mathrm {e}} ^ {2} + (1 - u ^ {2}) \cdot c _ {a} ^ {2} = 1, 2 2 \\ C T _ {q 1} = \frac {c _ {a} {} ^ {2} + c _ {\mathrm {e 1}} {} ^ {2}}{2} \cdot \frac {u}{1 - u} \cdot \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (1) ] = 4 5, 9 4 \mathrm {h} \\ \mathbf {C T _ {1}} = \mathbf {C T _ {q 1}} + \mathbf {E} [ \mathbf {T _ {e}} (\mathbf {1}) ] = 4 7, 8 3 \mathrm {h} \\ W I P _ {1} = C T _ {1} \cdot \lambda_ {a} = 2 4 \\ \end{array}
$$

# Exercise 2- Solution (2)

$$
E [ T _ {a} ] = 2 \mathsf {h}
$$

$$
c _ {a 2} ^ {2} = c _ {d 1} ^ {2} = 1, 2 2
$$

$$
\lambda_ {a} = 0, 5 \mathrm {u / h}
$$

WS2

$$
\operatorname {E} \left[ \mathrm {T} _ {s} (1) \right] = 1, 6 \mathrm {h}.
$$

$$
c _ {s 2} ^ {2} = 1, 5 0
$$

$$
a = 0, 9 0
$$

$$
E _ {2} [ R ] = 2, 5 h
$$

$$
c _ {2} ^ {2} [ R ] = 1, 5
$$

$$
\mathrm {E} \left[ \mathrm {T} _ {\mathrm {e}} (2) \right] = \frac {\mathrm {E} \left[ \mathrm {T} _ {\mathrm {s}} (2) \right]}{a} = 1, 7 8 \mathrm {h}
$$

$$
\mathsf {c} _ {\mathrm {e 2}} ^ {2} = \mathsf {c} _ {\mathrm {s 2}} ^ {2} + \frac {\left(1 + c _ {2} ^ {2} [ R ]\right) a \cdot (1 - a) \cdot E _ {2} [ R ]}{\operatorname {E} [ \mathrm {T} _ {\mathrm {s}} (2) ]} = 1, 8 5
$$

$$
u _ {1} = \frac {\mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (1) ]}{E [ T _ {a} ]} = 0, 8 9
$$

$$
c _ {d} ^ {2} (2) = u ^ {2} \cdot c _ {\mathrm {e}} ^ {2} + (1 - u ^ {2}) \cdot c _ {a} ^ {2} = 1, 7 1
$$

$$
C T _ {q 2} = \frac {c _ {a} ^ {2} + c _ {\mathrm {e} 2} ^ {2}}{2} \cdot \frac {u}{1 - u} \cdot \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (2) ] = 2 2, 1 0 \mathrm {h}
$$

$$
\mathbf {C T} _ {2} = \mathbf {C T} _ {\mathbf {q} 2} + \mathbf {E} [ \mathbf {T} _ {\mathbf {e}} (2) ] = 2 3, 8 8 \mathrm {h}
$$

$$
W I P _ {2} = C T _ {2} \cdot \lambda_ {a} = 1 2
$$

# Exercise 2 - Solution (3)

$$
E [ T _ {a} ] = 2 \mathsf {h}
$$

$$
c _ {a 3} ^ {2} = c _ {d 2} ^ {2} = 1, 7 1
$$

$$
\lambda_ {a} = 0, 5 \mathrm {u / h}
$$

WS3

$$
\operatorname {E} \left[ \mathrm {T} _ {\mathrm {s}} (3) \right] = 1, 7 \mathrm {h}.
$$

$$
c _ {s 3} ^ {2} = 2, 0 0
$$

$$
a = 0, 9 0
$$

$$
E _ {3} [ R ] = 3, 0 h
$$

$$
c _ {3} ^ {2} [ R ] = 1, 7 5
$$

$$
\mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (3) ] = \frac {\mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (3) ]}{a} = 1, 8 9 \mathrm {h}
$$

$$
\mathsf {c} _ {\mathrm {e 3}} ^ {2} = \mathsf {c} _ {\mathrm {s 3}} ^ {2} + \frac {(1 + c _ {3} ^ {2} [ R ]) a \cdot (1 - a) \cdot E _ {3} [ R ]}{\mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (3) ]} = 2, 4 3 6
$$

$$
u _ {3} = \frac {\mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (3) ]}{E [ T _ {a} ]} = 0, 9 4 5
$$

$$
C T _ {q 3} = \frac {c _ {a} ^ {2} + c _ {\mathrm {e 3}} ^ {2}}{2} \cdot \frac {u}{1 - u} \cdot \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (3) ] = 3 5, 2 6 \mathrm {h}
$$

$$
\mathbf {C T} _ {3} = \mathbf {C T} _ {\mathbf {q} 3} + \mathbf {E} [ \mathbf {T} _ {\mathbf {e}} (3) ] = 3 7, 1 5 \mathrm {h}
$$

$$
W I P _ {3} = C T _ {3} \cdot \lambda_ {a} = 1 9
$$

![](images/ccbb4b75df669dc9a98241bea16077fa4e571a56738c6033ebc1ee6c68a901d7.jpg)

$$
C T _ {T O T} = 1 0 8, 8 6
$$

$$
W I P _ {T O T} = 5 5
$$

# Exercise 3

> Items arrive with interarrival times E[Ta]= 21 min,exponentially distributed   
Let's consider the following stations:

WSA:E[T:(a)] = 20 min (exponentially distributed)   
WSB:E[Ts(b)]= 20 min, σs= 5

The product X needs to be processed by both WSA and WSB   
V Having the possibility to choose the sequence, is it better to put WSA before WSB or WSB before WSA in the line?   
> Motivate the answer by computing total CT and WIP on the line in both cases

# Exercise 3 - Solution (1)

![](images/1e876523097632dc60bd3fd83109bddb79f899d94db139af20b871f6027b49ad.jpg)

# Exercise 3 - Solution (2)

E[Ta] = 21 min

入a 21 1 u/min

M/G/1

WSB

Cd(a)=Ca(b)

𝜆a(a)=λa(b)

G/M/1

WSA

E[Te(b)] = 20 min

E[Te(a)] = 20 min

$$
\sigma_ {e} = 5
$$

$$
c _ {\mathrm {e}} ^ {2} = 1
$$

$$
c _ {e} = \frac {\sigma_ {e}}{E [ T _ {e} (b) ]} = \frac {5}{2 0} = 0, 2 5
$$

$$
u _ {a} = \frac {2 0}{2 1} = 0, 9 5 2
$$

$$
u _ {b} = \frac {2 0}{2 1} = 0, 9 5 2
$$

$$
W I P (a) = \frac {u}{1 - u} = 1 9, 8
$$

$$
\mathrm {C T _ {q} (b)} = \frac {c _ {a +} ^ {2} c _ {e} {} ^ {2}}{2} \cdot \frac {\mathrm {u}}{1 - \mathrm {u}} \cdot E [ T _ {e} (b) ] = 2 1 0 \min
$$

$$
\mathrm {C T} _ {\mathrm {q}} (\mathrm {a}) = \frac {c _ {a +} ^ {2} c _ {\mathrm {e}} ^ {2}}{2} \cdot \frac {\mathrm {u}}{1 - \mathrm {u}} \cdot E [ T _ {e} (a) ] = 2 3 0 \mathrm {m i n}
$$

$$
\mathrm {W I P} _ {\mathrm {q}} (\mathrm {b}) = \lambda_ {b} \cdot \mathrm {C T} _ {\mathrm {q}} (\mathrm {b}) = 1 0
$$

$$
\mathrm {W I P} _ {\mathrm {q}} (\mathrm {a}) = \lambda_ {a} \cdot \mathrm {C T} _ {\mathrm {q}} (\mathrm {a}) = 1 1
$$

$$
\mathrm {C T (b)} = \mathrm {C T _ {q} (b)} + E [ T _ {e} (b) ] = 2 3 0 \mathrm {m i n}
$$

$$
\mathrm {C T} (\mathsf {a}) = \mathrm {C T} _ {\mathsf {q}} (\mathsf {a}) + E [ T _ {e} (\mathsf {a}) ] = 2 5 0 \min
$$

$$
\operatorname {W I P} (\mathsf {b}) = \lambda_ {b} \cdot \operatorname {C T} (\mathsf {b}) = 1 0, 9 5
$$

$$
\mathsf {W I P} (\mathsf {b}) = \lambda_ {a} \cdot \mathsf {C T} (\mathsf {a}) = 1 2
$$

$$
c _ {d} ^ {2} (a) = u ^ {2} \cdot c _ {\mathrm {e}} ^ {2} + (1 - u ^ {2}) \cdot c _ {a} ^ {2} = 0, 1 5
$$

BETTER PERFORMANCE

$$
C T _ {T O T} = 2 3 0 + 2 5 0 = 4 8 0 \min
$$

$$
\mathbf {W I P} _ {\mathrm {T O T}} = \mathbf {1 0}, 9 5 + \mathbf {1 2} = 2 3
$$

# Nonserial Network Models

> Many production systems have more than one inflow point into the production system.   
> Products that may have been found defective or that have broken may be sent back to the manufacturing facility to be reworked

> These units will not necessarily enter the production line at the same point as a new job   
> If a defect is found during inspection after partially completing production, it may be sent to a rework station and then re-enter the production sequence at the appropriate point

# Nonserial Network Models

To study factory structures that are more realistic than pure serial systems, two additional structures must be studied to compute the squared coefficients of the various streams of jobs within the factory

merging of streams entering a workstation   
V spliting of output streams that come from a single workstation but are routed to more than one workstation

V These two processes,are firstly addressed separately, and then combined for a general network model

# Merging Inflow Streams

When multiple inflow streams arrive at a workstation with difering interarrival time distributions, the composite inter-arrival time distribution parameters need be computed   
V The process of merging inflow streams is technically called a superposition of the individual inter-arrval processes   
V It is assumed that the individual input streams are independent of one another and that each has independent and identically distributed interarrival times

each of these input streams is said to be a renewal process

![](images/e348b652bf4d5c0d34f853243e8b5d5e13ac3762c9b480fc97e466347564960b.jpg)

# Merging Inflow Streams

Consider an arrival stream that is formed by merging n individual arrival processes   
The individual streams have mean arrival rates given by >; = 1/E[Ti] and squared coefcients of variation denoted by C2; for i= 1.,., n   
The mean arival rate, ^a, and the squared coefficient of variation, C²a, for a renewal process used to approximate the merged arival process are given by:

![](images/df4ef5ce05e340d8a5ce9b4ccb708c7bd32138c1ee8a32c31415bec35ec2a1f1.jpg)

$$
\lambda_ {a} = \sum_ {i = 1} ^ {n} \lambda_ {i} = \sum_ {i = 1} ^ {n} \frac {1}{E [ T _ {i} ]}
$$

$$
C _ {a} ^ {2} = \sum_ {i = 1} ^ {n} \frac {\lambda_ {i}}{\lambda_ {a}} C _ {i} ^ {2}.
$$

# Example

V An automated lubricating facility is located in the center of a manufacturing plant   
Y Arrivals of parts needing lubrication come from three sources: manufactured parts needing assembly, defective parts that have been disassembled and willbe returned for reassembly, and parts coming from a sister manufacturing facility in another part of the town   
The three arrval streams have been analyzed separately

>The mean arrival rates for the three streams are given by the vector (1,A2λ3) = (13.2/hr, 3.6/r,6.0/hr)   
>The squared coeficients of variation for the three inflow streams are (C2, C22, C²3) = (5.0, 3.0, 2.2)

Find the inter-arrival time distribution parameters

# Example

V The total inflow into the workstation is the sum of the individual inflows so that ^a = 22.8/hr   
V The relative weights, 13.2/22.8, 3.6/22.8,and 6.0/22.8,are thus used to determine the composite inflow stream's squared coefficient of variation as

$$
C _ {a} ^ {2} = \frac {1 3 . 2}{2 2 . 8} 5. 0 + \frac {3 . 6}{2 2 . 8} 3. 0 + \frac {6 . 0}{2 2 . 8} 2. 2 = 3. 9 4 7
$$

》 To compute the mean and standard deviation of the inter-arrival times, remember that mean rates and mean times are reciprocals:

$$
\begin{array}{l} E \left[ T _ {a} \right] = \frac {1}{2 2 . 8} \mathrm {h r} = 2. 6 3 \mathrm {m i n}, \quad \text {a n d} \\ V [ T _ {a} ] = 3. 9 4 7 (2. 6 3 ^ {2}) = 2 7. 3 0 \mathrm {m i n} ^ {2} \\ \end{array}
$$

> Find the inter-arrival time distribution parameters for the following system:

![](images/445fe41313dd461b37ad98fd62f706d9cdad30c6b874df071cc222265ef14089.jpg)

# Solution

![](images/15af0aefc85e6f8341db2c68f9b1a46d5dcff04de7a3908a54088dbe000ac346.jpg)

$$
\lambda_ {\mathrm {a}} = \sum_ {n} \lambda_ {\mathrm {i}} = 1 + 3 = 4 j / h
$$

$$
c _ {a} ^ {2} = \sum_ {n} \frac {\lambda_ {\mathrm {i}}}{\lambda_ {\mathrm {a}}} \cdot c _ {\mathrm {i}} = \frac {1}{4} \cdot 1. 3 6 5 + \frac {3}{4} \cdot 2. 0 9 5 = 1. 9 1
$$

# Splitting of Departure Stream

> Jobs that exit from a workstation can be transferred to different workstations based on several possibilities   
> Multiple products can be made by specializing a partially processed product   
The processing sequences can be identical through some steps,and then the items are branched to their unique completion workstations or sequence of workstations   
After a quality control test, good items continue their normal route, while bad items are reworked or corrected at a different workstation before continuing normal processing

# Splitting of Departure Stream

Consider a departure stream from a specified workstation with a mean inter-departure time and coeficient of variation given by E[Tal and C²2d, respectively   
When a job departs from the specified workstation,there is a probability, p, that the job willbe routed to a target workstation   
If there are no other arriving streams to the target workstation, then the mean inter-arrival time and squared coefficient of variation for arrivals to target workstation are given by

$$
E [ T _ {a} ] = \frac {E [ T _ {d} ]}{p} \qquad \mathrm {o r} \qquad \lambda_ {a} = p \lambda_ {d}
$$

$$
C _ {a} ^ {2} = p C _ {d} ^ {2} + 1 - p.
$$

> The fifth workstation within a manufacturing facility performs a quality control check on partially manufactured items   
V Parts receive an unqualified pass from the inspector with probability 0.8 and they are then sent to Workstation 6 to continue the manufacturing process   
V Approximately 18% of the time, a part has a partial pass of the quality check and is sent to Workstation 10 for rework   
V And approximately 2% of the time, a part completely fails the test and is sent to the hazardous waste station for disposal which is designated as Workstation 99   
V The throughput rate for Workstation 5 is 7 jobs per hour and the coefficient of variation for the inter-departure times is 3

![](images/527519f3e0e90697c104a57f5d1d90e00550ac0c3e32d5666a5e4f874c853be0.jpg)

# The results are the following

(as a check, the arrival rates can be summed and they must equal the departure rate from the original stream before it was split)

$$
\lambda_ {a} (5, 6) = 0. 8 \times 7 = 5. 6 / \mathrm {h r}
$$

$$
C _ {a} ^ {2} (5, 6) = 0. 8 \times 3 + 0. 2 = 2. 6
$$

$$
\lambda_ {a} (5, 1 0) = 0. 1 8 \times 7 = 1. 2 6 / \mathrm {h r}
$$

$$
C _ {a} ^ {2} (5, 1 0) = 0. 1 8 \times 3 + 0. 8 2 = 1. 3 6
$$

$$
\lambda_ {a} (5, 9 9) = 0. 0 2 \times 7 = 0. 1 4 / \mathrm {h r}
$$

$$
C _ {a} ^ {2} (5, 9 9) = 0. 0 2 \times 3 + 0. 9 8 = 1. 0 4.
$$

> Analyze the network reported in the figure and find the arrival parameters at workstations 2, 3, and 4

![](images/a3698a28ff368332e06f023ab9f547123f5094338227de22f2067f881f5b1214.jpg)

$$
\lambda_ {a} = p \lambda_ {d}
$$

$$
C _ {a} ^ {2} = p C _ {d} ^ {2} + 1 - p
$$

$$
\lambda_ {a} = \sum_ {i = 1} ^ {n} \lambda_ {i}
$$

$$
C _ {a} ^ {2} = \sum_ {i = 1} ^ {n} \frac {\lambda_ {i}}{\lambda_ {a}} C _ {i} ^ {2}
$$

$$
C _ {d} ^ {2} (G / G / 1) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} C _ {s} ^ {2}
$$

> Workstations 2: merging of two inputflows (one external and one split from workstation 1) and computation of departure variability

$$
\begin{array}{l} \lambda_ {a} = p \lambda_ {d} \\ C _ {a} ^ {2} = p C _ {d} ^ {2} + 1 - p \\ \end{array}
$$

![](images/4b3b391f35c9a9392056afb588415ef3b2dd64ea84884fa7850320a551ae62c8.jpg)

$$
\lambda_ {a} = \sum_ {i = 1} ^ {n} \lambda_ {i}
$$

$$
C _ {a} ^ {2} = \sum_ {i = 1} ^ {n} \frac {\lambda_ {i}}{\lambda_ {a}} C _ {i} ^ {2}
$$

$$
\begin{array}{l} \lambda (2) = 2 + 3 = 5 \mathrm {j} / \mathrm {h} \\ C _ {a} ^ {2} (2) = 2 / 5 * 1 + 3 / 5 * 2 = 1. 6 \\ C ^ {2} _ {d} (2) = (1 - 0. 8 ^ {2}) ^ {*} 1. 6 + 0. 8 ^ {2} * 1 = 1. 2 2 \\ C _ {d} ^ {2} (G / G / 1) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} C _ {s} ^ {2} \\ \end{array}
$$

# Solution

> Workstations 3 analysis: only one flow split from workstation 2 and departure variability computation

$$
\begin{array}{l} \lambda_ {a} = p \lambda_ {d} \\ C _ {a} ^ {2} = p C _ {d} ^ {2} + 1 - p \\ \end{array}
$$

![](images/be9607925d5a5c5bfca560bd9aaf684e62e3215aa6afac66360cab9303916e77.jpg)

$$
\begin{array}{l} \lambda (3) = 3 \mathrm {j / h} \\ \mathrm {C} _ {\mathrm {a}} ^ {2} (3) = 2 \\ C _ {d} ^ {2} (3) = (1 - 0. 8 ^ {2}) ^ {*} 2 + 0. 8 ^ {2 *} 1 = 1. 3 6 \\ \end{array}
$$

$$
C _ {d} ^ {2} (G / G / 1) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} C _ {s} ^ {2}
$$

Workstations 4 analysis: merging two input flows

![](images/2a60150b56c9af53d258275a93e043cf3e4050ee9d14f206d64ae8f748be7aed.jpg)

$$
\lambda_ {a} = \sum_ {i = 1} ^ {n} \lambda_ {i} \quad C _ {a} ^ {2} = \sum_ {i = 1} ^ {n} \frac {\lambda_ {i}}{\lambda_ {a}} C _ {i} ^ {2}
$$

$$
\lambda (4) = 3 + 5 = 8 \mathrm {j / h}
$$

$$
\mathrm {C} _ {\mathrm {a}} ^ {2} (4) = 5 / 8 ^ {*} 1. 2 2 + 3 / 8 ^ {*} 1. 3 6 = 1. 2 7
$$

# General Network Approximation Model

V To address a general factory network connection topology, the possibilities of external flows into any one of the workstations must be considered along with job branching for rework purposes,splitting of the output from a workstation to different next workstations, etc.

>Workstation inflows can come from a variety of sources, external as well as other workstations within the factory,and this is handled by the flow merging mechanism   
> Probabilistic branching of workstation outflow requires departure stream splitting mechanics

Since there is no longer sequential flows, parameter dependencies are also not sequential so that equations relating the parameters will have to be solved simultaneously instead of sequentially

# General Network Approximation Model

![](images/133d38a4573756eb7629f1dedf3580b150abdc0449c4323c32057e16735309f4.jpg)

V With a non-serial network,determining the arrival stream characteristics is more complicated than for the serial systems   
> Since the flow rate into Workstation 1 is not known as yet, the inflow into Workstation 2 cannot be computed directly   
V The resolution requires that all of the flow rates are computed simultaneously   
The problem can be solved by means of a system of linear equations

$$
\lambda_ {1} = \gamma + \beta \lambda_ {2},
$$

$$
\lambda_ {2} = \lambda_ {1} + \alpha \lambda_ {2},
$$

# General Network Approximation Model

The parameters α ,β ,Y are all known data   
V This linear system rearranged in terms of the unknowns on the left side of the equality is

$$
\begin{array}{l} \lambda_ {1} - \beta \lambda_ {2} = \gamma , \\ - \lambda_ {1} + (1 - \alpha) \lambda_ {2} = 0. \\ \end{array}
$$

The solution to this system can be written in matrix form as

$$
\left( \begin{array}{c} \lambda_ {1} \\ \lambda_ {2} \end{array} \right) = \left( \begin{array}{c c} 1 & - \beta \\ - 1 & 1 - \alpha \end{array} \right) ^ {- 1} \left( \begin{array}{c} \gamma \\ 0 \end{array} \right)
$$

# General Network Approximation Model

V Consider a network consisting of workstations numbered from 1 to n   
V The switching rule for the network is defined by an nxn matrix P= (pij), where pi,j is the probability that an arbitrary job leaving Workstation i will be routed directly to Workstation j   
The matrix Pis called the routing matrix for the network   
Row iof the routing matrix consists of the probabilities relating to the splitting of the outflow from Workstation iinto the various resultant successor Workstations j   
V The jth column of the matrix represents the probabilities that jobs leaving the various workstations go to Workstation j

# General Network Approximation Model

Define γi as the external inflow rate and Xias the total inflow rate into Workstation i   
The total rate into Workstation imust satisfy the following equation:

$$
\lambda_ {i} = \gamma_ {i} + \sum_ {k = 1} ^ {n} p _ {k i} \lambda_ {k}, \text {f o r} i = 1, \dots , n
$$

or in standard matrix form:

$$
\boldsymbol {\lambda} = \boldsymbol {P} ^ {T} \boldsymbol {\lambda} + \boldsymbol {\gamma}
$$

# General Network Approximation Model

V Consider a general network of n workstations with switching rule defined by the routing matrix P and assume that the sum of at least one row of P is strictly less than one (i.e., jobs exit the network from at least one workstation)   
> Let Y = (Y1，· · · ,Yn) denote a vector consisting of the mean arrival rate of jobs from an external source to the workstations.   
> Let λ= (^1，· · ·,>n) be the unknown vector denoting mean arrival rates of all jobs to the workstations   
The vector λ is given by

$$
\boldsymbol {\lambda} = \left(I - P ^ {T}\right) ^ {- 1} \boldsymbol {\gamma}
$$

where lis an nxn identity matrix.

# Example

Consider the factory network of workstations depicted in the figure,with the noted branching probabilities and an external flow rate into the first workstation of 5 jobs per hour.   
The system of equations defining the workstation total arrival rates are

$$
\begin{array}{l} \lambda_ {1} = 5 + 0. 1 0 \lambda_ {2} + 0. 0 5 \lambda_ {3} \\ \lambda_ {2} = 0 + 0. 7 5 \lambda_ {1} \\ \lambda_ {3} = 0 + 0. 2 5 \lambda_ {1} + 0. 9 0 \lambda_ {2} \\ \end{array}
$$

![](images/5588825e6f2e0c43c26675fba64a2175c5f0dd9b78b27c8b161ec71bb55ae037.jpg)

This system rearranged is

$$
\begin{array}{l} 1 \lambda_ {1} - 0. 1 0 \lambda_ {2} - 0. 0 5 \lambda_ {3} = 5 \\ - 0. 7 5 \lambda_ {1} + 1 \lambda_ {2} + 0 \lambda_ {3} = 0 \\ - 0. 2 5 \lambda_ {1} - 0. 9 0 \lambda_ {2} + 1 \lambda_ {3} = 0, \\ \end{array}
$$

which has the unique solution

$$
\lambda_ {1} = 5. 6 9 0, \lambda_ {2} = 4. 2 6 7, \lambda_ {3} = 5. 2 6 3
$$

Thus, the first workstation receives 5.690 jobs per hour; 5 of these from the external source and the remaining 0.690 jobs from Workstations 2 and 3   
V The second workstation receives 4.267 jobs per hour, all of these from Workstation 1   
V The third workstation receives a total of 5.263 jobs per unit time as the combined inflow from Workstations 1 and 2

# Exercises

V Compute the mean flow rates for the systems ilustrated in the two figures

![](images/385ed88d18af99e5f6c13bd3f6e56386eb071137aa2f335e0b6e2442dd50e6e0.jpg)

![](images/fb0c7bd24714f695345617c7d82498a66677e5dcc4179f822c4f63b0bff307c6.jpg)

# Solution (1)

![](images/8e19e8ff3762f2e1473009fb97bc8016bed65593ef77d90a9c4ba843039f626c.jpg)

![](images/ce608698cc17f63269674293c07f52f0aed1f8c3a609c94d04c69d595a85b9c9.jpg)

$$
\begin{array}{l} \lambda_ {1} = 1 0 \\ \lambda_ {2} = \frac {3}{4} \cdot \lambda_ {1} = 7, 5 \\ \lambda_ {3} = \lambda_ {2} + \frac {1}{4} \cdot \lambda_ {1} = 1 0 \\ \end{array}
$$

# Solution (2)

![](images/f4b333d2fb9327a37b727f5b826b053698e3bdbdd041265a656e9a403ea0d3bd.jpg)

![](images/2f46c7f319ac44edd01fef403738d4aebd31ed0e2a7cead1a8d1182806baae95.jpg)

$$
\lambda_ {1} = 1 0 + \frac {1}{3} \cdot \lambda_ {2} + \frac {1}{5} \cdot \lambda_ {3} = 1 6. 6 7
$$

$$
\lambda_ {2} = \frac {3}{4} \cdot \lambda_ {1} = 1 2. 5
$$

$$
\lambda_ {3} = \frac {2}{3} \cdot \lambda_ {2} + \frac {1}{4} \cdot \lambda_ {1} = 1 2. 5
$$

$$
\mathsf {T H} = \frac {4}{5} \cdot \lambda_ {3} = 1 0
$$

# General Network Approximation Model

To obtain the squared coefficients of variation for the composite arrival stream into each workstation,a system of linear equations relating all of these coefficients must be solved

Solution procedure is similar to obtaining the net inflow rates   
Individual equations much more complex

The inflow into a given workstation j is made up of the proportions of the departure stream from those workstations that feed into j along with any external stream that comes directly to j

$$
C _ {a} ^ {2} (j) = \frac {\gamma_ {j}}{\lambda_ {j}} C _ {a} ^ {2} (0, j) + \sum_ {k = 1} ^ {n} \frac {\lambda_ {k} p _ {k , j}}{\lambda_ {j}} C _ {a} ^ {2} (k, j)
$$

$$
C _ {a} ^ {2} (j) = \frac {\gamma_ {j}}{\lambda_ {j}} C _ {a} ^ {2} (0, j) + \sum_ {k = 1} ^ {n} \frac {\lambda_ {k} p _ {k , j}}{\lambda_ {j}} \left(p _ {k, j} C _ {d} ^ {2} (k) + 1 - p _ {k, j}\right)
$$

# Exercise

Y Analyze the network reported in the figure and find the arrival parameters at all the workstations

![](images/5051d8b09e45c054f65559c92a882e6a7785e8ffc24fac5cf00f626c15b1a9ee.jpg)

# Solution

Routing matrix

![](images/93510986816d6bb6a6673748457a74ab34d1b59e663df1f99f6330eb4c5b89da.jpg)

![](images/0b1f7ba366d1379d8a17670314ea7ce7c91fa57a86c87b08bbfd3db8dace19ba.jpg)

# Solution

Workstation 1

![](images/1d22d91f3ed9fed936c11b8bcc002a0495d850d43b66a0836470402cac51aa61.jpg)

![](images/5ddd04e0b39e2ae5047498a59d887a419583f773c18593881a1ce5df818cbd15.jpg)

$$
\lambda_ {1} = \gamma_ {1} = 3 \mathrm {j / h}
$$

$$
\mathsf {C} _ {\mathrm {a}} ^ {2} (1) = \gamma_ {1} / \lambda_ {1} * \mathsf {C} _ {\mathrm {a}} ^ {2} (0, 1) + 0 = 1
$$

$$
\mathsf {C} _ {\mathsf {d}} ^ {2} (1) = 1
$$

$$
\lambda_ {i} = \gamma_ {i} + \sum_ {i} ^ {n} p _ {k i} \lambda_ {k}, \text {f o r} i = 1, \dots , n
$$

$$
C _ {a} ^ {2} (j) = \frac {\gamma_ {j}}{\lambda_ {j}} C _ {a} ^ {2} (0, j) + \sum_ {k = 1} ^ {n} \frac {\lambda_ {k} p _ {k , j}}{\lambda_ {j}} \left(p _ {k, j} C _ {d} ^ {2} (k) + 1 - p _ {k, j}\right)
$$

# Solution

# Workstation 2

![](images/e19acd904091048d3a5dfc260b7eb203ba7c4a035e383db673d1377fc44c6e9a.jpg)

![](images/7b88c2bf1d6590a0ccb7804f50d7ca7c1936eb3e21e188a4a760654731122c1e.jpg)

$$
\lambda_ {i} = \gamma_ {i} + \sum_ {k = 1} ^ {n} p _ {k i} \lambda_ {k}, \text {f o r} i = 1, \dots , n
$$

$$
C _ {a} ^ {2} (j) = \frac {\gamma_ {j}}{\lambda_ {j}} C _ {a} ^ {2} (0, j) + \sum_ {k = 1} ^ {n} \frac {\lambda_ {k} p _ {k , j}}{\lambda_ {j}} \left(p _ {k, j} C _ {d} ^ {2} (k) + 1 - p _ {k, j}\right)
$$

$$
\lambda_ {2} = \gamma_ {2} + 0. 5 ^ {*} \lambda_ {1} = 2 + 0. 5 ^ {*} 3 = 3. 5 \mathrm {j / h}
$$

$$
\mathsf {C} _ {\mathsf {a}} ^ {2} (2) = \gamma_ {2} / \lambda_ {2} * \mathsf {C} _ {\mathsf {a}} ^ {2} (0, 2) + \lambda_ {1} \mathsf {p} _ {1 2} / \lambda_ {2} (\mathsf {p} _ {1 2} \mathsf {C} _ {\mathsf {d}} ^ {2} (1) + 1 - \mathsf {p} _ {1 2}) =
$$

$$
2 / 3. 5 ^ {\star} 1 + 3 ^ {\star} 0. 5 / 3. 5 ^ {\star} (0. 5 ^ {\star} 1 + 1 - 0. 5) = 1
$$

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (2) = 1
$$

# Solution

Workstation 3

![](images/372d686d50e3ff320f049692954c696696f0add2d55c95c7a1a2cafb4bf24d2a.jpg)

![](images/55e0b48e2c3e511555519a21a3fd3b4924adaf705baa176d9c0492882d90ac6c.jpg)

$$
\lambda_ {i} = \gamma_ {i} + \sum_ {k = 1} ^ {n} p _ {k i} \lambda_ {k}, \text {f o r} i = 1, \dots , n
$$

$$
C _ {a} ^ {2} (j) = \frac {\gamma_ {j}}{\lambda_ {j}} C _ {a} ^ {2} (0, j) + \sum_ {k = 1} ^ {n} \frac {\lambda_ {k} p _ {k , j}}{\lambda_ {j}} \left(p _ {k, j} C _ {d} ^ {2} (k) + 1 - p _ {k, j}\right)
$$

$$
\lambda_ {3} = 0. 5 ^ {*} \lambda_ {1} + \lambda_ {2} = 0. 5 ^ {*} 3 + 3. 5 = 5 \mathrm {j / h}
$$

$$
\begin{array}{l} \mathsf {C} _ {\mathrm {a}} ^ {2} (3) = \lambda_ {1} \mathsf {p} _ {1 3} / \lambda_ {3} (\mathsf {p} _ {1 3} ^ {*} \mathsf {C} _ {\mathrm {d}} ^ {2} (1) + 1 - \mathsf {p} _ {1 3}) + \lambda_ {2} \mathsf {p} _ {2 3} / \lambda_ {3} (\mathsf {p} _ {2 3} ^ {*} \mathsf {C} _ {\mathrm {d}} ^ {2} (2) + 1 - \mathsf {p} _ {2 3}) = \\ 3 ^ {\star} 0. 5 / 5 ^ {\star} (0. 5 ^ {\star} 1 + 1 - 0. 5) + 3. 5 / 5 ^ {\star} 1 = 1 \\ \end{array}
$$

# General Network Approximation Model

To analyze a general network, the mean arrival rate into each workstation is first determined   
Then workstation utilization factors are calculated since these depend on the just computed arrival rates   
A Finally the squared coefficients of variation for the arrival streams are computed either by a successive substitution iteration or by finding the inverse matrix   
Y At this point, the network can be decomposed and each workstation treated individually   
> Finally, these results are combined to estimate the performance characteristics of the system as a whole

# Example

V Consider a factory that consists entirely of single-server workstations with service time data for each workstation given in the Table   
V The arrivals from an external source enter into the factory at the first workstation, and the arivals are exponentially distributed with a mean rate of 5 jobs per hour   
The topology of the factory is shown in the figure   
V Find the mean cycle time for jobs, the factory inventory levels,and the workloads of each workstation

![](images/8b9b801c31ffcf23bd9752378ca91987cca82c9566f8526d16309a850d826f52.jpg)

![](images/4b82750e4e3fc54cc1ba5bb5523c5861ec6cc1fd46e49b3a8058ba0994d2b776.jpg)

# Step 1: Workstation Arrival Rates

The first goal is to obtain the composite inflow rate into each workstation

$$
\lambda_ {1} = 5 + \frac {1}{1 0} \lambda_ {4}
$$

$$
\lambda_ {2} = 0 + \frac {2}{3} \lambda_ {1} + \frac {2}{1 0} \lambda_ {4}
$$

$$
\lambda_ {3} = 0 + \frac {1}{3} \lambda_ {1} + \frac {3}{1 0} \lambda_ {4}
$$

$$
\lambda_ {4} = 0 + \lambda_ {2} + \lambda_ {3}.
$$

$$
\left(\lambda_ {1}, \lambda_ {2}, \lambda_ {3}, \lambda_ {4}\right) = (6. 2 5, 6. 6 6 7, 5. 8 3 3, 1 2. 5)
$$

# Step 2: Workstation utilizations

The workload to each workstation is the mean job arrival rate multiplied by the mean processing time per job which then equals the utilization factor

![](images/116a7057d0c92fc661e30e0074ddfedabc27e0384c049dad602c1beac661e80b.jpg)

# Step 3: Squared Coefficients of Variation

V Squared coefficients of variations of the job inter-arrival times for each workstation

$$
C _ {a} ^ {2} (1) = \frac {5}{6 . 2 5} + \frac {1 2 . 5 (0 . 1)}{6 . 2 5} \left[ \frac {1}{1 0} \left(0. 3 6 C _ {a} ^ {2} (4) + 0. 6 4 \times 2. 4 4 1 4\right) + \frac {9}{1 0} \right]
$$

$$
\begin{array}{l} C _ {a} ^ {2} (2) = \frac {6 . 2 5 (0 . 6 6 6 7)}{6 . 6 6 6 7} \left[ \frac {2}{3} \left(0. 3 3 9 8 C _ {a} ^ {2} (1) + 0. 6 6 0 2 \times 1. 0 3 5 5\right) + \frac {1}{3} \right] \\ + \frac {1 2 . 5 (0 . 2)}{6 . 6 6 6 7} \left[ \frac {2}{1 0} \left(0. 3 6 C _ {a} ^ {2} (4) + 0. 6 4 \times 2. 4 4 1 4\right) + \frac {8}{1 0} \right] \\ \end{array}
$$

$$
\begin{array}{l} C _ {a} ^ {2} (3) = \frac {6 . 2 5 (0 . 3 3 3 3)}{5 . 8 3 3 3} \left[ \frac {1}{3} \left(0. 3 3 9 8 C _ {a} ^ {2} (1) + 0. 6 6 0 2 \times 1. 0 3 5 5\right) + \frac {2}{3} \right] \\ + \frac {1 2 . 5 (0 . 3)}{5 . 8 3 3 3} \left[ \frac {3}{1 0} \left(0. 3 6 C _ {a} ^ {2} (4) + 0. 6 4 \times 2. 4 4 1 4\right) + \frac {7}{1 0} \right] \\ \end{array}
$$

$$
\begin{array}{l} C _ {a} ^ {2} (4) = \frac {6 . 6 6 6 7 (1)}{1 2 . 5} \left[ 1 \left(0. 2 4 8 8 C _ {a} ^ {2} (2) + 0. 7 5 1 2 \times 1. 7 7 5 1\right) + 0 \right] \\ + \frac {5 . 8 3 3 3 (1)}{1 2 . 5} \left[ 1 \left(0. 1 2 9 0 C _ {a} ^ {2} (3) + 0. 8 7 1 0 \times 0. 3 9 0 6\right) + 0 \right]. \\ \end{array}
$$

# Step 3: Squared Coefficients of Variation

# Simplified system and solution

$$
C _ {a} ^ {2} (1) = 0. 0 0 7 2 C _ {a} ^ {2} (4) + 1. 0 1 1 2
$$

$$
C _ {a} ^ {2} (2) = 0. 1 4 1 6 C _ {a} ^ {2} (1) + 0. 0 2 7 0 C _ {a} ^ {2} (4) + 0. 9 1 0 4
$$

$$
C _ {a} ^ {2} (3) = 0. 0 4 0 5 C _ {a} ^ {2} (1) + 0. 0 6 9 4 C _ {a} ^ {2} (4) + 1. 0 7 0 8
$$

$$
C _ {a} ^ {2} (4) = 0. 1 3 2 7 C _ {a} ^ {2} (2) + 0. 0 6 0 2 C _ {a} ^ {2} (3) + 0. 8 6 9 9
$$

$$
\mathbf {c} _ {a} ^ {2} = \left( \begin{array}{c c c c} 1 & 0 & 0 & - 0. 0 0 7 2 \\ - 0. 1 4 1 6 & 1 & 0 & - 0. 0 2 7 0 \\ - 0. 0 4 0 4 5 & 0 & 1 & - 0. 0 6 9 4 \\ 0 & - 0. 1 3 2 7 & - 0. 0 6 0 2 & 1 \end{array} \right) ^ {- 1} \left( \begin{array}{c} 1. 0 1 1 2 \\ 0. 9 1 0 4 \\ 1. 0 7 0 8 \\ 0. 8 6 9 9 \end{array} \right) = \left( \begin{array}{c} 1. 0 1 9 0 \\ 1. 0 8 4 0 \\ 1. 1 8 7 4 \\ 1. 0 8 5 2 \end{array} \right)
$$

# Step 4: Decomposition

With the determination of arrival rates and squared coefficients of variation, each workstation is analyzed as if it were an isolated workstation

$$
C T (1) = \left(\frac {1 . 0 1 9 1 + 1 . 0 3 5 5}{2}\right) \left(\frac {0 . 8 1 2 5}{1 - 0 . 8 1 2 5}\right) (0. 1 3 0) + 0. 1 3 0 = 0. 7 0 9 \mathrm {h r}
$$

$$
W I P _ {s} (1) = 0. 7 0 9 \times 6. 2 5 = 4. 4 2 9
$$

$$
C T (2) = \left(\frac {1 . 0 8 4 0 + 1 . 7 7 5 1}{2}\right) \left(\frac {0 . 8 6 6 7}{1 - 0 . 8 6 6 7}\right) (0. 1 3 0) + 0. 1 3 0 = 1. 3 3 8 \mathrm {h r}
$$

$$
W I P _ {s} (2) = 1. 3 3 8 \times 6. 6 6 6 7 = 8. 9 2 0
$$

$$
C T (3) = \left(\frac {1 . 1 8 7 4 + 0 . 3 9 0 6}{2}\right) \left(\frac {0 . 9 3 3 3}{1 - 0 . 9 3 3 3}\right) (0. 1 6 0) + 0. 1 6 0 = 1. 9 2 7 \mathrm {h r}
$$

$$
W I P _ {s} (3) = 1. 9 2 7 \times 5. 8 3 3 3 = 1 1. 2 4 3
$$

$$
C T (4) = \left(\frac {1 . 0 8 5 2 + 2 . 4 4 1 4}{2}\right) \left(\frac {0 . 8}{1 - 0 . 8}\right) (0. 0 6 4) + 0. 0 6 4 = 0. 5 1 5 \mathrm {h r}
$$

$$
W I P _ {s} (4) = 0. 5 1 5 4 \times 1 2. 5 = 6. 4 4 3.
$$

# Step 5: Factory Performance Measures

The factory throughput rate is equal to the inflow rate   
>THs = 5/hr

V The work in process for the whole factory is the sum of the individual workstation work in process numbers

>WIPs = 31.03

V Little's Law yields the mean cycle time

>CTs = 31.03/5= 6.206 hr   
>Notice that CTs is greater than the sum of the individual workstation cycle times because most jobs visit some of the workstations more than once

# Exercise

Consider a factory that consists of three single-server workstations with service time data reported in the table   
The arrivals from an external source have a mean rate of 10 jobs per hour and a squared coefficient of variation of 1.5   
The topology is shown in the figure   
> Compute the system performance measures of throughput, cycle time and work in process for this network.

![](images/8ab38ce6b194795c116457a2e6c2673e30ab49cd2684f38562be700c53bb2767.jpg)

![](images/8834c400717a8af8b6194783e5d6787f219a1737a035c4be974143ca7377698e.jpg)

![](images/4288c53231370f9c30ee49c79fc4658958bb8f8cfd5303ba8ea21bbf5f415649.jpg)

$$
\lambda_ {1} = 1 0
$$

$$
u _ {1} = 1 0 \cdot 0. 0 8 6 = 0. 8 6
$$

$$
\lambda_ {2} = \frac {3}{4} \cdot \lambda_ {1} = 7. 5
$$

$$
u _ {2} = 7. 5 \cdot 0. 1 1 = 0. 8 2 5
$$

$$
\lambda_ {3} = \lambda_ {2} + \frac {1}{4} \cdot \lambda_ {1} = 1 0
$$

$$
\mathrm {u} _ {3} = 1 0 \cdot 0. 0 8 = 0. 8
$$

$$
c _ {a 1} ^ {2} = 1. 5
$$

$$
c _ {a 2} ^ {2} = \frac {3}{4} \cdot c _ {d 1} ^ {2} + 1 - \frac {3}{4} = \frac {3}{4} \cdot ((1 - u _ {1} ^ {2}) \cdot c _ {a 1} ^ {2} + u _ {1} ^ {2} \cdot c _ {s 1} ^ {2}) + 1 - \frac {3}{4} = 1. 2 9 3
$$

$$
c _ {a 3} ^ {2} = \frac {1}{4} \cdot \frac {1 0}{1 0} \cdot (\frac {1}{4} \cdot c _ {d 1} ^ {2} + 1 - \frac {1}{4}) + 1 \cdot \frac {7 , 5}{1 0} \cdot c _ {d 2} ^ {2} = 1. 0 0 6
$$

$$
\mathrm {C T} _ {1} = \frac {c _ {\mathrm {a} +} ^ {2} c _ {\mathrm {e}} ^ {2}}{2} \cdot \frac {\mathrm {u}}{1 - \mathrm {u}} \cdot \mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (1) ] + \mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (1) ] = 0. 8 3 9 4 \mathrm {h}
$$

$$
\mathrm {W I P} _ {1} = \mathrm {C T} _ {1} \cdot \lambda_ {1} = 8. 3 9 4
$$

$$
\mathrm {C T} _ {2} = \frac {c _ {\mathrm {a} +} ^ {2} c _ {\mathrm {e}} ^ {2}}{2} \cdot \frac {\mathrm {u}}{1 - \mathrm {u}} \cdot \mathrm {E} [ \mathrm {T} _ {s} (2) ] + \mathrm {E} [ \mathrm {T} _ {s} (2) ] = 0. 6 6 \mathrm {h}
$$

$$
\mathrm {W I P} _ {2} = \mathrm {C T} _ {2} \cdot \lambda_ {2} = 4. 9 5
$$

$$
\mathrm {C T} _ {3} = \frac {\mathrm {c} _ {\mathrm {a} +} ^ {2} \mathrm {c} _ {\mathrm {e}} {} ^ {2}}{2} \cdot \frac {\mathrm {u}}{1 - \mathrm {u}} \cdot \mathrm {E} [ \mathrm {T} _ {s} (3) ] + \mathrm {E} [ \mathrm {T} _ {s} (3) ] = 0. 4 9 1 \mathrm {h}
$$

$$
\mathrm {W I P} _ {3} = \mathrm {C T} _ {3} \cdot \lambda_ {3} = 4. 9 1
$$

![](images/dcdaf29cd1474bb80f9ce9369617f106a0fd7af5fb1c0381b08ec092bbce63f2.jpg)

$$
P =
$$

![](images/c3628f0b2a56f5c6cedd95aae2817890c10799237ad1d2fe34290b92d5d94490.jpg)

$$
\mathbf {W I P} _ {T O T} = 1 8. 2 5 4 \mathrm {j}
$$

$$
\mathrm {C T} _ {\text {T O T}} = \frac {\mathrm {W I P} _ {\text {T O T}}}{\mathrm {T H}} = 1. 8 2 5 \mathrm {h}
$$
