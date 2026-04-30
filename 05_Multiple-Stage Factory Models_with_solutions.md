# Analysis and Management of Production System

# Lesson 5: Multiple-stage factory models

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Flow Variability

> Till now, our attention was on the analysis of a single workstation   
>The workstation impact on the output flow of jobs from the workstations was not considered as this information was not needed to study the performance of a single workstation   
> But the variability of a station has effects on the behaviour of the next Station on the line and, when the output from a WS becomes the input to the next one, this aspect can be no more neglected: this generates the so-called flow variability   
> Flow: transfer of a job or a part from one machine to the other

# Flow Variability

# Arrivals:

E[Ta] → mean time between two arrivals   
>c²a → squared coefficient of variation of the mean time between two arrivals

# V Process:

E[Te] → effective process time   
>c²e → squared coefficient of variation of the effective process time   
E[Te] < E[Ta] → otherwise, the station would be overloaded

# Departures:

E[Td]→ mean time between two departures/releases   
>c²d → squared coefficient of variation of the mean time between two departures

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
> If the WS is lightly loaded, instead, the inter-departure time distribution should be similar to the inter-arrival time distribution,so that cd² should be similar to ca² 

# Variability of departures

### Diagram Description: Signal Processing Logic (LV vs HV)

1.  **Top Row (LV to HV Transition):** 
    *   **Input:** Labeled "LV" (Low Value/Volatility) with sparse pink dots along the line.
    *   **Process:** Passes through a central orange box labeled **"HV"**.
    *   **Output:** Results in an **"HV"** state with a higher density of dots.

2.  **Second Row (HV Maintenance):** 
    *   **Input:** Labeled "HV" with a high density of pink dots.
    *   **Process:** Passes through a central orange box labeled **"HV"**.
    *   **Output:** Remains an **"HV"** state with maintained high density.

3.  **Third Row (LV Maintenance):** 
    *   **Input:** Labeled "LV" with sparse pink dots.
    *   **Process:** Passes through a central orange box labeled **"LV"**.
    *   **Output:** Remains an **"LV"** state with sparse dots.

4.  **Bottom Row (HV to LV Transition):** 
    *   **Input:** Labeled "HV" with high dot density.
    *   **Process:** Passes through a central orange box labeled **"LV"**.
    *   **Output:** Results in an **"LV"** state where the density of dots is reduced.

**Core Logic:** The diagram demonstrates that the central processing block (the box) determines the final output state (HV or LV), effectively acting as a filter or a state-assigner regardless of the initial input density.

# High-usage station

>Theflow variability out of a high-usage station is mainly determined by the process variability of the station itself

# Variability of departures

# Low-usage station

>The flow variability out of a low-usage station is mainly determined by the arrival variability

# Variability of departures

Whitt equation

$$
C _ {d} ^ {2} (G / G / 1) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} C _ {s} ^ {2}
$$

$$
C _ {d} ^ {2} (G / G / c) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} \frac {C _ {s} ^ {2} + \sqrt {c} - 1}{\sqrt {c}}
$$

* $u \sim 1$: the station is almost always busy, thus $c_d^2 \sim c_s^2$
* $u \sim 0$: the station is almost never busy, thus $c_d^2 \sim c_a^2$

# Example

For a single server workstation, the inter-arrival distribution parameters are E[Ta] = 20 min and C²a = 1/2.The service time distribution parameters are E[T] = 15 min and C²= 1/3   
> Then λ= 3/hr and μ = 4/hr, and the system utilization factor u  = λ/μ = 3/4   
> The squared coeffcient of variation of the inter-departure times is given by

$$
C _ {d} ^ {2} = \left(1 - \left(\frac {3}{4}\right) ^ {2}\right) \frac {1}{2} + \left(\frac {3}{4}\right) ^ {2} \frac {1}{3} = \frac {1 3}{3 2} = 0. 4 0 6 2 5
$$

# Exercises

> A workstation has a workload that uses 85% of its single machine capacity. Arrivals to the workstation are exponentially distributed and the service time SCV is 1.5. What is the estimated SCV of the departure stream?   
A two-machine workstation has a utilization factor of 8o%. The arrival SCV is 2.0 and the service time follows an Erlang-2 distribution. What is the estimated SCV of the departure stream?

# Solution (1)

> A workstation has a workload that uses 85% of its single machine capacity. Arrivals to the workstation are exponentially distributed and the service time SCV is 1.5. What is the estimated SCV of the departure stream?

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

> A two-machine workstation has a utilization factor of 8o%. The arrival SCV is 2.0 and the service time follows an Erlang-2 distribution. What is the estimated SCV of the departure stream?

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

### Diagram Description: Linear 3-Stage Process Flow

Basic sequential system or a tandem queueing model. It consists of three primary components arranged in a horizontal linear progression.

*   **Components:** Three square blocks numbered sequentially as **1**, **2**, and **3**.
*   **Connectivity:** 
    *   An incoming arrow from the left enters **Block 1**, representing the system input.
    *   A connecting arrow leads from **Block 1** to **Block 2**.
    *   A connecting arrow leads from **Block 2** to **Block 3**.
    *   An outgoing arrow exits **Block 3** to the right, representing the system output or finished state.
*   **Logic:** This diagram represents a **tandem configuration** where work, data, or signals must pass through each stage in a fixed order. In the context of operations management or queueing theory, this depicts a three-station production line or service chain.

> In a serial ine having a constant flow with no losses or reworks,anything that comes out of a station enters the following one   
> This system is treated as a series of G/G/c queues with specified service parameters (E[Ts(i)], C²s, (i), Ci) for each workstation i   
> Because of the serial nature of the system, the arrival stream for workstation iis the departure stream from workstation i-1

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
> When they arrive, there is a single clerk who takes their information; this process takes an exponentially distributed length of time with an average of 4 minutes per patient   
> There is a triage nurse who next sees the patient; the nurse takes an exponentially distributed length of time averaging 10 minutes per patient   
> Finally, one of two doctors sees the patient and each doctor takes an exponentially distributed amount of time with each patient averaging 24 minutes with the doctor   
> We would like to know the average number of patients within the facility at any one time and the average time that a patient spends in the emergency room

# Example

> The emergency room system is composed of an M/M/1 system feding a ·/M/1 system feeding a ·/M/2 system   
> Because of the property that M/M/c systems have exponential inter-departure times,the second and third nodes are an M/M/1 and M/M/2 system with an arrival rate of 4 per hour   
> The system can be analyzed as three independent single node systems   
> The first node has a utilization factor of u,= 4/15 and thus the average number of patients in the first node is WiP(1) = 4/11.   
> The second node has a utilization factor of uz= 2/3 yielding WiP(2) = 2

# Example

> For the third node,we firstfind the time spent waiting for the doctor, i.e., CTq(3)= 42.67 min since u3= 0.8   
> Adding the doctor's time to the wait time yields the time spent in third node as CT(3)= 1.11 hr   
> Applying Litle's Law gives the average number of patients at the node as WIP(3) = 4.44   
> Thus, the total number in the emergency room is WIP = 4/11 + 2 + 4.44 = 6.8   
> Applying Litle's Law one more time, yields the average value for the total time a patient spends in the emergency room as CTs = 1.7 hr

# Generalization

> The analysis approach used in the Example is exact only under the assumptions of infinite capacity nodes and exponential distributions for inter-arrivals and processing times, but it provides the motivation for approximation schemes when these assumptions do not hold   
> The analysis approach for general systems is based on the concept that a system's performance can be adequately approximated by separating the system into individual workstations   
The performance characteristics of the individual workstations are computed separately and then these results recombined for the total system behavior   
> This decomposition approach is fundamental to the approximation of general network configurations

# Example

> Consider a three-workstation factory with serial flow   
> Each workstation has a single machine with the service time distribution parameters as listed in the table   
The inter-arrival time distribution for jobs to the factory has a mean of 15 minutes or a mean rate of 4 jobs per hour, and a squared coefficient of variation of 0.75   
The system mean work-in-process,cycle time,and throughput are desired

| Workstation $i$ | $E[T_s(i)]$ | $C_s^2(i)$ |
| :---: | :---: | :---: |
| 1 | 12 min | 2.0 |
| 2 | 9 min | 0.7 |
| 3 | 13.2 min | 1.0 |

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

> Because this is a pure serial network, the arrival rate and throughput rate will be the same for each workstation   
> Thus,the utilization factors for the other two workstations are U2 = E[Ts(2)/E[Ta(1)]=0.6 and u3= E[Ts(3)]/E[Ta(1)]= 0.88

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

> Find the system performance measures of CTs,WIPs,and throughput for a pure serial system consisting of three single capacity workstations   
> The arrival rate to the system is 3 jobs per hour, with the inter-arrival time being exponentially distributed   
The processing time data are:

| Workstation $i$ | $E[T_i]$ | $C^2[T_i]$ |
| :---: | :---: | :---: |
| 1 | 0.25 hr | 4 |
| 2 | 0.29 hr | 3 |
| 3 | 0.30 hr | 2 |

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
C T _ {q 3} = \frac {c _ {a} {} ^ {2} + c _ {e 3} {} ^ {2}}{2} \cdot \frac {u}{1 - u} \cdot \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} (3) ] = 6, 64 \mathrm {h}
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

### Image Description: Sequential Workstation Flow (WS1-WS3)

The image depicts a standard linear or tandem process configuration, commonly used to model production lines or service sequences in engineering environments.

*   **Workstation 1 (WS1)**: Represented as the starting blue rectangular block on the left.
*   **Workstation 2 (WS2)**: The intermediate stage, connected to WS1 by a horizontal directional arrow.
*   **Workstation 3 (WS3)**: The final stage in this sequence, connected to WS2 by a horizontal directional arrow.

**System Logic**:
The diagram illustrates a strictly serial flow where work or data moves sequentially from WS1 through WS2 and finally to WS3. This layout is typical for analyzing throughput, cycle times, and workstation utilization in a three-stage system.

# Exercise 2

> Find the system performance measures of CTs, WiPs, and throughput for a three-workstation pure serial system   
> The arrval rate to the system is one job every two hours with an SCV of 2.0.   
> The machine data for the three single-capacity workstations are given below.

| Workstation $i$ | $E[T_i]$ | $C^2[T_i]$ | Availability | $E[R]$ | $C^2[R]$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 1.6 hr | 0.75 | 0.85 | 2.0 hr | 1.30 |
| 2 | 1.5 hr | 1.50 | 0.90 | 2.5 hr | 1.50 |
| 3 | 1.7 hr | 2.00 | 0.90 | 3.0 hr | 1.75 |

# Exercise 2- Solution (1)

$$
\begin{array}{l} E [ T _ {a} ] = 2 \mathsf {h} \\ c _ {a} ^ {2} = 2 \\ \lambda_ {a} = 0, 5 \mathrm {u / h} \\ \end{array}
$$

WS1

$$
\begin{aligned}
E[T_s(2)] &= 1,5 \text{ h.} \\
c_{s1}^2 &= 0,75 \\
a &= 0,85 \\
E_1[R] &= 2 \text{ h} \\
c_1^2[R] &= 1,3 \\
E[T_e(1)] &= \frac{E[T_s(1)]}{a} = 1,88 \text{ h} \\
c_{e1}^2 &= c_{s1}^2 + \frac{(1+c_1^2[R])a \cdot (1-a) \cdot E_1[R]}{E[T_s(1)]} = 1,12 \\
u_1 &= \frac{E[T_e(1)]}{E[T_a]} = 0,94 \\
c_d^2(1) &= u^2 \cdot c_e^2 + (1-u^2) \cdot c_a^2 = 1,22 \\
CT_{q1} &= \frac{c_a^2 + c_{e1}^2}{2} \cdot \frac{u}{1-u} \cdot E[T_e(1)] = 45,94 \text{ h} \\
CT_1 &= CT_{q1} + E[T_e(1)] = 47,83 \text{ h} \\
WIP_1 &= CT_1 \cdot \lambda_a = 24
\end{aligned}
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
\begin{aligned}
E[T_s(1)] &= 1,6 \text{ h.} \\
c_{s2}^2 &= 1,50 \\
a &= 0,90 \\
E_2[R] &= 2,5 \text{ h} \\
c_2^2[R] &= 1,5 \\
E[T_e(2)] &= \frac{E[T_s(2)]}{a} = 1,78 \text{ h} \\
c_{e2}^2 &= c_{s2}^2 + \frac{(1+c_2^2[R])a \cdot (1-a) \cdot E_2[R]}{E[T_s(2)]} = 1,85 \\
u_1 &= \frac{E[T_e(1)]}{E[T_a]} = 0,89 \\
c_d^2(2) &= u^2 \cdot c_e^2 + (1-u^2) \cdot c_a^2 = 1,71 \\
CT_{q2} &= \frac{c_a^2 + c_{e2}^2}{2} \cdot \frac{u}{1-u} \cdot E[T_e(2)] = 22,10 \text{ h} \\
CT_2 &= CT_{q2} + E[T_e(2)] = 23,88 \text{ h} \\
WIP_2 &= CT_2 \cdot \lambda_a = 12
\end{aligned}
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
\begin{aligned}
E[T_s(3)] &= 1,7 \text{ h.} \\
c_{s3}^2 &= 2,00 \\
a &= 0,90 \\
E_3[R] &= 3,0 \text{ h} \\
c_3^2[R] &= 1,75 \\
E[T_e(3)] &= \frac{E[T_s(3)]}{a} = 1,89 \text{ h} \\
c_{e3}^2 &= c_{s3}^2 + \frac{(1+c_3^2[R])a \cdot (1-a) \cdot E_3[R]}{E[T_s(3)]} = 2,436 \\
u_3 &= \frac{E[T_e(3)]}{E[T_a]} = 0,945 \\
CT_{q3} &= \frac{c_a^2 + c_{e3}^2}{2} \cdot \frac{u}{1-u} \cdot E[T_e(3)] = 35,26 \text{ h} \\
CT_3 &= CT_{q3} + E[T_e(3)] = 37,15 \text{ h} \\
WIP_3 &= CT_3 \cdot \lambda_a = 19
\end{aligned}
$$

$$
\begin{aligned}
CT_{TOT} &= 108,86 \\
WIP_{TOT} &= 55
\end{aligned}
$$

# Exercise 3

> Items arrive with interarrival times E[Ta]= 21 min,exponentially distributed   
Let's consider the following stations:

WSA: E[T:(a)] = 20 min (exponentially distributed)   
WSB: E[Ts(b)]= 20 min, σs= 5

The product X needs to be processed by both WSA and WSB   
> Having the possibility to choose the sequence, is it better to put WSA before WSB or WSB before WSA in the line?   
> Motivate the answer by computing total CT and WIP on the line in both cases

# Exercise 3 - Solution (1)

### Diagram Description: Two-Stage Tandem Queueing System

This diagram illustrates the flow and parameters of a sequential two-station queueing model, commonly used in **Operations Research** and **Queueing Theory**.

**1. Input Parameters (Arrival Process):**
*   **$E[T_a] = 21 \text{ min}$**: Mean interarrival time.
*   **$c_a^2 = 1$**: Squared coefficient of variation of arrivals (indicating a Poisson arrival process).
*   **$\lambda_a = \frac{1}{21} \text{ u/min}$**: Arrival rate to the system.

**2. Workstation A (WSA):**
*   **Model**: **M/M/1** (Markovian arrivals, Markovian service times, single server).
*   **$E[T_e(a)] = 20 \text{ min}$**: Mean effective service time for Station A.

**3. Intermediate Flow Logic:**
*   The connection between the stations follows the principle of flow conservation:
    *   **$\lambda_d(a) = \lambda_a(b)$**: The departure rate from A is equal to the arrival rate at B.
    *   **$c_d(a) = c_a(b)$**: The variability of departures from A becomes the variability of arrivals at B.

**4. Workstation B (WSB):**
*   **Model**: **M/G/1** (Markovian arrivals, General service time distribution, single server).
*   **$E[T_e(b)] = 20 \text{ min}$**: Mean effective service time for Station B.

**Analytical Context**:
This setup is a classic example for calculating system-wide performance metrics such as total cycle time ($CT_{tot}$) and total work-in-process ($WIP_{tot}$). Since both stations have a service time of 20 min and an arrival rate of $1/21$ u/min, the utilization ($u$) for both is approximately **0.95**, indicating a highly utilized system.

WSA

$$
\begin{aligned}
E[T_e(a)] &= 20 \text{ min} \\
c_e^2 &= 1 \\
u_a &= \frac{20}{21} = 0,952 \\
WIP(a) &= \frac{u}{1-u} = 19,8 \\
CT(a) &= \frac{WIP}{\lambda_a} = 416 \text{ min} \\
CT_q(a) &= CT - E[T_e(a)] = 396 \text{ min} \\
WIP_q(a) &= \lambda_a \cdot CT_q(a) = 18,8 \\
c_d^2(a) &= u^2 \cdot c_e^2 + (1-u^2) \cdot c_a^2 = 1
\end{aligned}
$$

WSB

$$
\begin{aligned}
E[T_e(b)] &= 20 \text{ min} \\
\sigma_e &= 5 \\
c_e &= \frac{\sigma_e}{E[T_e(b)]} = \frac{5}{20} = 0,25 \\
u_b &= \frac{20}{21} = 0,952 \\
CT_q(b) &= \frac{c_a^2 + c_e^2}{2} \cdot \frac{u}{1-u} \cdot E[T_e(b)] = 210 \text{ min} \\
WIP_q(b) &= \lambda_b \cdot CT_q(b) = 10 \\
CT(b) &= CT_q(b) + E[T_e(b)] = 230 \text{ min} \\
WIP(b) &= \lambda_b \cdot CT(b) = 10,95
\end{aligned}
$$

$$
\begin{aligned}
CT_{TOT} &= 416 + 230 = 646 \text{ min} \\
WIP_{TOT} &= 19,8 + 10,95 = 31
\end{aligned}
$$

# Exercise 3 - Solution (2)

### Diagram Description: Reversed Two-Stage Tandem Queueing System

This diagram illustrates a sequential two-station queueing model where the order of workstations is set as M/G/1 followed by G/M/1. 

**1. Input Parameters (System Arrivals):**
*   **$E[T_a] = 21 \text{ min}$**: Mean interarrival time.
*   **$c_a^2 = 1$**: Squared coefficient of variation for arrivals, representing a Markovian (Poisson) external arrival process.
*   **$\lambda_a = \frac{1}{21} \text{ u/min}$**: External arrival rate to the system.

**2. First Stage: Workstation B (WSB)**
*   **Queueing Model**: **M/G/1** (Markovian arrivals, General service time distribution).
*   **$E[T_e(b)] = 20 \text{ min}$**: Mean effective service time for Station B.

**3. Intermediate Flow Logic:**
*   A directional arrow shows the flow of processed units from WSB to WSA.
*   The diagram includes the flow linking equations: **$c_d(a) = c_a(b)$** and **$\lambda_d(a) = \lambda_a(b)$**. *(Technical note: While the notation uses specific indices, the logical rule shown is that the departure rate and variability from the first station become the arrival parameters for the second station).*

**4. Second Stage: Workstation A (WSA)**
*   **Queueing Model**: **G/M/1** (General arrivals derived from WSB's departures, Markovian service time).
*   **$E[T_e(a)] = 20 \text{ min}$**: Mean effective service time for Station A.

WSB

$$
\begin{aligned}
\sigma_e &= 5 \\
c_e &= \frac{\sigma_e}{E[T_e(b)]} = \frac{5}{20} = 0,25 \\
u_b &= \frac{20}{21} = 0,952 \\
CT_q(b) &= \frac{c_a^2 + c_e^2}{2} \cdot \frac{u}{1-u} \cdot E[T_e(b)] = 210 \text{ min} \\
WIP_q(b) &= \lambda_b \cdot CT_q(b) = 10 \\
CT(b) &= CT_q(b) + E[T_e(b)] = 230 \text{ min} \\
WIP(b) &= \lambda_b \cdot CT(b) = 10,95 \\
c_d^2(b) &= u^2 \cdot c_e^2 + (1-u^2) \cdot c_a^2 = 0,15
\end{aligned}
$$

WSA

$$
\begin{aligned}
c_e^2 &= 1 \\
u_a &= \frac{20}{21} = 0,952 \\
WIP(a) &= \frac{u}{1-u} = 19,8 \\
CT_q(a) &= \frac{c_a^2 + c_e^2}{2} \cdot \frac{u}{1-u} \cdot E[T_e(a)] = 230 \text{ min} \\
WIP_q(a) &= \lambda_a \cdot CT_q(a) = 11 \\
CT(a) &= CT_q(a) + E[T_e(a)] = 250 \text{ min} \\
WIP(a) &= \lambda_a \cdot CT(a) = 12
\end{aligned}
$$

BETTER PERFORMANCE

$$
\begin{aligned}
CT_{TOT} &= 230 + 250 = 480 \text{ min} \\
WIP_{TOT} &= 10,95 + 12 = 23
\end{aligned}
$$

# Nonserial Network Models

> Many production systems have more than one inflow point into the production system.   
> Products that may have been found defective or that have broken may be sent back to the manufacturing facility to be reworked

> These units will not necessarily enter the production line at the same point as a new job   
> If a defect is found during inspection after partially completing production, it may be sent to a rework station and then re-enter the production sequence at the appropriate point

# Nonserial Network Models

To study factory structures that are more realistic than pure serial systems, two additional structures must be studied to compute the squared coefficients of the various streams of jobs within the factory

merging of streams entering a workstation   
> spliting of output streams that come from a single workstation but are routed to more than one workstation

> These two processes,are firstly addressed separately, and then combined for a general network model

# Merging Inflow Streams

When multiple inflow streams arrive at a workstation with difering interarrival time distributions, the composite inter-arrival time distribution parameters need be computed   
> The process of merging inflow streams is technically called a superposition of the individual inter-arrval processes   
> It is assumed that the individual input streams are independent of one another and that each has independent and identically distributed interarrival times

> each of these input streams is said to be a renewal process

### Diagram Description: Superposition of Arrival Streams

This diagram illustrates the **superposition** (or merging) of multiple independent arrival processes into a single, aggregate arrival stream. This is a fundamental concept in network queueing models for analyzing workstations that receive input from several different routing paths.

**1. Incoming Streams (Inputs):**
*   Three distinct arrows converge at a single central point, representing three separate sources of work or data.
*   Each incoming stream $i$ (for $i = 1, 2, 3$) is characterized by two parameters:
    *   **$\lambda_i$**: The specific arrival rate of that stream.
    *   **$C_i^2$**: The squared coefficient of variation of the interarrival times for that stream, indicating its specific variability.

**2. Aggregate Stream (Output):**
*   A single arrow departs from the convergence point to the right, representing the combined flow of all incoming units.
*   **$\lambda$**: The total aggregate arrival rate. In standard queueing theory, this is the sum of the individual rates ($\lambda = \lambda_1 + \lambda_2 + \lambda_3$).
*   **$C_a^2$**: The squared coefficient of variation for the new, merged arrival process.

**System Logic:**
When multiple product types or data streams converge at a single processing unit, the total arrival rate is additive. However, calculating the new combined variability ($C_a^2$) requires specific approximations to accurately model the queueing behavior and delays at the receiving workstation.

# Merging Inflow Streams

Consider an arrival stream that is formed by merging n individual arrival processes   
The individual streams have mean arrival rates given by λ = 1/E[Ti] and squared coefcients of variation denoted by C2; for i= 1,..., n   
The mean arival rate, λa, and the squared coefficient of variation, C²a, for a renewal process used to approximate the merged arival process are given by:

$$
\lambda_ {a} = \sum_ {i = 1} ^ {n} \lambda_ {i} = \sum_ {i = 1} ^ {n} \frac {1}{E [ T _ {i} ]}
$$

$$
C _ {a} ^ {2} = \sum_ {i = 1} ^ {n} \frac {\lambda_ {i}}{\lambda_ {a}} C _ {i} ^ {2}.
$$

# Example

> An automated lubricating facility is located in the center of a manufacturing plant   
> Arrivals of parts needing lubrication come from three sources: manufactured parts needing assembly, defective parts that have been disassembled and willbe returned for reassembly, and parts coming from a sister manufacturing facility in another part of the town   
The three arrval streams have been analyzed separately

>The mean arrival rates for the three streams are given by the vector (λ1,λ2,λ3) = (13.2/hr, 3.6/r,6.0/hr)   
>The squared coeficients of variation for the three inflow streams are (C²1, C²2, C²3) = (5.0, 3.0, 2.2)

Find the inter-arrival time distribution parameters

# Example

> The total inflow into the workstation is the sum of the individual inflows so that λa = 22.8/hr   
> The relative weights, 13.2/22.8, 3.6/22.8,and 6.0/22.8, are thus used to determine the composite inflow stream's squared coefficient of variation as

$$
C _ {a} ^ {2} = \frac {1 3 . 2}{2 2 . 8} 5. 0 + \frac {3 . 6}{2 2 . 8} 3. 0 + \frac {6 . 0}{2 2 . 8} 2. 2 = 3. 9 4 7
$$

》 To compute the mean and standard deviation of the inter-arrival times, remember that mean rates and mean times are reciprocals:

$$
\begin{array}{l} E \left[ T _ {a} \right] = \frac {1}{2 2 . 8} \mathrm {h r} = 2. 6 3 \mathrm {m i n}, \quad \text {a n d} \\ V [ T _ {a} ] = 3. 9 4 7 (2. 6 3 ^ {2}) = 2 7. 3 0 \mathrm {m i n} ^ {2} \\ \end{array}
$$

> Find the inter-arrival time distribution parameters for the following system:

### Diagram Description: Merge Node Calculation

This diagram presents a practical exercise in queueing theory, specifically focusing on the superposition (merging) of two independent arrival streams into a single node.

**1. Input Streams:**
*   **Stream 1 (Top):**
    *   Arrival Rate ($\lambda_1$): **1 j/h** (jobs/hour)
    *   Squared Coefficient of Variation ($C_1^2$): **1.365**
*   **Stream 2 (Bottom):**
    *   Arrival Rate ($\lambda_2$): **3 j/h**
    *   Squared Coefficient of Variation ($C_2^2$): **2.095**

**2. Merge Process:**
*   The two streams converge into a central oval labeled **"Merge"**, representing the aggregation of the workloads.

**3. Output Stream (To be calculated):**
*   **$\lambda = ?$**: The total aggregate arrival rate.
*   **$C_a^2 \text{ (merged)} = ?$**: The squared coefficient of variation for the new merged arrival process.

# Solution

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
> Parts receive an unqualified pass from the inspector with probability 0.8 and they are then sent to Workstation 6 to continue the manufacturing process   
> Approximately 18% of the time, a part has a partial pass of the quality check and is sent to Workstation 10 for rework
>  And approximately 2% of the time, a part completely fails the test and is sent to the hazardous waste station for disposal which is designated as Workstation 99
>  The throughput rate for Workstation 5 is 7 jobs per hour and the coefficient of variation for the inter-departure times is 3

### Diagram Description: Routing (Splitting) Node Calculation

This diagram illustrates a **splitting** process within a queueing network. The output of one workstation is probabilistically distributed to multiple subsequent stations, a critical concept in industrial operations and network analysis.

**1. Source Stream (Departures from Node 5):**
*   Departure Rate ($\lambda$): **7**
*   Squared Coefficient of Variation ($C_d^2$): **3**

**2. Routing Probabilities:**
The departure stream is split into three distinct paths, with the sum of all probabilities equaling 1 ($0.8 + 0.18 + 0.02 = 1$):
*   To Node 6: $p = 0.8$
*   To Node 10: $p = 0.18$
*   To Node 99: $p = 0.02$

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

# Exercise

> Analyze the network reported in the figure and find the arrival parameters at workstations 2, 3, and 4

### Diagram Description: Queueing Network (Splitting and Merging)

This diagram illustrates a multi-node queueing network, representing a system where workstation outputs are probabilistically routed and multiple arrival streams are merged.

**1. Node 1 (Source Departures):**
*   Departure Rate ($\lambda_d(1)$): **6 j/h**
*   Squared Coefficient of Variation ($C_d^2(1)$): **3**

**2. Routing (Splitting) from Node 1:**
*   The flow from Node 1 is split equally between Node 2 and Node 3.
*   Probability to Node 2: **0.5**
*   Probability to Node 3: **0.5**

**3. Node 2 (Merge and Process):**
*   **External Arrivals**: Rate $\gamma = 2 \text{ j/h}$, Variability $C_a^2 = 1$.
*   **Workstation Parameters**: Utilization $u_2 = 0.8$, Service Variability $C_s^2(2) = 1$.

**4. Node 3 (Process):**
*   **Workstation Parameters**: Utilization $u_3 = 0.8$, Service Variability $C_s^2(3) = 1$.

**5. Node 4 (Destination):**
*   Receives the converging departure streams from both Node 2 and Node 3.

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


$$
\lambda_ {a} = \sum_ {i = 1} ^ {n} \lambda_ {i}
$$

$$
C _ {a} ^ {2} = \sum_ {i = 1} ^ {n} \frac {\lambda_ {i}}{\lambda_ {a}} C _ {i} ^ {2}
$$

$$
\lambda (2) = 2 + 3 = 5 \text{ j/h}
$$

$$
C _ {a} ^ {2} (2) = \frac{2}{5} \cdot 1 + \frac{3}{5} \cdot 2 = 1.6
$$

$$
C _ {d} ^ {2} (2) = \left(1 - 0.8 ^ {2}\right) \cdot 1.6 + 0.8 ^ {2} \cdot 1 = 1.22
$$

$$
C _ {d} ^ {2} (G / G / 1) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} C _ {s} ^ {2}
$$

> Workstations 3 analysis: only one flow split from workstation 2 and departure variability computation

$$
\begin{array}{l} \lambda_ {a} = p \lambda_ {d} \\ C _ {a} ^ {2} = p C _ {d} ^ {2} + 1 - p \\ \end{array}
$$

$$
\lambda (3) = 3 \text{ j/h}
$$

$$
C _ {a} ^ {2} (3) = 2
$$

$$
C _ {d} ^ {2} (3) = \left(1 - 0.8 ^ {2}\right) \cdot 2 + 0.8 ^ {2} \cdot 1 = 1.36
$$

$$
C _ {d} ^ {2} (G / G / 1) \approx \left(1 - u ^ {2}\right) C _ {a} ^ {2} + u ^ {2} C _ {s} ^ {2}
$$

Workstations 4 analysis: merging two input flows

$$
\lambda_ {a} = \sum_ {i = 1} ^ {n} \lambda_ {i} \quad C _ {a} ^ {2} = \sum_ {i = 1} ^ {n} \frac {\lambda_ {i}}{\lambda_ {a}} C _ {i} ^ {2}
$$

$$
\lambda (4) = 3 + 5 = 8 \mathrm {j / h}
$$

$$
C _ {a} ^ {2} (4) = \frac{5}{8} \cdot 1.22 + \frac{3}{8} \cdot 1.36 = 1.27
$$

# General Network Approximation Model

To address a general factory network connection topology, the possibilities of external flows into any one of the workstations must be considered along with job branching for rework purposes,splitting of the output from a workstation to different next workstations, etc.

> Workstation inflows can come from a variety of sources, external as well as other workstations within the factory,and this is handled by the flow merging mechanism   
> Probabilistic branching of workstation outflow requires departure stream splitting mechanics

Since there is no longer sequential flows, parameter dependencies are also not sequential so that equations relating the parameters will have to be solved simultaneously instead of sequentially

# General Network Approximation Model

### Diagram Description: Queueing Network with Feedback Loops

This diagram illustrates a two-node queueing network characterized by probabilistic feedback loops. This structure is typically used to model rework, quality inspections, or iterative service processes.

**1. Node 1 Flow:**
*   Receives external arrivals at a rate of **$\gamma$**.
*   Receives internal feedback (rework) from Node 2 with a probability of **$\beta$**.
*   The total, effective arrival rate at Node 1 is denoted as **$\lambda_1$**.
*   100% of the output from Node 1 flows directly into Node 2.

**2. Node 2 Flow:**
*   Receives the full departure stream from Node 1.
*   Receives self-feedback (units returning immediately to the same node for reprocessing) with a probability of **$\alpha$**.
*   The total, effective arrival rate at Node 2 is denoted as **$\lambda_2$**.

**3. System Departure:**
*   Units successfully exit the network from Node 2 with a probability of **$(1 - \alpha - \beta)$**. This ensures that the sum of all outbound routing probabilities from Node 2 equals 1. 

> With a non-serial network,determining the arrival stream characteristics is more complicated than for the serial systems   
> Since the flow rate into Workstation 1 is not known as yet, the inflow into Workstation 2 cannot be computed directly   
> The resolution requires that all of the flow rates are computed simultaneously   
The problem can be solved by means of a system of linear equations

$$
\lambda_ {1} = \gamma + \beta \lambda_ {2},
$$

$$
\lambda_ {2} = \lambda_ {1} + \alpha \lambda_ {2},
$$

# General Network Approximation Model

The parameters α ,β ,Y are all known data   
> This linear system rearranged in terms of the unknowns on the left side of the equality is

$$
\begin{array}{l} \lambda_ {1} - \beta \lambda_ {2} = \gamma , \\ - \lambda_ {1} + (1 - \alpha) \lambda_ {2} = 0. \\ \end{array}
$$

The solution to this system can be written in matrix form as

$$ \begin{pmatrix} \lambda_1 \\ \lambda_2 \end{pmatrix} = \begin{pmatrix} 1 & -\beta \\ -1 & 1-\alpha \end{pmatrix}^{-1} \begin{pmatrix} \gamma \\ 0 \end{pmatrix} $$

# General Network Approximation Model

> Consider a network consisting of workstations numbered from 1 to n.
> The switching rule for the network is defined by an nxn matrix P= (pij), where pi,j is the probability that an arbitrary job leaving Workstation i will be routed directly to Workstation j.
> The matrix P is called the routing matrix for the network.
> Row iof the routing matrix consists of the probabilities relating to the splitting of the outflow from Workstation iinto the various resultant successor Workstations j.
> The jth column of the matrix represents the probabilities that jobs leaving the various workstations go to Workstation j

# General Network Approximation Model

Define γi as the external inflow rate and λi as the total inflow rate into Workstation i   
The total rate into Workstation imust satisfy the following equation:

$$
\lambda_ {i} = \gamma_ {i} + \sum_ {k = 1} ^ {n} p _ {k i} \lambda_ {k}, \text {f o r} i = 1, \dots , n
$$

or in standard matrix form:

$$
\boldsymbol {\lambda} = \boldsymbol {P} ^ {T} \boldsymbol {\lambda} + \boldsymbol {\gamma}
$$

# General Network Approximation Model

Consider a general network of n workstations with switching rule defined by the routing matrix P and assume that the sum of at least one row of P is strictly less than one (i.e., jobs exit the network from at least one workstation)   
> Let γ = (γ1，· · · ,γn) denote a vector consisting of the mean arrival rate of jobs from an external source to the workstations.   
> Let λ= (λ1，· · ·,λn) be the unknown vector denoting mean arrival rates of all jobs to the workstations   
The vector λ is given by

$$
\boldsymbol {\lambda} = \left(I - P ^ {T}\right) ^ {- 1} \boldsymbol {\gamma}
$$

where I is an nxn identity matrix.

# Example

Consider the factory network of workstations depicted in the figure,with the noted branching probabilities and an external flow rate into the first workstation of 5 jobs per hour.   
The system of equations defining the workstation total arrival rates are

$$
\begin{aligned}
\lambda_1 &= 5 + 0.10\lambda_2 + 0.05\lambda_3 \\
\lambda_2 &= 0 + 0.75\lambda_1 \\
\lambda_3 &= 0 + 0.25\lambda_1 + 0.90\lambda_2
\end{aligned}
$$

### Diagram Description: Three-Node Queueing Network with Feedback

This diagram illustrates a complex open queueing network consisting of three interconnected workstations (nodes), featuring probabilistic routing and multiple feedback loops.

**1. External Input:**
*   External arrivals enter the system solely at **Node 1** with a rate of **$\gamma = 5$**.

**2. Routing from Node 1:**
*   To Node 2: **$3/4$** (75%)
*   To Node 3: **$1/4$** (25%)

**3. Routing from Node 2:**
*   To Node 3: **$9/10$** (90%)
*   Feedback to Node 1: **$1/10$** (10%)

**4. Routing from Node 3:**
*   System Departure: **$19/20$** (95% of the flow successfully exits the system).
*   Feedback to Node 1: **$1/20$** (5% of the flow requires rework and is sent back to the first node).

This system rearranged is

$$
\begin{aligned}
1\lambda_1 - 0.10\lambda_2 - 0.05\lambda_3 &= 5 \\
-0.75\lambda_1 + 1\lambda_2 + 0\lambda_3 &= 0 \\
-0.25\lambda_1 - 0.90\lambda_2 + 1\lambda_3 &= 0
\end{aligned}
$$

which has the unique solution

$$
\lambda_ {1} = 5. 6 9 0, \lambda_ {2} = 4. 2 6 7, \lambda_ {3} = 5. 2 6 3
$$

Thus, the first workstation receives 5.690 jobs per hour; 5 of these from the external source and the remaining 0.690 jobs from Workstations 2 and 3   
> The second workstation receives 4.267 jobs per hour, all of these from Workstation 1   
> The third workstation receives a total of 5.263 jobs per unit time as the combined inflow from Workstations 1 and 2

# Exercises

> Compute the mean flow rates for the systems ilustrated in the two figures

### Figure 1 - Diagram Description: Three-Node Feed-Forward Queueing Network

This diagram illustrates a straightforward, three-node open queueing network characterized by a feed-forward flow, meaning there are no rework or feedback loops.

**1. External Input:**
*   External arrivals enter the system exclusively at **Node 1** with an incoming rate of **10**.

**2. Routing from Node 1 (Splitting):**
*   The departure stream from Node 1 is probabilistically split into two paths:
    *   Routed to Node 2: **3/4** (75% of the flow).
    *   Routed directly to Node 3: **1/4** (25% of the flow).

**3. Routing from Node 2:**
*   A single arrow connects Node 2 to Node 3, indicating that all processed units from Node 2 are routed entirely to **Node 3**.

**4. System Departure (Node 3):**
*   Node 3 acts as the final collection and processing stage for both streams (the direct flow from Node 1 and the processed flow from Node 2). The arrow pointing outward from Node 3 indicates that all units successfully exit the system from this point.

### Figure 2 - Diagram Description: Three-Node Queueing Network with Multiple Feedback Loops

This diagram illustrates a complex three-node open queueing network featuring probabilistic routing and two distinct feedback loops returning to the first node.

**1. External Input:**
*   External arrivals enter the system exclusively at **Node 1** with an incoming rate of **10**.

**2. Routing from Node 1:**
*   To Node 2: **3/4**
*   To Node 3: **1/4**

**3. Routing from Node 2:**
*   To Node 3: **2/3**
*   Feedback to Node 1: **1/3** (rework/loop back to the start).

**4. Routing from Node 3:**
*   System Departure: **4/5** (units successfully exiting the system).
*   Feedback to Node 1: **1/5** (rework/loop back to the start).

# Solution (1)

| | | |
|---|---|---|
| 0 | 3/4 | 1/4 |
| 0 | 0 | 1 |
| 0 | 0 | 0 |

$$
\lambda_1 = 10
$$

$$
\lambda_2 = \frac{3}{4} \cdot \lambda_1 = 7.5
$$

$$
\lambda_3 = \lambda_2 + \frac{1}{4} \cdot \lambda_1 = 10
$$

# Solution (2)

| | | |
|---|---|---|
| 0 | 3/4 | 1/4 |
| 1/3 | 0 | 2/3 |
| 1/5 | 0 | 0 |

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

> Analyze the network reported in the figure and find the arrival parameters at all the workstations

### Diagram Description: Three-Node Network with Superposition and Splitting

This diagram illustrates an open, feed-forward queueing network with three nodes. It demonstrates both the splitting of a departure stream and the merging (superposition) of multiple arrival streams.

**1. Node 1:**
*   **External Arrivals:** Rate $\gamma_1 = 3 \text{ j/h}$, Variability $C_a^2(0,1) = 1$.
*   **Workstation:** Utilization $u_1 = 0.7$, Service Variability $C_s^2(1) = 1$.
*   **Routing:** The departure stream is split equally, with $0.5$ (50%) going to Node 2 and $0.5$ (50%) going directly to Node 3.

**2. Node 2:**
*   **External Arrivals:** Rate $\gamma_2 = 2 \text{ j/h}$, Variability $C_a^2(0,2) = 1$.
*   **Workstation:** Utilization $u_2 = 0.9$, Service Variability $C_s^2(2) = 1$.
*   **Routing:** All processed units flow entirely to Node 3.

**3. Node 3:**
*   Acts as the final destination node, merging the direct flow from Node 1 and the processed flow from Node 2.

# Solution

Routing matrix

| | | |
|---|---|---|
| 0 | 0.5 | 0.5 |
| 0 | 0 | 1 |
| 0 | 0 | 0 |

# Solution

Workstation 1

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

Workstation 2

$$
\lambda _ {2} = \gamma _ {2} + 0.5 \cdot \lambda _ {1} = 2 + 0.5 \cdot 3 = 3.5 \text{ j/h}
$$

$$C _ {a} ^ {2} (2) = \frac{\gamma _ {2}}{\lambda _ {2}} C _ {a} ^ {2} (0,2) + \frac{\lambda _ {1} p _ {12}}{\lambda _ {2}} \left(p _ {12} C _ {d} ^ {2} (1) + 1 - p _ {12}\right) = \frac{2}{3.5} \cdot 1 + \frac{3 \cdot 0.5}{3.5} \cdot (0.5 \cdot 1 + 1 - 0.5) = 1$$

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (2) = 1
$$

# Solution

Workstation 3

$$
\lambda _ {3} = 0.5 \cdot \lambda _ {1} + \lambda _ {2} = 0.5 \cdot 3 + 3.5 = 5 \text{ j/h}
$$

$$
C _ {a} ^ {2} (3) = \frac{\lambda _ {1} p _ {13}}{\lambda _ {3}} \left(p _ {13} C _ {d} ^ {2} (1) + 1 - p _ {13}\right) + \frac{\lambda _ {2} p _ {23}}{\lambda _ {3}} \left(p _ {23} C _ {d} ^ {2} (2) + 1 - p _ {23}\right) = \frac{3 \cdot 0.5}{5} (0.5 \cdot 1 + 1 - 0.5) + \frac{3.5}{5} \cdot 1 = 1
$$

# General Network Approximation Model

To analyze a general network, the mean arrival rate into each workstation is first determined 
Then workstation utilization factors are calculated since these depend on the just computed arrival rates   
A Finally the squared coefficients of variation for the arrival streams are computed either by a successive substitution iteration or by finding the inverse matrix   
At this point, the network can be decomposed and each workstation treated individually   
Finally, these results are combined to estimate the performance characteristics of the system as a whole

# Example

> Consider a factory that consists entirely of single-server workstations with service time data for each workstation given in the Table   
> The arrivals from an external source enter into the factory at the first workstation, and the arivals are exponentially distributed with a mean rate of 5 jobs per hour   
The topology of the factory is shown in the figure   
> Find the mean cycle time for jobs, the factory inventory levels,and the workloads of each workstation

| Workstation $i$ | $E[T_s(i)]$ | $C_s^2(i)$ |
| :---: | :---: | :---: |
| 1 | 7.80 min | 1.0355 |
| 2 | 7.80 min | 1.7751 |
| 3 | 9.60 min | 0.3906 |
| 4 | 3.84 min | 2.4414 |

### Diagram Description: Four-Node Network with Complex Feedback Routing

This diagram illustrates an advanced open queueing network comprising four nodes, characterized by parallel processing paths and a complex feedback distribution from the final node.

**1. External Input:**
*   External arrivals enter the system exclusively at **Node 1** with an incoming rate of **5**.

**2. Routing from Node 1 (Splitting):**
*   To Node 2: **2/3**
*   To Node 3: **1/3**

**3. Routing from Nodes 2 and 3 (Merging):**
*   All processed units from **Node 2** flow directly into **Node 4** (implicit probability of 1).
*   All processed units from **Node 3** flow directly into **Node 4** (implicit probability of 1).

**4. Routing from Node 4 (Feedback & Departure):**
*   Node 4 acts as an inspection/rework dispatcher. The flows are distributed as follows:
    *   Feedback to Node 2: **2/10**
    *   Feedback to Node 3: **3/10**
    *   Feedback to Node 1: **1/10** (long loop back to the start).
    *   System Departure: **4/10** (implicit, calculated as $1 - 2/10 - 3/10 - 1/10$).

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

| Workstation $i$ | $\lambda_i$ | $E[T_s(i)]$ | $u_i$ | $u_i^2$ | $1 - u_i^2$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 6.250/hr | 0.130 hr | 0.8125 | 0.6602 | 0.3398 |
| 2 | 6.667/hr | 0.130 hr | 0.8667 | 0.7512 | 0.2488 |
| 3 | 5.833/hr | 0.160 hr | 0.9333 | 0.8710 | 0.1290 |
| 4 | 12.50/hr | 0.064 hr | 0.8000 | 0.6400 | 0.3600 |

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

| Workstation $i$ | $E[T_s(i)]$ | $C_s^2(i)$ |
| :---: | :---: | :---: |
| 1 | 0.086 | 1.3521 |
| 2 | 0.110 | 0.8264 |
| 3 | 0.080 | 1.5625 |

### Diagram Description: Three-Node Feed-Forward Queueing Network

This diagram illustrates an open queueing network with three workstations arranged in a feed-forward configuration (no feedback loops).

**1. External Input:**
*   External arrivals enter the system at **Node 1** with a rate of **10**.

**2. Routing from Node 1 (Splitting):**
*   To Node 2: **3/4** (75% of the total flow).
*   To Node 3: **1/4** (25% of the total flow).

**3. Routing from Node 2:**
*   All units processed at Node 2 flow directly into **Node 3** (implicit probability of 1).

**4. System Departure:**
*   All units exit the system after being processed at **Node 3**.

# Solution

$P$:

| | | |
|:---:|:---:|:---:|
| 0 | 3/4 | 1/4 |
| 0 | 0 | 1 |
| 0 | 0 | 0 |

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

$$
\mathbf {W I P} _ {T O T} = 1 8. 2 5 4 \mathrm {j}
$$

$$
\mathrm {C T} _ {\text {T O T}} = \frac {\mathrm {W I P} _ {\text {T O T}}}{\mathrm {T H}} = 1. 8 2 5 \mathrm {h}
$$
