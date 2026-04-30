# Analysis and Management of Production System

# Lesson 4: Variability of processing time

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

> Approximation of the cycle time in a queue system consists of four parameters

> coefficient of variation of the inter-arrival time process (Ca2)   
>squared coefficient of variation of the service time process (C22)   
>machine utilization (u)   
>mean service time (E[Tsl)

$$
C T _ {q} (G / G / 1) = \frac {\left(C _ {a} ^ {2} + C _ {s} ^ {2}\right)}{2} \left(\frac {u}{1 - u}\right) E [ T _ {s} ]
$$

# Introduction

> Reducing one of the variability components, Ca2or C2，willreduce the cycle time in the queue   
> Example: consider a single machine system with the following values

$$
C _ {a} ^ {2} = 1, C _ {s} ^ {2}, = 1, u = 0. 8, E [ T s ] = 2 h r
$$

Thus the cycle time in the queue CTq is

$$
C T _ {q} = \frac {(1 + 1)}{2} \left(\frac {0 . 8}{1 - 0 . 8}\right) 2 \mathrm {h r} = 8 \mathrm {h r}
$$

# Introduction

> If Cs2 is reduced by 10% to 0.9, the resulting cycle time is 7.6 hours (a reduction of 5%)   
> If C is not changed, to accomplish the same reduction in cycle time would take a reduction in machine utilization from O.8 to 0.7917

$$
\begin{array}{l} \frac {(1 + 1)}{2} \left(\frac {u}{1 - u}\right) 2 = 7. 6, \\ 4. 6 u = 3. 6, \\ u = 0. 7 9 1 7 \\ \end{array}
$$

》 A 50% reduction in the service time variability would reduce the cycle time measure to 6 hours   
V The equivalent machine utilization factor for 6 hours given the original system parameters is 0.75   
V Either of these changes would result in a cycle time in the queue of 6 hours which is a 25% reduction from the original 8 hours

# Introduction

> Reducing variability is equivalent to reducing the machine utilization   
Y A reduction of utilization with a constant arrival rate implies a reduction of mean processing time (i.e., an increase in the mean processing rate)   
Very important to concentrate on reducing variability for the inter-arrival and service time processes since these reductions are like finding “free" machine capacity

# Main contributors to processing time variability

V Natural processing time variability - the variability evident in the time it takes to actually process a specific job type   
Random breakdowns and repairs during processing - the variability of the time between breakdowns and the variability of the time to repair a broken machine   
Operator unavailability - can induce random delays in the time a job spends“in control of” a machine (machine and job are available, but the operator is busy serving another machine/job)   
Job class setup and take-down times - the time caused by a job-type change on a machine (change-over time generally occurs at the end of processing of one job type and the starting of a different job class)

# Natural process time variability

V Consider a job with processing time random variable,T, with known mean and variance parameters E[T] and V[T], respectively   
If the processing time is made up of several separate tasks, it is possible to reduce the total processing time variability by reducing the variability of the individual tasks

> Sub-tasks that can be studied separately or possibly assigned to different workers for manual task operations

# Natural process time variability

# Example:

Consider that the natural processing time random variable T is made up of three separate (independent) sub-tasks

$$
E [ T ] = E [ T _ {1} ] + E [ T _ {2} ] + E [ T _ {3} ]
$$

$$
V [ T ] = V [ T _ {1} ] + V [ T _ {2} ] + V [ T _ {3} ]
$$

$$
C ^ {2} [ T ] = \frac {V [ T ]}{E [ T ] ^ {2}}.
$$

Additionally consider that these three sub-processes times are independent and identically distributed random variables so that

$$
E [ T ] = 3 E [ T _ {1} ]
$$

$$
V [ T ] = 3 V [ T _ {1} ]
$$

# Natural process time variability

The individual processing time random variables Ti, for i= 1, 2, 3, have distributional parameters

$$
E [ T _ {i} ] = \frac {E [ T ]}{3}
$$

$$
V [ T _ {i} ] = \frac {V [ T ]}{3}
$$

the squared coefficient of variation of the individual tasks are

$$
C ^ {2} [ T _ {i} ] = \frac {V [ T _ {i} ]}{E [ T _ {i} ] ^ {2}} = \frac {V [ T ] / 3}{E [ T ] ^ {2} / 3 ^ {2}} = 3 C ^ {2} [ T ], \text {f o r} i = 1, 2, 3
$$

If the total processing time is made up of three identical sub-tasks, then the squared coefficient of variation of the individual tasks is actually three times that of the total time squared coefficient of variation

V Consider a natural processing time that is exponentially distributed with a mean time of 3 hours   
The squared coefficient of variation C2[T] is equal to 1   
V Assume that this job consists of three distinct but identically distributed sub-tasks   
These sub-tasks have processing times random variables Ti that have distributional parameters E[Ti] = 1 h and V[Ti] = 3 h², for each i   
V After further study of the three sub-tasks,it is found that the variability of each task can be reduced and the resulting times are i.i.d. exponentially distributed times each with a mean of one hour (it is assumed that these variabilities can be reduced while the mean processing times remain unchanged)   
C2[Ti] = 1, for each sub-task i

$$
E [ T _ {i} ] = 1
$$

$$
C ^ {2} [ T _ {i} ] = 1
$$

$$
V [ T _ {i} ] = 1
$$

The total processing time random variable now has parameters

$$
E [ T ] = \sum_ {i = 1} ^ {3} E [ T _ {i} ] = 3
$$

$$
V [ T ] = \sum_ {i = 1} ^ {3} V [ T _ {i} ] = 3
$$

$$
C ^ {2} [ T ] = \frac {3}{3 ^ {2}} = 1 / 3.
$$

Total processing time variability reduced to 1/3 of its original value   
》 This reduction willin turn reduce the associated workstation cycle time in the queue by 1/6

Extra processing capability has been found   
Y This new system is equivalent in cycle time response to a system with a faster processing time

# Exercise

Consider a processing time, T, with measured parameters E[T]= 6 h and C2[7] =2, that has 4 i.i.d. sub-tasks   
Determine E[T] and C2[T] for the sub-tasks   
Y Assume that the variability of each sub-task can be reduced (identically) so that C2[T] = 2   
> Determine the squared coeffcient of variation of the total processing time and the percentage improvement over the “old” processing time variabiity

# Solution

$$
E[T] = 6 \text{ h}, \qquad c^2[CT] = 2, \text{ 4 subtasks}
$$

$$
E[T_i] = \frac{6}{4} = 1.5 \text{ h}
$$

$$
V[T] = c^2[T] \cdot E^2[T] = 2 \cdot 36 = 72 \text{ h}^2
$$

$$
V[T_i] = \frac{72}{4} = 18 \text{ h}^2
$$

$$
c^2[T_i] = \frac{V[T_i]}{E^2[T_i]}
= \frac{18}{1.5^2}
= 8
$$

$$
\text{If } c^2[T_i] = 2
$$

$$
V[T_i] = c^2[T_i] \cdot E^2[T_i]
= 2 \cdot 1.5^2
= 4.5 \text{ h}^2
$$

$$
V[T] = 4.5 \cdot 4 = 18 \text{ h}^2
$$

$$
c^2[T] = \frac{V[T]}{E^2[T]}
= \frac{18}{36}
= 0.5
$$

$$
\frac{1}{4} \text{ of original } c^2
$$

# Machine breakdown

Major source of processing time variability is due to the breakdown of an operating machine and the subsequent delay while the machine is being repaired

Job might not be recoverable (i.e., lost)   
Y Job might require additional processing before resumption of “normal" processing   
V Job might not be effected by the breakdown and normal processing can resume immediately after the repair is complete (as if the breakdown never occurred)

V Only the latter case is considered

> Although for the second case,the additional processing time needed to resume service can be included in the machine repair time so that the second and third situations become equivalent

# Effective processing time

The effective processing time， Te, refers to the time that a job has control of the processor until the time at which the job releases the processor so that it is available to begin work on another job   
The job can complete processing without a breakdown interruption, the machine could breakdown once during service, the machine could breakdown twice during service, etc.   
So the effective processing time is also a random variable given by

$$
T _ {e} = T + \sum_ {i = 1} ^ {N} R _ {i}
$$

where T is the normal (uninterrupted) processing time random variable, the Ri's are the (i.i.d.) repair time random variables,and N is the random number of failures during the service time T

# Availability

The availability, a, of a processor that is subject to failures is the long-run average fraction of time that the processor is available for processing jobs

$$
a = \frac {E [ F _ {1} ]}{E [ F _ {1} ] + E [ R _ {1} ]}
$$

where F.,Fz,... and R.,R2.... are random variables representing successive failure times and successive repair times,respectively, for the processor

# Mean and variance of effective time

Hopp and Spearman developed an expression for the mean and variance of the effective service time for processors that are less than 100% reliable under the assumption that failures are exponentially distributed:

$$
E [ T _ {e} ] = \frac {E [ T _ {s} ]}{a}
$$

$$
C _ {e} ^ {2} = C ^ {2} \left[ T _ {e} \right] = C _ {s} ^ {2} + \frac {\left(1 + C ^ {2} \left[ R _ {1} \right]\right) a (1 - a) E \left[ R _ {1} \right]}{E \left[ T _ {s} \right]}
$$

# Example

Consider a single workstation with jobs arriving according to a Poisson process (i.e., exponential inter-arrival times) with an average time between arrivals of 75 minutes   
? Initially we ignore the fact that the machine at the workstation is not 100% reliable and observe that the normal processing time is described by an Erlang type-3 distribution with mean of 58 minutes   
Thus:

E[Ta] =75 min and Ca² = 1   
E[Ts]= 58 min and C² = 1/3   
>u = 58/75 = 0.7733   
>CTq = 132 min

# Example

> Now let's consider that the time between machine breakdowns is exponentially distributed with a mean time of 3 hours,and the repair time is distributed according to a lognormal distribution with a mean time of 30 min and a standard deviation of 15 min

$$
\begin{array}{l} a = \frac {E [ F _ {1} ]}{E [ F _ {1} ] + E [ R _ {1} ]} \\ = \frac {3}{3 + 1 / 2} = 0. 8 5 7 1 4 \\ \end{array}
$$

$$
E [ T _ {e} ] = \frac {E [ T ]}{a} = 6 7. 6 7 \mathrm {m i n}
$$

$$
C ^ {2} \left[ T _ {e} \right] = \frac {1}{3} + \frac {(1 + 0 . 2 5) (0 . 8 5 7 1 4) (1 - 0 . 8 5 7 1 4) (3 0)}{5 8} = 0. 4 1 2 5
$$

$$
u = 6 7. 6 7 / 7 5 = 0. 9 0 2 3
$$

$$
C T _ {q} = \frac {(1 + 0 . 4 1 2 5)}{2} \left(\frac {0 . 9 0 2 3}{1 - 0 . 9 0 2 3}\right) 6 7. 6 7 \min = 4 4 1 \min
$$

# Considerations

> It can be noticed that the inclusion of machine failure in the model results in over a threefold increase in the mean waiting time

? Ignoring failures can create significant errors in performance measures

V This increase is due to two factors

1） Machine failures cause an increase in the effective utilization factor   
2) Machine failures cause an increase in the service variability

As the utilization factor approaches one, small changes in the factor will have major changes in waiting times,and in this case, the majority of the increase in waiting times is due to the utilization factor increase

> Only about 5%-6% of the increase is due to the increase in service variability

# Example 2

> Let's consider a line consisting of 2 machines (M1, M2) with mean process time E[Ts]= 15 min and natural standard deviation equal to δs=3,35 min. Both machines undergoes failures which limit their availability (but in different ways according to the following table). Which machine is to be preferred?

| Machine | Failure type | E[F] | E[R] | C[R] |
| :--- | :--- | :--- | :--- | :--- |
| **M1** | Long and infrequent | 744 min | 248 min | 1 |
| **M2** | Short and frequent | 114 min | 38 min | 1 |

# Example 2

V Both the machines have the same availability, and thus the same effective processing time:

$$
a = 0. 7 5 \quad E [ T _ {e} ] = E [ T _ {s} ] / a = 1 5 / 0. 7 5 = 2 0 \mathrm {m i n}
$$

Effective capacity of the machines:

$$
\mu_ {\mathrm {e}} = 1 / \mathrm {E} [ \mathrm {T} _ {\mathrm {e}} ] = 3 \mathrm {i t e m / h r}
$$

V The two machines seem to be equivalent by using the mean values of effective processing time,but we also need to consider the variability:

$$
M 1: \quad c _ {e} ^ {2} = 0, 0 5 + (1 + 1) 0, 7 5 (1 - 0, 7 5) 2 4 8 / 1 5 = 6, 2 5 \quad \rightarrow H V
$$

$$
\mathrm {M} 2: \quad c _ {\mathrm {e}} ^ {2} = 0, 0 5 + (1 + 1) 0, 7 5 (1 - 0, 7 5) 3 8 / 1 5 = 1, 0 \quad \rightarrow \mathrm {M V}
$$

# Exercise 1

Consider a job with processing time distribution parameters E[T] = 3 hours and C² = 2   
V The machine breakdown and repair time characteristic parameters are:

E[F]=7 hr and C²[F]= 1  
E[R]= 1 hr and C²[R] = 1

> Find the parameters of the effective processing time: E[Te], V[Te],and C²[Te]

# Solution

$$
\quad E [ T _ {S} ] = 3 h \quad C _ {s} ^ {2} = 2
$$

$$
E [ F ] = 7 h \quad C ^ {2} (F) = 1, \quad E [ R ] = 1 h \quad C ^ {2} (R) = 1
$$

$$
a = \frac {E (F)}{E (F) + E (R)} = \frac {7}{7 + 1} = 0. 8 7 5
$$

$$
E [ T _ {e} ] = \frac {E [ T _ {s} ]}{a} = \frac {3}{0 . 8 7 5} = 3. 4 3 h
$$

$$
Ce ^ {2} = C s ^ {2} + \frac {(1 + c ^ {2} [ R ]) a (1 - a) E [ R ]}{E [ T s ]} = 2 + \frac {(1 + 1) \cdot 0 . 8 7 5 (1 - 0 . 8 7 5) \cdot 1}{3} = 2. 0 7 3
$$

$$
V [ Te] = Ce ^ {2} \cdot E[Te] ^ {2} = 2, 0 7 3 \cdot 3, 4 3 ^ {2} = 2 4, 3 9
$$

# Exercise 2

V Consider M/M/1/$\infty$ system with a server that has exponential time between breakdowns and exponential repair times   
Given an arrival rate of 5 jobs per hour, a service rate of 7 jobs per hour, a breakdown rate of once per hour and a mean repair time of 15 minutes, compute the system performance measures of WIP, CTs, and ths

# Solution

$$
a = \frac{E[F_1]}{E[F_1] + E[R_1]}
= \frac{1}{1 + 0.25}
= 0.8
$$

$$
E[T_e] = \frac{E[T]}{a}
= \frac{0.143}{0.8}
= 0.18 \text{ h}
$$

$$
C^2[T_e]
= 1 + \frac{[(1+1)\cdot 0.8 \cdot (1-0.8)\cdot 0.25]}{0.143}
= 1.56
$$

$$
u = 5 \cdot 0.18 = 0.9
$$

$$
CT_{q} = \left(\frac{1+1.56}{2}\right)\left(\frac{0.9}{1-0.9}\right)\cdot 0.18 = 2.07
$$

$$
CT = CT_q + E[T_e]
= 2.07 + 0.18
= 2.25 \text{ h}
$$

$$
WIP = TH \cdot CT
= 5 \cdot 2.25
= 11.25
$$

# Exercise 3

V Consider an M/M/1/3 system with a server that has exponential time between breakdowns (α rate) and exponential repair times (β rate)

Develop the state diagram of the system

Consider an arrival rate of 5 jobs per hour, a service rate of 4 jobs per hour, a breakdown rate of once per hour,and a mean repair time of 10 minutes

Determine the steady-state probabilities for the system states   
V Compute the system performance measures of WIPs, CTs and ths   
V Compute the proportion of the time that the machine is idle, down (i.e., under repair), and processing

# Solution

### Visual Diagram: State-Transition Network for a System with Failures and Repairs
- **Component Type**: Continuous-Time Markov Chain (CTMC) / State-transition diagram.
- **Logic**: Represents a finite capacity system ($N=3$) subject to random failures and repair processes.

---

#### 1. State Definitions
The diagram consists of 7 discrete states organized into two levels:
*   **State 0**: The system is empty and idle.
*   **Level P (Processing)**: States **1P, 2P, 3P**, representing the functioning system with 1, 2, or 3 jobs present.
*   **Level B (Broken/Blocked)**: States **1B, 2B, 3B**, representing the system in a failed state with 1, 2, or 3 jobs present.

#### 2. Transition Rate Dynamics
The transitions between states are governed by four parameters:

*   **Arrivals ($\lambda$)**:
    *   Moves the system from state $n$ to $n+1$.
    *   Occurs in both the functional level ($0 \to 1P$, $1P \to 2P$, $2P \to 3P$) and the failed level ($1B \to 2B$, $2B \to 3B$).
*   **Service ($\mu$)**:
    *   Represents job completion and the reduction of system load.
    *   Transitions occur only in the upper (P) level: $3P \to 2P$, $2P \to 1P$, and $1P \to 0$.
*   **Failures ($\alpha$)**:
    *   Vertical downward transitions from the functional level (P) to the failed level (B): $1P \to 1B$, $2P \to 2B$, $3P \to 3B$.
*   **Repairs ($\beta$)**:
    *   Vertical upward transitions from the failed level (B) to the functional level (P): $1B \to 1P$, $2B \to 2P$, $3B \to 3P$.

#### 3. System Constraints
*   **Maximum Capacity**: The system is limited to 3 jobs. There are no arrival arcs ($\lambda$) exiting states **3P** or **3B**, indicating that further arrivals are blocked and lost.
*   **Service Interruption**: During a failure (Level B), no $\mu$ arcs are present, signifying that production is suspended until the repair ($\beta$) is complete.
*   **Steady-State Balance**: The flow rate entering a state must equal the flow rate exiting it. 
    *   *Example for node 2P*: $(\lambda + \mu + \alpha) p_{2P} = \lambda p_{1P} + \mu p_{3P} + \beta p_{2B}$.

# Solution

| State | Probability |
| :--- | :--- |
| **P0** | 0.14 |
| **P1P** | 0.17 |
| **P1B** | 0.02 |
| **P2P** | 0.23 |
| **P2B** | 0.03 |
| **P3P** | 0.33 |
| **P3B** | 0.08 |

# Solution

Th= 5*(1-(0.33+0.08)) = 2.95 j/h   
WIP= (0.17+0.02)+2*(0.23+0.03)+3*(0.33+0.08) = 1.94   
CTs= WIP/Th = 0.66 h   
Idle: P0 = 0.14   
Processing: P1P+P2P+P3P = 0.17+0.23+0.33 = 0.73   
V Down: P1B+P2B+P3B = 0.02+0.03+0.08 = 0.13
