# Analysis and Management of Production System

# Lesson 7: Batch models

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Introduction

Grouping individual jobs into batches is a strategy frequently used in industry

> Purpose of sharing transportation between workstations (pallet movement)
> Sharing machine setup by products of the same time, even though the items are processed individually   
> Multiple service capacity resource such as ovens (heat treatment, plating processes)

# Introduction

The batching phenomenon has an impact on downstream processing stations   
E.g., consider the batch move concept where, say k, items are grouped together for the convenience of moving them to a subsequent single unit processing station.

> Items arrive at the next workstation k at a time, so the workstation might be idle for a while and then instantaneously have a queue of waiting units
> Increased cycle times and larger WiPlevels at the downstream workstation
> The batch process causes an increased delay because units must wait for the completion of other units before they can be grouped and continue processing

# Introduction

Models are developed for various forms of batching, so that the benefits and costs of the grouping process under consideration can be quantified   
For the setup sharing situation,there willbe a trade-off between the cycle time increase and the setup time savings due to batching

# Batching for transport

Batch move model structure

> Items are grouped in batches of size k at the completion of processing at a workstation that processes single units   
> Items wait in the incomplete batch until the proper quantity has been reached   
> The full batch is transported to the next workstation, where they are processed individually

Basic assumption: transportation time is negligible, thus not explicitly considered

> If transportation time is significant, it can be approximated by considering the transporter as a separate workstation

### Logical Flow Analysis: Transfer Batch Formation

The diagram describes a material handling process divided into four main phases:

1. **Single Unit Server (First station):** Parts (represented by the individual circles) arrive at the system and are processed individually by the first machine.
2. **Batch Forming:** Upon exiting the first machine, parts do not immediately move to the next station. Instead, they are accumulated in a container until a predetermined size is reached (in this example, a batch of 4 units). This accumulation generates a waiting time called **Wait-to-Batch Time** (the first processed part must wait for the completion of the last part in the batch before the transfer occurs).
3. **Queued Batches:** The completed batches are moved to the second station, where they wait their turn in a queue. At this stage, the entity queuing is the entire batch, not the individual parts.
4. **Single Unit Server with Holding Area (Second station):** When it is a batch's turn, it enters a buffer area at the machine (*Holding Area*). Since the second machine is also a single unit server, it picks and processes one part at a time from the batch. This mechanism generates a second waiting time, the **Wait-in-Batch Time** (the last part of the batch must wait for all previous parts to be processed before its own turn).

* **Transfer Batches vs. Process Batches:** The diagram clearly highlights the use of *transfer* batches. Although the machines process the parts individually (unit process batch), the movement between work centers occurs in groups.
* **Impact on Cycle Time (CT):** The introduction of batching logic structurally increases the Cycle Time of the individual part due to the addition of waiting times for batch formation and consumption (Wait-to-Batch and Wait-in-Batch).
* **Managerial Trade-off:** The increase in Cycle Time is generally accepted to optimize the inefficiencies and costs associated with *material handling*, reducing the overall number of transports between stations.

# Batching for transport

Cycle time depends on three components:

Batch forming time   
Queue time for batches
> Dependent on mean arrival rate of batches and squared coefficient of variation of the inter-arrival batch times
Processing time delay due to the individual processing

# Batch Forming Time

Consider a batch formed by k arriving items   
Let Td be the random variable denoting the time between departures from the source workstation that are to be batched for transportation to the destination workstation   
The inter-arrival rate of individuals $\lambda(I)$ to the destination workstation in the absence of batching is given by

$$
\lambda \left(\mathsf {I}\right) = \frac {1}{\mathsf {E} [ \mathsf {T d} ]}
$$

# Batch Forming Time

The inter-arrival time of batches T(B) is a random variable given by the Sum of k individual inter-departure times

$$
\mathsf {T} (\mathsf {B}) = \mathsf {T} _ {\mathrm {d}, 1} + \mathsf {T} _ {\mathrm {d}, 2} + \ldots + \mathsf {T} _ {\mathrm {d}, \mathrm {k}}
$$

Since the individual inter-departure times are independent and identically distributed (i.i.d.) random variables, the expected value of the batch interarrival time is

$$
\mathsf {E} [ \mathsf {T} (\mathsf {B}) ] = \mathsf {k E} [ \mathsf {T} _ {\mathsf {d}} ]
$$

The arrival rate of batches to the destination workstation, $\lambda(B)$, is

$$
\lambda (\mathsf {B}) = \frac {1}{\mathsf {E} [ \mathsf {T} (\mathsf {B}) ]} = \frac {1}{\mathrm {k E} [ \mathrm {T d} ]} = \frac {\lambda (\mathsf {I})}{\mathsf {k}}
$$

# Batch Forming Time

The variance of the batch inter-arrival times at the destination workstation is

$$
\mathsf {V} [ \mathsf {T} (\mathsf {B}) ] = \mathsf {V} [ \mathsf {T} _ {\mathsf {d}, 1} + \mathsf {T} _ {\mathsf {d}, 2} + \ldots + \mathsf {T} _ {\mathsf {d}, \mathsf {k}} ] = \mathsf {k V} [ \mathsf {T} _ {\mathsf {d}} ]
$$

Thus, the squared coefficient of variation, C²[T(B)], of the batch interarrival times can be computed from the squared coefficient of variation of the individual inter-arrival times by

$$
\mathrm {C} ^ {2} [ \mathrm {T} (\mathrm {B}) ] = \frac {\mathrm {V} [ \mathrm {T} (\mathrm {B}) ]}{\mathrm {E} [ \mathrm {T} (\mathrm {B}) ] ^ {2}} = \frac {\mathrm {K V} [ \mathrm {T d} ]}{(\mathrm {k E} [ \mathrm {T} _ {\mathrm {d}} ]) ^ {2}} = \frac {\mathrm {C} ^ {2} [ \mathrm {T d} ]}{\mathrm {k}}
$$

# Batch Forming Time

The delay that an individual item encounters when being placed into a batch depends on its position among the k batched items   
First departing item must wait for k-1 items to depart before the batch is ready for transportation to the destination workstation

> The delay of the first item is $D_{1}= T_{d,2}+...+T_{d,k}$

The second item forming the new batch has to wait for k-2 succeeding departures   
> The delay of the second item is $D_{2}= T_{d,3}+...+T_{d,k}$
Average delay is the expected value of the sum of all these delays divided by the batch size k

$$
E [ D ] = \frac {E [ D _ {1} + D _ {2} + \cdots + D K _ {1} , D K ]}{K} = \frac {(K - 1) E [ T _ {d} ] + (K - 2) E [ T _ {d} ] + \cdots + 1 E [ T _ {d} ] + 0 E [ T d ]}{k} =
$$

$$
\frac {(\mathrm {k} - 1) \mathrm {k} / 2 \mathrm {E} [ \mathrm {T d} ]}{\mathrm {k}} = \frac {(\mathrm {k} - 1)}{2} \mathrm {E} [ \mathrm {T _ {d}} ]
$$

# Batch Queue Waiting Time

The cycle time for the recipient workstation for the batch move situation has two distinct components: the queue time and the service time.   
Let $\lambda(B)$ be the arrival rate of the batches to the queue is with corresponding squared coefficient of variation $C^2[T(B)]$ 
Let the random variable $T_{s}(B)$ be the service time to process all of the items within the batch,which is given by

$$
\mathsf {T} _ {\mathsf {s}} (\mathsf {B}) = \mathsf {T} _ {\mathsf {s}, 1} (\mathsf {I}) + \mathsf {T} _ {\mathsf {s}, 2} (\mathsf {I}) + \ldots + \mathsf {T} _ {\mathsf {s}, \mathsf {k}} (\mathsf {I})
$$

# Batch Queue Waiting Time

The processing times $T_{s,i}(I)$ are independent and identically distributed random variables with known mean $E[T_{s}(I)]$ and squared coefficient of variation $C^2[T_{s}(I)]$   
Thus, the batch service time characteristics can be computed from the individual item data as

$$
\mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] = \mathsf {k E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ]
$$

$$
\mathsf {C} ^ {2} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] = \frac {\mathsf {C} ^ {2} [ \mathsf {T} \mathsf {s} (\mathsf {I}) ]}{\mathsf {k}}
$$

Utilization factor for the workstation

$$
\mathsf {u} (\mathsf {B}) = \lambda (\mathsf {B}) \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] = \frac {\lambda_ {(\mathsf {I})}}{\mathsf {k}} (\mathsf {k E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ]) = \lambda (\mathsf {I}) \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ] = \mathsf {u} (\mathsf {I})
$$

# Batch Queue Waiting Time

The expected cycle time in the queue for individuals in a move batch is identical to the cycle time in the queue for the workstation operating in a single item mode

$$
\begin{array}{l} \mathsf {C T} _ {\mathsf {q}} (\mathsf {B}) = \left(\frac {\mathsf {C} ^ {2} [ \mathsf {T} _ {\mathsf {a}} (\mathsf {B}) ] + \mathsf {C} ^ {2} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ]}{2}\right) \left(\frac {\mathsf {u} (\mathsf {B})}{1 - \mathsf {u} (\mathsf {B})}\right) \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] = \\ = (\frac {\left(\frac {C ^ {2} [ T _ {a} (I) ]}{k}\right) + \left(\frac {C ^ {2} [ T _ {s} (I) ]}{k}\right)}{2}) \left(\frac {u (I)}{1 - u (I)}\right) k E [ T _ {s} (I) ] = \\ = \left(\frac {(C ^ {2} [ \mathrm {T a (I)} ]) + (C ^ {2} [ \mathrm {T s (I)} ])}{2}\right) \left(\frac {\mathrm {u (I)}}{1 - \mathrm {u (I)}}\right) E [ T _ {\mathrm {s}} (\mathrm {I}) ] = C T _ {\mathrm {q}} (\mathrm {I}) \\ \end{array}
$$

# Batch Processing time delay

The delay (D) is equal to the item processing time plus the processing times of allitems that were part of the batch and are processed before the item in question

$$
\begin{array}{l} \mathsf {D} = \mathsf {T} _ {\mathsf {s}, 1} + (\mathsf {T} _ {\mathsf {s}, 1} + \mathsf {T} _ {\mathsf {s}, 2}) + (\mathsf {T} _ {\mathsf {s}, 1} + \mathsf {T} _ {\mathsf {s}, 2} + \mathsf {T} _ {\mathsf {s}, 3}) + \ldots + (\mathsf {T} _ {\mathsf {s}, 1} + \mathsf {T} _ {\mathsf {s}, 2} + \ldots + \mathsf {T} _ {\mathsf {s}, \mathsf {k - 1}}) = \\ = (k - 1) T _ {s, 1} + (k - 2) T _ {s, 2} + \dots + (1) T _ {s, k - 1} \\ \end{array}
$$

The expected value for this delay is

$$
E [ D ] = \{(k - 1) + (k - 2) + \dots + (1) \} E [ T _ {s} ]
$$

The sum of the first k-1 integers equals k(k -1)/2, so the average extra delay associated with an item waiting its turn within the batch for processing is

$$
\frac {\mathrm {E} [ \mathrm {D} ]}{\mathrm {k}} = \frac {\left(\frac {\mathrm {k} (\mathrm {k} - 1)}{2}\right) \mathrm {E} [ \mathrm {T s} ]}{\mathrm {k}} = \frac {(\mathrm {k} - 1)}{2} \mathrm {E} [ \mathrm {T s} ]
$$

# Total cycle time

Assume a pure serial system layout with Workstation i sending jobs directly to Workstation jby batch moves of size k and alljobs are processed one-at-a-time at j   
The mean system cycle time per job at Workstation j is given by

$$
\begin{array}{l} \mathrm {C T (j)} = \frac {(k - 1)}{2} \mathrm {E [ T _ {a} (i) ]} + \left(\frac {C _ {d} ^ {2} (i) + C _ {s} ^ {2} (j)}{2}\right) \left(\frac {u}{1 - u}\right) \mathrm {E [ T s (j) ]} + \frac {(k - 1)}{2} \mathrm {E [ T _ {s} (j) ]} + \\ + \mathrm {E} [ \mathrm {T s} (\mathrm {j}) ] \\ \end{array}
$$

where the batch formation time after processing at Workstation i is considered part of the cycle time at Workstation j

# Total cycle time

There are times in which a batch has already been formed so that the basic arrival rate is in terms of batches to a workstation in which processing is by individual job   
In this case there would be batch formation times so the mean system cycle time per job at the workstation is

$$
\mathrm {C T} _ {\mathrm {s}} = \left(\frac {\mathrm {k C} _ {\mathrm {a}} ^ {2} (\mathrm {B}) + \mathrm {C} _ {\mathrm {s}} ^ {2} (\mathrm {I})}{2}\right) \left(\frac {\mathrm {u}}{1 - \mathrm {u}}\right) \mathrm {E} [ \mathrm {T s} (\mathrm {I}) ] + \frac {(\mathrm {k} + 1)}{2} \mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {I}) ]
$$

where the utilization is u=kE[Ts(I)]/E[Ta(B)]

# Variability of departures

Where the batch arrives, if the workstation is busy processing items, the first item willonly experience a service time inter-departure delay   
All other inter-departure times for items in the batch are merely separated by service time delays   
The general approach for modeling departures is to approximate them by a renewal process   
Thus, the inter-departure time squared coefficient of variation for individuals for the batch-move server for a single machine workstation is

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (\mathsf {I}) = \mathrm {k C} _ {\mathrm {a}} ^ {2} (\mathsf {B}) (1 - \mathsf {u} ^ {2}) + (\mathsf {k} - 1) (1 - \mathsf {u}) ^ {2} + \mathsf {u} ^ {2} \mathsf {C} _ {\mathrm {s}} ^ {2} (\mathsf {I})
$$

# Variability of departures

In the context of a pure serial system layout, with Workstation i sending jobs directly to Workstation j by batch moves of size k, the squared coefficient of variation of inter-departures of individuals from workstation j is given by

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (\mathfrak {j}) = \mathsf {C} _ {\mathrm {d}} ^ {2} (\mathfrak {i}) (1 - \mathfrak {u j} ^ {2}) + (\mathfrak {k} - 1) (1 - \mathfrak {u j}) ^ {2} + \mathfrak {u j} ^ {2} \mathsf {C} _ {\mathrm {s}} ^ {2} (\mathfrak {j})
$$

# Example

Consider two workstations in series consist of only one machine that process items at a rate of 3 per hour, with a squared coefficient of variation of the inter-arrivals of 2   
The first workstation processes jobs on average in 0.25 hours with SCV of 2   
The second workstation processes jobs on average in 0.25 hours with SCV of 1.5   
The batch size is k=4   
Find CT and cd of the second workstation

# Example

Since the SCV of the inter-arrivals and service process of the first workstation are the same, the SCV of the inter-departures will also be the same, e.g., 2   
Mean of inter-departure of individuals from first workstation is 1/3   
Utilization factor for the second workstation is u2 = 3(0.25)= 0.75   
Average cycle time per item:

$$
\mathrm {C T} (2) = \frac {4 - 1}{2} \left(\frac {1}{3}\right) + \frac {2 + 1 . 5}{2} \frac {0 . 7 5}{0 . 2 5} (0. 2 5) + \frac {4 - 1}{2} 0. 2 5 + 0. 2 5 = 2. 4 3 7 5 \mathrm {h r}
$$

Squared coefficient of variation of the inter-departure times:

$$
\mathrm {C} ^ {2} _ {\mathrm {d}} (2) = 2 \left(1 - 0. 7 5 ^ {2}\right) + 3 \left(1 - 0. 7 5\right) ^ {2} + 0. 7 5 ^ {2} (1. 5) = 1. 9 0 6 3
$$

# Exercise

Consider two workstations in series that consist of only one machine   
The items are moved from the first to the second workstation in batches of 10 items   
Both workstations process items at a rate of 1 j/h, with a squared coefficient of variation of processing times of 0.16   
The arrival rate is 0.9 j/h and the inter-arrval time are exponentially distributed   
Find the total CT of the line

# Solution
### Two-Station Production System Layout with Batching

The image displays a block diagram (typical of an Excel spreadsheet layout) of a production line consisting of two machines with an intermediate batching process.

#### 1. Arrival Process
Parts enter the system individually (represented by the small circle and the arrow entering a buffer).
*   **ra:** `0,9 pz/h` (Arrival rate, $r_a$, equal to 0.9 parts per hour).
*   **Ca²:** `1` (Squared coefficient of variation of interarrival times, $C_a^2$. A value of 1 typically indicates Markovian/exponential arrivals).

#### 2. Machine 1 (M1)
Represented by the light blue box "M1". This is the first processing station.
*   **Ce²:** `0,16 h` (Squared coefficient of variation of the effective process time. *Technical note: the image reports "h" as the unit of measurement, although $C_e^2$ is typically a dimensionless parameter*).
*   **te:** `1 h/pz` (Effective process time, $t_e$, equal to 1 hour per part).
*   **U1:** `0,90` (Utilization of Machine 1. This is mathematically consistent, as $U = r_a \cdot t_e = 0.9 \cdot 1 = 0.9$).

#### 3. Batch Formation and Transfer (Batching Area)
Upon exiting M1, parts do not go directly to M2. Instead, they fall into a container (graphically represented as a bucket) to form a batch. An arrow indicates the transfer of this batch to the queue of the next machine.
*   **K:** `10 pz` (Batch size, indicating that parts are grouped into sets of 10 before being transferred or made available to the next station).

#### 4. Machine 2 (M2)
Represented by the green box "M2". It picks parts from the buffer that received the batch, processes them, and then they exit the system (indicated by the rightward arrow).
*   **Ce²:** `0,16 h` (Squared coefficient of variation of the effective process time, identical to M1).
*   **te:** `1 h/pz` (Effective process time, $t_e$, identical to M1).
*   **U2:** `0,9` (Utilization of Machine 2, identical to M1. This makes sense since the average incoming flow and process times are the same, ensuring a balanced line).

$$
\mathrm {C T} (1) = \frac {1 + 0 . 1 6}{2} \frac {0 . 9}{0 . 1} * 1 + 1 = 6. 2 2 \mathrm {h}
$$

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (1) = (1 - 0. 9 ^ {2}) 1 + 0. 9 ^ {2} (0. 1 6) = 0. 3 2
$$

$$
\mathrm {C T} (2) = \frac {1 0 - 1}{2} \left(\frac {1}{0 . 9}\right) + \frac {0 . 3 2 + 0 . 1 6}{2} \frac {0 . 9}{0 . 1} (1) + \frac {1 0 - 1}{2} 1 + 1 = 1 2. 6 6 \mathrm {h}
$$

$$
\mathrm {C T (l i n e)} = 6. 2 2 + 1 2. 6 6 = 1 8. 8 8 \mathrm {h}
$$

# Batching for Setup Reduction

### Analytical Model of a Batching System with Setup

The image illustrates the mathematical parameterization of a workstation operating with batching logic. The diagram is divided into three logical sections:

#### 1. Arrival Process
Individual items (represented by the magenta circles) arrive at the system to be grouped.
*   **$\lambda(I)$**: Item arrival rate.
*   **$Ca^2(I)$**: Squared coefficient of variation of interarrival times, which describes the variability of the incoming flow.

#### 2. Queued Batches
*   **$k$**: Batch size. In the graphical example, items are grouped into batches of $k=4$ units. 
*   The full containers represent the physical queue of batches waiting to be processed by the machine.

#### 3. Server & Setup
This section breaks down the total time a batch spends at the machine into its two fundamental components:
*   **$E[R]$ and $C^2[R]$**: Parameters associated with the entire batch. They indicate the Expected Value ($E[R]$) and the Squared Coefficient of Variation ($C^2[R]$) of the **Setup** time. This is the time required to prepare the machine before it starts processing the items in the batch.
*   **$E[Ts(I)]$ and $Cs^2(I)$**: Parameters associated with the single item. They indicate the Expected Value of the service time ($E[Ts(I)]$) and its Squared Coefficient of Variation ($Cs^2(I)$) . The server (highlighted in orange) processes the items one at a time, picking them from the batch.

When a single-unit processing workstation must be setup before processing a group of items of the same job type, a batch of size k is formed to spread the batch setup time across k jobs rather than one job   
There are many choices for the batch size for each item and a batch quantity should be chosen that balances the setup time reduction against the increased batching delay as the batching quantity is increased

# Batching for Setup Reduction

Items arive to the workstation one at-a-time with known mean rate $\lambda(I)= 1/E[T_{a}(I)]$ and known inter-arival time SCV $C^2_{a}(I)$   
Each batch has a service time that consists of the setup time random variable Rplus kindividualrandom services $T_{s,1}$ ,..., $T_{s,k}$   
The expected processing time and variance for the batch are

$$
\mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] = \mathsf {E} [ \mathsf {R} ] + \mathsf {k E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ]
$$

$$
\mathsf {V} [ \mathsf {T} _ {\mathrm {s}} (\mathsf {B}) ] = \mathsf {V} [ \mathsf {R} ] + \mathsf {k V} [ \mathsf {T} _ {\mathrm {s}} (\mathsf {I}) ]
$$

# Batching for Setup Reduction

The squared coefficient of variation for the batch service time is then computed from the definition

$$
\mathrm {C} ^ {2} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {B}) ] = \frac {\mathrm {V} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {B}) ]}{\mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {B}) ] ^ {2}} = \frac {\mathrm {C} ^ {2} [ \mathrm {R} ] \mathrm {E} [ \mathrm {R} ] ^ {2} + \mathrm {k C} ^ {2} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {I}) ] \mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {I}) ] ^ {2}}{\mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {B}) ] ^ {2}}
$$

Thus, the utilization factor accounting for the setup time is

$$
\mathsf {u} = \lambda (\mathsf {I}) \frac {\mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ]}{\mathsf {k}} = \lambda (\mathsf {I}) (\frac {\mathsf {E} [ \mathsf {R} ]}{\mathsf {k}} + \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ])
$$

The cycle time in the queue, CTq, is the same as that developed for transport batches

# Batching for Setup Reduction

Given the new values for the batch times and the utilization factor, the mean cycle time per job at the workstation,where a setup operation is performed before any of the individual jobs within each batch are processed, is given by

$$
\mathsf {C T} (\mathsf {I}) = \frac {(\mathsf {k} - 1)}{2} \mathsf {E} [ \mathsf {T a} (\mathsf {I}) ] + (\frac {(\frac {\mathsf {C} ^ {2} \mathsf {a} (\mathsf {I})}{\mathsf {k}} + \mathsf {C} _ {\mathsf {s}} ^ {2} (\mathsf {B})}{2}) (\frac {\mathsf {u}}{1 - \mathsf {u}}) \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] + \frac {(\mathsf {k} + 1)}{2} \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ] + \mathsf {E} [ \mathsf {R} ]
$$

E[R] and $C^2[R]$ are the mean and squared coefficient of variation of the setup operation

# Batching for Setup Reduction

The SCV for the inter-departure times from a workstation that processes jobs one-at-a-time with a batch set-up is

$$
\begin{array}{l} \mathsf {C} ^ {2} [ \mathsf {T} _ {\mathsf {d}} (\mathsf {I}) ] = \mathsf {k C} ^ {2} [ \mathsf {T} _ {\mathsf {a}} (\mathsf {B}) ] (1 - \mathsf {u} ^ {2}) + \mathsf {k} (1 - \mathsf {u}) ^ {2} - 1 + \frac {2 \mathsf {k} (1 - \mathsf {u}) (\mathsf {E} [ \mathsf {R} ] + \mathsf {E} [ \mathsf {T s} (\mathsf {I}) ])}{\mathsf {E} [ \mathsf {T a} (\mathsf {B}) ]} + \\ + \frac {\mathrm {k (E [ R ] ^ {2} (C ^ {2} [ R ] + 1) + k E [ T _ {s} (I) ] ^ {2} (C ^ {2} [ T _ {s} (I) + 1 ] + 2 E [ R ] E [ T s (I) ]}}{\mathrm {E [ T a (B) ] ^ {2}}} \\ \end{array}
$$

# Example

Consider finding the batch size k that results in the minimum cycle time for a single product with E[Ts(I)]= 0.1 hours,C²(I)= 1.5, E[R]= 0.2 hours and C²[R]= 1   
Assume that the arrival rate of individual units is λ(I)= 5.666 per hour (E[Ta(I)]= 0.1765 hours), and C²a(I)= 3.0

The workstation utilization is given by

$$
\mathsf {u} = \lambda (\mathsf {B}) \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] = \frac {5 . 6 6 6}{\mathsf {k}} (0. 2 + 0. 1 \mathsf {k})
$$

The feasibility condition is that k must be large enough so that u<1; hence, k must be greater or equal to 3

# Example

The following table displays the computed information for each batch size over the range of k ∈ {3,..., 9}.

| $k$ | $u$ | $E[T_s(B)]$ | $C^2[T_s(B)]$ | $CT_s$ |
| :---: | :---: | :---: | :---: | :---: |
| 3 | 0.944 | 0.5 | 0.340 | 6.254 |
| 4 | 0.850 | 0.6 | 0.278 | 2.460 |
| 5 | 0.793 | 0.7 | 0.235 | 1.974 |
| **6** | **0.755** | **0.8** | **0.203** | **1.860** |
| 7 | 0.728 | 0.9 | 0.179 | 1.863 |
| 8 | 0.708 | 1.0 | 0.160 | 1.917 |
| 9 | 0.692 | 1.1 | 0.145 | 1.998 |

The optimal batch size occurs at K=6 using the minimum CTs as the criterion

# Batch Service

### Analytical Model of a Batching System

The image illustrates the mathematical parameterization of a workstation where items are grouped into batches before processing. The diagram is divided into three logical sections:

#### 1. Arrival Process
Individual items (represented by the magenta circles) arrive at the system to be grouped.
*   **$\lambda(I)$**: Item arrival rate.
*   **$Ca^2(I)$**: Squared coefficient of variation of the item interarrival times.

#### 2. Batch Formation and Queue
*   **$k$**: Batch size. Items are grouped into batches of size $k$ (in the graphical example, $k=4$).
*   The image shows an incomplete batch being formed (which generates the Wait-to-Batch time) and a physical queue of completed batches waiting to be processed.

#### 3. Server
In this model, the batch itself is treated as the single entity being served by the workstation.
*   **$E[Ts(B)]$**: Expected Batch Service Time. It represents the expected total time required to process the entire batch once it enters the server.
*   **$Cs^2(B)$**: Squared Coefficient of Variation of the batch service time, representing the statistical variability of the processing time for the whole batch.

A batch server is a processor that can process several jobs simultaneously   
Service cannot start until a full batch is available

# Batch Service

Consider a single-server workstation that processes jobs in fixed batches of size k   
Jobs arrive individuallyand are placed in batches before proceeding into the workstation   
The mean system cycle time per job at the workstation is given by

$$
\mathsf {C T} _ {\mathsf {s}} = \frac {(\mathsf {k} - 1)}{2} \mathsf {E} [ \mathsf {T a} (\mathsf {I}) ] + \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] + \left(\frac {\mathsf {C} ^ {2} [ \mathsf {T} _ {\mathsf {a}} (\mathsf {B}) ] + \mathsf {C} ^ {2} [ \mathsf {T s} (\mathsf {B}) ]}{2}\right) \left(\frac {\mathsf {u} (\mathsf {B})}{1 - \mathsf {u} (\mathsf {B})}\right) \mathsf {E} [ \mathsf {T s} (\mathsf {B}) ]
$$

Where $E[T_{s}(B)]$ is the mean batch processing time and $u(B) = \lambda(B)E[T_{s}(B)]$. This formula needs to be adjusted according to the nature of the batch formation process.

# Batch Service

At the end of the processing, the batch is unloaded and the individual items are moved into their subsequent workstations   
The SCV of the inter-departures of individuals from the batch service workstation is

$$
C _ {d} ^ {2} (I) = k C _ {d} ^ {2} (B) + k - 1
$$

Which can be written in terms of the basic workstation characteristics for batches as

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (\mathsf {I}) = \mathsf {k} [ (1 - \mathsf {u} ^ {2}) \mathsf {C} _ {\mathrm {a}} ^ {2} (\mathsf {B}) + \mathsf {u} ^ {2} \mathsf {C} _ {\mathrm {s}} ^ {2} (\mathsf {B}) ] + \mathsf {k} - 1
$$

# Example

Consider a batch-processing workstation in which arivals occur from another batch server in batches of size 5 with a mean rate of 3 batches per hour and an SCV of batch inter-arival times of 0.75   
The SCV of the batch service time is also 0.75 with a workstation utilization of 84%   
The average time each job spends in the workstation is thus given by

$$
C T = 1 6. 8 + \frac {0 . 7 5 + 0 . 7 5}{2} \times \frac {0 . 8 4}{1 - 0 . 8 4} \times 1 6. 8 = 8 2. 9 5 \mathrm {m i n}
$$

> 16.8 is the service time given in minutes and is obtained by dividing the utilization factor by the arrival rate   
> The first term in the previous cycle time equation is not used since the arrivals were already in batches

# Example

Since the SCV of the inter-arrival times and the service times are the same, it is also the SCV of the inter-departure times for batches   
The approximation for the inter-departure SCV of individuals is given by

$$
\mathrm {C} ^ {2} _ {\mathrm {d}} (\mathrm {I}) = 5 (1 - 0. 8 4 2) (0. 7 5) + 0. 8 4 2 (0. 7 5) + 4 = 7. 7 5
$$

# Batch line exercise

A production line consists of 2 workstations and produces 40 pieces per day with an 8-hour shift; the inter-arrival times are distributed exponentially   
The first station consists of 3 parallel machines with a process time of 30 minutes with a standard deviation of 15 minutes   
The second station is composed of a single machine with an average process time of 8 minutes,which appears to be very worn and has breakdowns every hour with repair times that are between 4 and 12 minutes   
The pieces leaving the line are transferred in batch of 40 pieces to a second line located in another plant about 30 km away   
In this plant the line is made up of two single-machine workstations with variable average process times of 8 minutes and 10 minutes respectively   
Calculate the resulting cycle time (excluding the time due only to the transfer)

# Solution

Uniform Probability Distribution   
Expected value of x

$$
E (x) = (a + b) / 2
$$

Variance of x

$$
V a r (x) = (b - a) ^ {2} / 1 2
$$

### Probability Density Function (PDF) of a Continuous Uniform Distribution

The image illustrates the Probability Density Function (PDF) for a continuous uniform distribution, typically denoted as $U(a,b)$. 

#### Graphical Elements:
*   **Axes**: The horizontal axis represents the random variable $x$, while the vertical axis represents the probability density $f_X(x)$.
*   **Interval $[a, b]$**: The parameters $a$ and $b$ represent the minimum and maximum boundaries of the distribution on the x-axis.
*   **Constant Density**: Within the interval from $a$ to $b$, the probability density is constant and equal to $\frac{1}{b-a}$. This forms a rectangular shape.
*   **Zero Density**: For any value of $x$ outside the interval $[a, b]$ (i.e., $x < a$ or $x > b$), the probability density is exactly 0 (indicated by the blue lines lying flat on the x-axis).

#### Mathematical Significance:
*   The constant height of $\frac{1}{b-a}$ ensures that the total area under the PDF curve (the area of the rectangle, calculated as base $\times$ height, or $(b-a) \times \frac{1}{b-a}$) is exactly equal to 1. This is a fundamental requirement for all valid probability density functions.

# Solution

### WS1: Performance Parameters

| Parameter | Symbol | Value | Unit |
| :--- | :--- | :--- | :--- |
| **Arrival rate** | $\lambda(I)$ | 5 | job/hours |
| **Arrival SCV** | $c_a^2(I)$ | 1 | |
| **Parallel machines** | $c$ | 3 | |
| **Service Time** | $E[T_s]$ | 0.5 | hours |
| **Service SCV** | $c_s^2(I)$ | 0.25 | |
| | | | |
| **Utilization** | $u$ | 0.833333 | |
| **Cycle Time (CT)** | $CT$ | **0.947819** | h |
| **Departure SCV** | $c_d^2(I)$ | 0.699297 | |

---

### Key Formulas (G/G/c Approximation)

These are the standard approximation formulas used in Factory Physics to calculate the performance of a multi-machine workstation with general arrival and service distributions.

**1. Time in Queue ($CT_q$) Approximation:**
This is the VUT (Variability-Utilization-Time) equation adapted for multiple servers (often referred to as Kingman's formula approximation for $G/G/c$ queues). Note that the total Cycle Time is the sum of the time in queue and the service time ($CT = CT_q + E[T_s]$).

$$
CT_q(G/G/c) \approx \left(\frac{c_a^2 + c_s^2}{2}\right) \left(\frac{u^{\sqrt{2c+2}-1}}{c(1-u)}\right) E[T_s]
$$

**2. Departure SCV ($c_d^2$) Approximation:**
This formula calculates the variability of the output flow, which becomes the arrival variability ($c_a^2$) for the *next* workstation down the line. It demonstrates how pooling multiple machines ($c$) dampens the propagation of variability.

$$
C_d^2(G/G/c) \approx (1 - u^2) c_a^2 + u^2 \frac{c_s^2 + \sqrt{c} - 1}{\sqrt{c}}
$$

### Technical Analysis
*   **Utilization ($u$):** Calculated as the total arrival workload divided by the total available capacity: $u = \frac{\lambda \cdot E[T_s]}{c} = \frac{5 \cdot 0.5}{3} \approx 0.833$.
*   **Variability Dampening:** Because there are 3 parallel machines, the high arrival variability ($c_a^2 = 1$) is "smoothed out" by the low service variability ($c_s^2 = 0.25$), resulting in a departure variability ($0.699$) that is significantly lower than the arrival variability.

# Solution

### WS2: Performance Parameters

Here is the extraction of the data for Workstation 2 (WS2). Notice that this station is linked to the previous one, as its arrival parameters ($\lambda$ and $c_a^2$) match the departure parameters from WS1.

| Parameter | Symbol | Value | Unit |
| :--- | :--- | :--- | :--- |
| **Arrival rate** | $\lambda(I)$ | 5 | job/hours |
| **Arrival SCV** | $c_a^2(I)$ | 0.699297 | |
| **Parallel machines** | $c$ | 1 | |
| **Service Time** | $E[T_s]$ | 0.133333 | h |
| **Service SCV** | $c_s^2(I)$ | 1 | |
| | | | |
| **MTBF (Mean Time Between Failures)** | $E[F]$ | 1 | h |
| **MTTR (Mean Time To Repair)** | $E[R]$ | 0.133333 | h |
| **Repair Time Variance** | $Var[R]$ | 0.001481 | h² |
| **Repair Time SCV** | $c_R^2$ | 0.083333 | |
| | | | |
| **Availability** | $a$ | 0.882353 | |
| **Effective Service Time** | $E[T_e]$ | 0.151111 | h |
| **Effective SCV** | $c_e^2(I)$ | 1.112457 | |
| | | | |
| **Utilization** | $u$ | 0.755556 | |
| **Cycle Time (CT)** | $CT$ | **0.57422** | h |
| **Departure SCV** | $c_d^2(I)$ | 0.935155 | |
| | | | |
| **Batch forming size** | $k$ | 40 | |
| **Batch forming CT** | | 3.9 | h |

---

### Key Formulas (Failures and Effective Processing)

WS2 introduces machine breakdowns (preemptive outages), which inflate both the average processing time and its variability. 

**1. Effective SCV ($C_e^2$) Approximation:**
This formula calculates the "effective" variability of the machine, factoring in the disruptions caused by random failures and repairs. It clearly shows how outages strictly increase the baseline service variability ($C_s^2$).

$$
C_e^2 = C^2[T_e] = C_s^2 + \frac{(1 + C^2[R])a(1-a)E[R]}{E[T_s]}
$$

**2. Wait-to-Batch Time (Batch forming CT):**
At the end of WS2, parts are accumulated into a transfer batch of size $k=40$. The time spent waiting for the batch to form is calculated as:

$$
Wait\text{-}to\text{-}Batch = \frac{k - 1}{2 \cdot \lambda} = \frac{40 - 1}{2 \cdot 5} = \frac{39}{10} = 3.9 \text{ h}
$$

### Technical Analysis
*   **System Linking:** The input variability for WS2 ($c_a^2 = 0.699297$) is exactly the output variability ($c_d^2$) from WS1. This demonstrates a flow where WS1 feeds directly into WS2.
*   **Impact of Breakdowns:** Even though the natural service time is very fast ($E[T_s] \approx 0.133$ hours), the machine is only available $88.2\%$ of the time ($a = 0.882$). This inflates the effective time needed per part ($E[T_e] \approx 0.151$ hours) and introduces significant variability ($c_e^2$ increases from 1 to 1.112).
*   **Batching Delay:** The final batch forming process introduces a massive delay ($3.9$ hours) compared to the actual processing time at the station ($CT = 0.574$ hours). This highlights how large transfer batches can dominate the overall manufacturing lead time.

# Solution

### WS3: Performance Parameters

Here is the extraction of the data for Workstation 3 (WS3). As expected in a flow line, this station inherits its arrival variability from the departure variability of the previous station (WS2).

| Parameter | Symbol | Value | Unit |
| :--- | :--- | :--- | :--- |
| **Arrival rate** | $\lambda(I)$ | 5 | j/h |
| **Arrival SCV** | $c_a^2(I)$ | 0.935155 | |
| **Parallel machines** | $c$ | 1 | |
| **Service Time** | $E[T_s]$ | 0.133333 | h |
| **Service SCV** | $c_s^2(I)$ | 1 | |
| | | | |
| **Utilization** | $u$ | 0.666667 | |
| **Cycle Time (CT)** | $CT$ | **6.891354** | h |
| **Departure SCV** | $c_d^2(I)$ | 5.297308 | |

---

### Key Formulas (Linked Batching Model)

WS3 introduces the mathematical complexity of handling the transfer batch ($k=40$) that was formed at the end of WS2. The formulas below calculate the performance of station $j$ (WS3) which is fed by station $i$ (WS2).

**1. Cycle Time with Transfer Batches ($CT(j)$):**
This extended formula breaks down the total cycle time into four distinct components to account for the batching logic:
1.  **Wait-to-Batch time:** $\frac{(k-1)}{2}E[T_a(i)]$ (Time spent forming the batch at the previous station).
2.  **Time in Queue:** $\left(\frac{C_d^2(i) + C_s^2(j)}{2}\right)\left(\frac{u}{1-u}\right)E[T_s(j)]$ (The standard VUT equation for the queueing delay of the batch).
3.  **Wait-in-Batch time:** $\frac{(k-1)}{2}E[T_s(j)]$ (Time spent waiting for the preceding items in the same batch to be processed at the current station).
4.  **Service time:** $E[T_s(j)]$ (The actual processing time of the single item).

$$
CT(j) = \frac{(k-1)}{2}E[T_a(i)] + \left(\frac{C_d^2(i) + C_s^2(j)}{2}\right)\left(\frac{u}{1-u}\right)E[T_s(j)] + \frac{(k-1)}{2}E[T_s(j)] + E[T_s(j)]
$$

**2. Departure SCV with Batch Flow ($C_d^2(j)$):**
This formula calculates the variability leaving the station when items flow through in batches. 

$$
C_d^2(j) = C_d^2(i)(1 - u_j^2) + (k - 1)(1 - u_j)^2 + u_j^2 C_s^2(j)
$$

### Technical Analysis
*   **System Linking Confirmed:** The input variability for WS3 ($c_a^2 = 0.935155$) perfectly matches the output variability ($c_d^2$) calculated in WS2.
*   **The Penalty of Large Batches:** The cycle time jumps to almost **6.9 hours**, despite the machine being relatively fast and only utilized at 66.6%. The vast majority of this time is non-value-added waiting time caused by the $k=40$ batch size.
*   **Variability Explosion:** Notice the massive spike in the Departure SCV ($c_d^2 \approx 5.30$). The $(k - 1)$ term in the variance formula demonstrates mathematically how large transfer batches act as an amplifier for flow variability. This highly erratic output will severely degrade the performance of whatever workstation follows WS3 in the line.

# Solution

### WS4: Performance Parameters

Here is the extraction of the data for Workstation 4 (WS4), which represents the final stage of this production line.

| Parameter | Symbol | Value | Unit |
| :--- | :--- | :--- | :--- |
| **Arrival rate** | $\lambda(I)$ | 5 | j/h |
| **Arrival SCV** | $c_a^2(I)$ | 5.297308 | |
| **Parallel machines** | $c$ | 1 | |
| **Service Time** | $E[T_s]$ | 0.166667 | h |
| **Service SCV** | $c_s^2(I)$ | 1 | |
| | | | |
| **Utilization** | $u$ | 0.833333 | |
| **Cycle Time (CT)** | $CT$ | **2.790545** | h |
| | | | |
| **TOTAL CT** | | **11.20394** | h |

---

### Key Formulas (G/G/1 Approximation)

Since WS4 consists of a single machine ($c=1$) without internal batching, the calculation for the expected Cycle Time falls back to the standard VUT (Variability-Utilization-Time) equation for a G/G/1 queue (Kingman's formula).

$$
CT = CT_q + E[T_s] = \left(\frac{c_a^2 + c_s^2}{2}\right) \left(\frac{u}{1-u}\right) E[T_s] + E[T_s]
$$

### Technical Analysis

*   **The Propagation of Variability:** As predicted, the massive departure variability generated by WS3 ($c_d^2 \approx 5.30$, caused by the large transfer batch size of $k=40$) hits WS4 directly, becoming its arrival variability ($c_a^2 = 5.297308$). 
*   **The Variability Penalty:** Because of this highly erratic arrival pattern, WS4 suffers a severe performance degradation. Even though the machine is only utilized at 83.3% and takes merely 10 minutes to process a single part ($E[T_s] \approx 0.167$ hours), the average part spends over 2.5 hours just waiting in the queue, resulting in a workstation CT of almost **2.8 hours**.
*   **Total Manufacturing Lead Time:** The `TOTAL CT` of **11.20394 hours** is simply the sum of the individual Cycle Times across the entire routing ($CT_{tot} = 0.947819 + 0.57422 + 6.891354 + 2.790545$). This final tally demonstrates a classic Factory Physics insight: the vast majority of the time a part spends in a factory is non-value-added waiting time, heavily driven by batching dynamics and unbuffered variability.

# Batch Network Exercise

Consider three workstations: the first workstation is a setup-batch processing workstation, the second worksation uses oven-batch processing,and the third workstation is a single unit server with batch arrivals   
The arrival rate of individuals to the fisrt workstation is according to a Poisson process (SCV=1) with a mean rate of 5 units per hour   
The batch size of the first workstation is k=3   
The batch forming time in this analysis will be added to the cycle time for Workstation 1   
Items remain in batches until they exit the system, so allthe probabilistic branches are made on batches   
2/3 of the batches leaving Workstation 1 are routed to Workstation 2 and 1/3 go to Workstation 3   
From Workstation 2, 1/4 of the batches are finished (leave the system)and the remaining 3/4 are routed to Workstation 3   
At Workstation 3 items are separated and they leave as individuals

# Batch Network Exercise

The batch setup time has a mean of 12 minutes and a variance of 1080 minutes². The individual processing time has a mean of 6 minutes and a variance of 240 minutes²   
The oven batch processing time has a mean of 48 minutes and a service SCV of 0.75   
The mean and standard deviation of the individual processing times are 12 and 8.458 minutes

### Production System Layout with Routing and Mixed Batching

The image displays a flowchart of a manufacturing system featuring three distinct workstations (WS1, WS2, WS3), probabilistic routing, and different types of batch processing.

#### 1. Arrival and Batch Formation
*   Single items (represented by circles) arrive at the system.
*   **Batch Form:** Items are accumulated and grouped into a transfer batch of size **$k$** before moving to the first workstation.

#### 2. WS1: Setup Batch
*   The formed batches wait in a queue.
*   **Workstation 1 (Setup Batch):** This station operates on the batch. The "Setup Batch" label typically indicates a machine that requires a setup time for the entire batch before processing the items within it.

#### 3. First Routing Split (After WS1)
Upon exiting WS1, the batch flow diverges based on specific probabilities:
*   **Probability $p$:** The batch is routed directly to WS3.
*   **Probability $1-p$:** The batch is routed to WS2.

#### 4. WS2: Oven Batch
*   Batches routed to this path wait in a queue before WS2.
*   **Workstation 2 (Oven Batch):** This represents a simultaneous batch processing station (Process Batching). The entire batch is processed together at the same time, analogous to an industrial oven baking a full tray of components at once.

#### 5. Second Routing Split (After WS2)
Upon exiting WS2, the flow diverges a second time:
*   **Probability $q$:** The batch is routed upwards to join the queue for WS3.
*   **Probability $1-q$:** The completed batch exits the production system entirely.

#### 6. WS3: Single Item
*   This workstation receives batches from two possible sources: directly from WS1 (via route $p$) or after being processed at WS2 (via route $q$).
*   **Workstation 3 (Single Item):** Unlike the previous stations, this machine operates on a single-unit basis. It pulls individual items out of the queued batches and processes them one by one. The finished single items then exit the system.

# Workstation 1 Including Batch Forming Time

The average batch forming time, BT, to be associated with each individual item is

$$
B T _ {\mathrm {s t a r t}} = \frac {(3 - 1)}{2} \frac {1}{5} = 0. 2 \mathrm {h r}
$$

Where the 1/5 hour is the mean inter-arrival time

The arrival rate of batches toWorkstation 1 is the individual arrival rate divided by the batch size yielding $\lambda1(B)$ =5/3 per hour

SCV for the inter-arrival time of batches is $C^2_{B}[T_{a}(1)]$ =1/3

# Workstation 1 Including Batch Forming Time

The batch setup time has a mean of 12 minutes and a variance of 1080 minutes2.   
The individual processing time has a mean of 6 minutes and a variance of 240 minutes2   
The characteristics for processing the entire batch are

$$
E \left[ T _ {s, 1} (B) \right] = 1 2 + 3 \times 6 = 3 0 \min = 0. 5 h r
$$

$$
\mathrm {V} [ \mathrm {T} _ {\mathrm {s}, 1} (\mathrm {B}) ] = 1 0 8 0 + 3 \times 2 4 0 = 1 8 0 0 \mathrm {m i n} ^ {2} = 0. 5 \mathrm {h r} ^ {2}
$$

$$
\mathrm {C} _ {\mathrm {s}, 1} ^ {2} (\mathrm {B}) = \frac {0 . 5}{0 . 5 ^ {2}} = 2
$$

The Workstation utilization is u = λ1(B) × E[Ts,1(B)] = 0.8333   
The batch forming time after processing is given by

$$
B T _ {\text {s t a r t}} = \frac {(3 - 1)}{2} 0. 1 = 0. 1 \mathrm {h r}
$$

Where 0.1 is the individual mean processing time

# Workstation 1 Including Batch Forming Time

Thus, the CT per job at the Workstation 1 is

$$
\mathsf {C T} (1) = \mathsf {B T} _ {\mathrm {s t a r t}} + \frac {\frac {1}{3} + 2}{2} \frac {0 . 8 3 3 3}{1 - 0 . 8 3 3 3} 0. 5 + \frac {3 + 1}{2} 0. 1 + 0. 2 + \mathsf {B T f i n} = 3. 6 1 6 \mathrm {h r}
$$

The departing SCV is approximated by

$$
\mathsf {C} ^ {2} _ {\mathsf {d}, 1} (\mathsf {B}) = (1 - 0. 8 3 3 3 ^ {2}) (1 / 3) + 0. 8 3 3 3 ^ {2} (2) = 1. 4 9 1
$$

The two branches going to Workstation 2 and 3 wil have the following characteristics

$$
\lambda_ {1 \rightarrow 2} (\mathsf {B}) = \frac {2}{3} \times \frac {5}{3} = 1. 1 1 1 / \mathsf {h r}; \mathsf {C} _ {\mathsf {a}, 1 \rightarrow 2} ^ {2} (\mathsf {B}) = \frac {2}{3} (1. 4 9 1) + \frac {1}{3} = 1. 3 2 7
$$

and

$$
\lambda_ {1 \rightarrow 3} (\mathsf {B}) = \frac {1}{3} \times \frac {5}{3} = 0. 5 5 6 / \mathsf {h r}; \mathsf {C} ^ {2} _ {\mathsf {a}, 1 \rightarrow 3} (\mathsf {B}) = \frac {1}{3} (1. 4 9 1) + \frac {2}{3} = 1. 1 6 4
$$

# Workstation 2 Oven Batch Processing

The oven batch processing time has a mean of 48 minutes and a service SCV of 0.75   
The arrival process characteristics are those calculated previously from the Workstation 1 departure stream

$$
\mathrm {E} \left[ \mathrm {T} _ {\mathrm {a}, 2} (\mathrm {B}) \right] = 0. 9 \text {h o u r s a n d} \mathrm {C} ^ {2} _ {\mathrm {a}, 2} (\mathrm {B}) = 1. 3 2 7
$$

The utilization for theworkstation is $u_{2}$ =1.111x0.8=0.889   
The CT is 

$$CT(2) = 0.8 + \left(\frac{1.327 + 0.75}{2}\right) \left(\frac{0.889}{1 - 0.889}\right) 0.8 = 7.454 \text{ hr}$$

The inter-departure time SCV for Workstation 2 for batches, is

$$
\mathrm {C} ^ {2} _ {\mathrm {d}, 2} (\mathrm {B}) = (1 - 0. 8 8 9 ^ {2}) \times 1. 3 2 7 + 0. 8 8 9 ^ {2} \times 0. 7 5 = 0. 8 7 1
$$

V The departure stream going to workstation 3 is 3/, thus

$$
\lambda_ {2 \rightarrow 3} (\mathsf {B}) = \frac {3}{4} \times 1. 1 1 1 = 0. 8 3 3 / \mathsf {h r}; \mathsf {C} ^ {2} _ {\mathsf {a}, 2 \rightarrow 3} (\mathsf {B}) = \frac {3}{4} (0. 8 7 1) + \frac {1}{4} = 0. 9 0 3
$$

# Workstation 3 Batch-Arrival Individual Service

The total mean arrival rate from Workstation 1 and 2 is given by:

$$
\lambda_ {3} (\mathsf {B}) = \lambda_ {1 \rightarrow 3} (\mathsf {B}) + \lambda_ {2 \rightarrow 3} (\mathsf {B}) = 0. 5 5 6 + 0. 8 3 3 = 1. 3 8 9 / \mathrm {h r}
$$

The SCV of the arrival stream is approximated by a weighted average of the two streams that merge yielding:

$$
\mathsf {C} ^ {2} _ {\mathsf {a}, 3} (\mathsf {B}) = \frac {0 . 5 5 6}{1 . 3 8 9} \times \mathsf {C} ^ {2} _ {\mathsf {a}, 1 \rightarrow 3} (\mathsf {B}) + \frac {0 . 8 3 3}{1 . 3 8 9} \times \mathsf {C} ^ {2} _ {\mathsf {a}, 2 \rightarrow 3} (\mathsf {B}) = 0. 4 \times 1. 1 6 4 + 0. 6 \times 0. 9 0 3 = 1. 0 0 7
$$

The mean and standard deviation of the individual processing times are 12 and 8.458 minutes   
The utilization factor for the workstation is: $u_{3}$ = 3x1.389x0.2= 0.833/hr   
Hence, the mean time that a job spends within Workstation 3 is

$$
\mathrm {C T} (3) = \frac {3 \times 1 . 0 0 7 + 0 . 5}{2} \frac {0 . 8 3 3}{1 - 0 . 8 3 3} 0. 2 + \frac {3 + 1}{2} 0. 2 = 2. 1 5 6 \mathrm {h r}
$$

# Network performance measures

The throughput rate of individual items for this system has to equal the arrival rate of 5 jobs per hour   
The cycle time for the system is determined by computing the WiP at each workstation, then summing to obtain the system WIP   
From the system WIP, using Little's Law, the cycle time for individuals is determined

| Workstation $i$ | $\lambda_i(I)$ | $CT(i)$ | $WIP(i)$ |
| :---: | :---: | :---: | :---: |
| 1 | 5/hr | 3.616 hr | 18.08 |
| 2 | 3.333/hr | 7.454 hr | 24.84 |
| 3 | 4.167/hr | 2.156 hr | 8.98 |

The total WIP is 51.9 jobs and the average cycle time for individual jobs is 51.9/5 = 10.38 hours
