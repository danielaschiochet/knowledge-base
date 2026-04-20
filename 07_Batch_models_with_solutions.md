# Analysis and Management of Production System

# Lesson 7: Batch models

Prof. Giulia Bruno

Department of Management and Production Engineering

giulia.bruno@polito.it

# Introduction

V Grouping individual jobs into batches is a strategy frequently used in industry

> Purpose of sharing transportation between workstations (pallet movement)   
》 Sharing machine setup by products of the same time, even though the items are processed individually   
> Multiple service capacity resource such as ovens (heat treatment, plating processes)

# Introduction

V The batching phenomenon has an impact on downstream processing stations   
V E.g., consider the batch move concept where, say k, items are grouped together for the convenience of moving them to a subsequent single unit processing station.

> Items arrive at the next workstation k at a time, so the workstation might be idle for a while and then instantaneously have a queue of waiting units   
V Increased cycle times and larger WiPlevels at the downstream workstation   
Y The batch process causes an increased delay because units must wait for the completion of other units before they can be grouped and continue processing

# Introduction

V Models are developed for various forms of batching, so that the benefits and costs of the grouping process under consideration can be quantified   
> For the setup sharing situation,there willbe a trade-off between the cycle time increase and the setup time savings due to batching

# Batching for transport

# Batch move model structure

> Items are grouped in batches of size k at the completion of processing at a workstation that processes single units   
> Items wait in the incomplete batch until the proper quantity has been reached   
> The full batch is transported to the next workstation, where they are processed individually

# V Basic assumption: transportation time is negligible, thus not explicitly considered

> If transportation time is significant, it can be approximated by considering the transporter as a separate workstation

![](images/d07aa5045422a35806d9bb988531cf5948e72f81c31da821209cbd736da5bfa8.jpg)

# Batching for transport

![](images/06c58afe72f15ed4791dd64eef09fc758731d62b03edda1fb222f51843b09a88.jpg)

Cycle time depends on three components

Batch forming time   
V Queue time for batches

Dependent on mean arrival rate of batches and squared coefficient of variation of the inter-arrival batch times

Processing time delay due to the individual processing

# Batch Forming Time

Consider a batch formed by k arriving items   
V Let Td be the random variable denoting the time between departures from the source workstation that are to be batched for transportation to the destination workstation   
V The inter-arrival rate of individuals X(l) to the destination workstation in the absence of batching is given by

$$
\lambda \left(\mathsf {I}\right) = \frac {1}{\mathsf {E} [ \mathsf {T d} ]}
$$

# Batch Forming Time

> The nter-arrival time of batches T(B) is a random variable given by the Sum of k individual inter-departure times

$$
\mathsf {T} (\mathsf {B}) = \mathsf {T} _ {\mathrm {d}, 1} + \mathsf {T} _ {\mathrm {d}, 2} + \ldots + \mathsf {T} _ {\mathrm {d}, \mathrm {k}}
$$

Since the individual inter-departure times are independent and identically distributed (i.i.d.) random variables, the expected value of the batch interarrival time is

$$
\mathsf {E} [ \mathsf {T} (\mathsf {B}) ] = \mathsf {k E} [ \mathsf {T} _ {\mathsf {d}} ]
$$

V The arrival rate of batches to the destination workstation, X(B), is

$$
\lambda (\mathsf {B}) = \frac {1}{\mathsf {E} [ \mathsf {T} (\mathsf {B}) ]} = \frac {1}{\mathrm {k E} [ \mathrm {T d} ]} = \frac {\lambda (\mathsf {I})}{\mathsf {k}}
$$

# Batch Forming Time

V The variance of the batch inter-arrival times at the destination workstation is

$$
\mathsf {V} [ \mathsf {T} (\mathsf {B}) ] = \mathsf {V} [ \mathsf {T} _ {\mathsf {d}, 1} + \mathsf {T} _ {\mathsf {d}, 2} + \ldots + \mathsf {T} _ {\mathsf {d}, \mathsf {k}} ] = \mathsf {k V} [ \mathsf {T} _ {\mathsf {d}} ]
$$

Thus, the squared coefficient of variation, C²[T(B)], of the batch interarrival times can be computed from the squared coefficient of variation of the individual inter-arrival times by

$$
\mathrm {C} ^ {2} [ \mathrm {T} (\mathrm {B}) ] = \frac {\mathrm {V} [ \mathrm {T} (\mathrm {B}) ]}{\mathrm {E} [ \mathrm {T} (\mathrm {B}) ] ^ {2}} = \frac {\mathrm {K V} [ \mathrm {T d} ]}{(\mathrm {k E} [ \mathrm {T} _ {\mathrm {d}} ]) ^ {2}} = \frac {\mathrm {C} ^ {2} [ \mathrm {T d} ]}{\mathrm {k}}
$$

# Batch Forming Time

The delay that an individual item encounters when being placed into a batch depends on its position among the k batched items   
V First departing item must wait for k-1 items to depart before the batch is ready for transportation to the destination workstation

The delay of the first item is D,= Td,2+..+Tdk

V The second item forming the new batch has to wait for k-2 succeeding departures   
The delay of the second item is D2= Td.3+..+Tk   
V Average delay is the expected value of the sum of all these delays divided by the batch size k

$$
E [ D ] = \frac {E [ D _ {1} + D _ {2} + \cdots + D K _ {1} , D K ]}{K} = \frac {(K - 1) E [ T _ {d} ] + (K - 2) E [ T _ {d} ] + \cdots + 1 E [ T _ {d} ] + 0 E [ T d ]}{k} =
$$

$$
\frac {(\mathrm {k} - 1) \mathrm {k} / 2 \mathrm {E} [ \mathrm {T d} ]}{\mathrm {k}} = \frac {(\mathrm {k} - 1)}{2} \mathrm {E} [ \mathrm {T _ {d}} ]
$$

# Batch Queue Waiting Time

The cycle time for the recipient workstation for the batch move situation has two distinct components: the queue time and the service time.   
V Let X(B) be the arrival rate of the batches to the queue is with corresponding squared coefficient of variation C2[T(B)]   
> Let the random variable T,(B) be the service time to process all of the items within the batch,which is given by

$$
\mathsf {T} _ {\mathsf {s}} (\mathsf {B}) = \mathsf {T} _ {\mathsf {s}, 1} (\mathsf {I}) + \mathsf {T} _ {\mathsf {s}, 2} (\mathsf {I}) + \ldots + \mathsf {T} _ {\mathsf {s}, \mathsf {k}} (\mathsf {I})
$$

# Batch Queue Waiting Time

The processing times Ts,i(l) are independent and identically distributed random variables with known mean E[Ts(l)] and squared coefficient of variation C2[T,()]   
Thus,the batch service time characteristics can be computed from the individual item data as

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

![](images/4f9d064732b7fe2f4962fc72486c093ef7c191e78249388d1c12ff42dc4f159b.jpg)

# Total cycle time

Assume a pure serial system layout with Workstation i sending jobs directly to Workstation jby batch moves of size k and alljobs are processed one-at-a-time at j   
Y The mean system cycle time per job at Workstation j is given by

$$
\begin{array}{l} \mathrm {C T (j)} = \frac {(k - 1)}{2} \mathrm {E [ T _ {a} (i) ]} + \left(\frac {C _ {d} ^ {2} (i) + C _ {s} ^ {2} (j)}{2}\right) \left(\frac {u}{1 - u}\right) \mathrm {E [ T s (j) ]} + \frac {(k - 1)}{2} \mathrm {E [ T _ {s} (j) ]} + \\ + \mathrm {E} [ \mathrm {T s} (\mathrm {j}) ] \\ \end{array}
$$

where the batch formation time after processing at Workstation i is considered part of the cycle time at Workstation j

# Total cycle time

There are times in which a batch has already been formed so that the basic arrival rate is in terms of batches to a workstation in which processing is by individual job   
Y In this case there would be batch formation times so the mean system cycle time per job at the workstation is

$$
\mathrm {C T} _ {\mathrm {s}} = \left(\frac {\mathrm {k C} _ {\mathrm {a}} ^ {2} (\mathrm {B}) + \mathrm {C} _ {\mathrm {s}} ^ {2} (\mathrm {I})}{2}\right) \left(\frac {\mathrm {u}}{1 - \mathrm {u}}\right) \mathrm {E} [ \mathrm {T s} (\mathrm {I}) ] + \frac {(\mathrm {k} + 1)}{2} \mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {I}) ]
$$

where the utilization is u=kE[T,(I)]/E[Ta(B)]

# Variability of departures

Where the batch arrives, if the workstation is busy processing items, the first item willonly experience a service time inter-departure delay   
》 All other inter-departure times for items in the batch are merely separated by service time delays   
The general approach for modeling departures is to approximate them by a renewal process   
> Thus, the inter-departure time squared coefficient of variation for individuals for the batch-move server for a single machine workstation is

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (\mathsf {I}) = \mathrm {k C} _ {\mathrm {a}} ^ {2} (\mathsf {B}) (1 - \mathsf {u} ^ {2}) + (\mathsf {k} - 1) (1 - \mathsf {u}) ^ {2} + \mathsf {u} ^ {2} \mathsf {C} _ {\mathrm {s}} ^ {2} (\mathsf {I})
$$

# Variability of departures

> In the context of a pure serial system layout, with Workstation i sending jobs directly to Workstation j by batch moves of size k, the squared coefficient of variation of inter-departures of individuals from workstation j is given by

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (\mathfrak {j}) = \mathsf {C} _ {\mathrm {d}} ^ {2} (\mathfrak {i}) (1 - \mathfrak {u j} ^ {2}) + (\mathfrak {k} - 1) (1 - \mathfrak {u j}) ^ {2} + \mathfrak {u j} ^ {2} \mathsf {C} _ {\mathrm {s}} ^ {2} (\mathfrak {j})
$$

# Example

Consider two workstations in series consist of only one machine that process items at a rate of 3 per hour, with a squared coefficient of variation of the inter-arrivals of 2   
> The first workstation processes jobs on average in 0.25 hours with SCV of 2   
V The second workstation processes jobs on average in 0.25 hours with SCV of 1.5   
V The batch size is k=4   
V Find CT and cd of the second workstation

# Example

Since the SCV of the inter-arrivals and service process of the first workstation are the same, the SCV of the inter-departures will also be the same, e.g., 2   
Mean of inter-departure of individuals from first workstation is 1/3   
V Utilization factor for the second workstation is uz = 3(0.25)= 0.75   
Average cycle time per item

$$
\mathrm {C T} (2) = \frac {4 - 1}{2} \left(\frac {1}{3}\right) + \frac {2 + 1 . 5}{2} \frac {0 . 7 5}{0 . 2 5} (0. 2 5) + \frac {4 - 1}{2} 0. 2 5 + 0. 2 5 = 2. 4 3 7 5 \mathrm {h r}
$$

> Squared coefficient of variation of the inter-departure times

$$
\mathrm {C} ^ {2} _ {\mathrm {d}} (2) = 2 \left(1 - 0. 7 5 ^ {2}\right) + 3 \left(1 - 0. 7 5\right) ^ {2} + 0. 7 5 ^ {2} (1. 5) = 1. 9 0 6 3
$$

# Exercise

Consider two workstations in series that consist of only one machine   
> The items are moved from the first to the second workstation in batches of 10 items   
V Both workstations process items at a rate of 1 j/h, with a squared coefficient of variation of processing times of 0.16   
> The arrival rate is 0.9 j/h and the inter-arrval time are exponentially distributed   
V Find the total CT of the line

# Solution

![](images/dd97d853961f9addf2d2b3c064dc3d67b3b97b5d73342697a8dc8759ff6fffaf.jpg)

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

![](images/36da4661eb770b2c416b9049acd5094b659682bee81bf57e9cc06e3ed2183eb5.jpg)

# Batching for Setup Reduction

![](images/4c2f1c20e8c2f3a56e7b86a1992ca67214449549c6797028b4cd52be3527715a.jpg)

![](images/d02090b2f9261dad6d121f20f0cdc32dc2c19a61c79b981500acd56c8f6b07bc.jpg)

![](images/02d293cf958c0a6efadde576474c8a6b2377ab6cc1ca0d9094c405c9df92a977.jpg)

V When a single-unit processing workstation must be setup before processing a group of items of the same job type, a batch of size k is formed to spread the batch setup time across k jobs rather than one job   
V There are many choices for the batch size for each item and a batch quantity should be chosen that balances the setup time reduction against the increased batching delay as the batching quantity is increased

# Batching for Setup Reduction

Items arive to the workstation one at-a-time with known mean rate X(l)= 1/E[Ta(l)] and known inter-arival time SCV C²a(l)   
> Each batch has a service time that consists of the setup time random variable Rplus kindividualrandom servicesTs,1,,K   
The expected processing time and variance for the batch are

$$
\mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] = \mathsf {E} [ \mathsf {R} ] + \mathsf {k E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ]
$$

$$
\mathsf {V} [ \mathsf {T} _ {\mathrm {s}} (\mathsf {B}) ] = \mathsf {V} [ \mathsf {R} ] + \mathsf {k V} [ \mathsf {T} _ {\mathrm {s}} (\mathsf {I}) ]
$$

# Batching for Setup Reduction

V The squared coefficient of variation for the batch service time is then computed from the definition

$$
\mathrm {C} ^ {2} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {B}) ] = \frac {\mathrm {V} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {B}) ]}{\mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {B}) ] ^ {2}} = \frac {\mathrm {C} ^ {2} [ \mathrm {R} ] \mathrm {E} [ \mathrm {R} ] ^ {2} + \mathrm {k C} ^ {2} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {I}) ] \mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {I}) ] ^ {2}}{\mathrm {E} [ \mathrm {T} _ {\mathrm {s}} (\mathrm {B}) ] ^ {2}}
$$

V Thus,the utilization factor accounting for the setup time is

$$
\mathsf {u} = \lambda (\mathsf {I}) \frac {\mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ]}{\mathsf {k}} = \lambda (\mathsf {I}) (\frac {\mathsf {E} [ \mathsf {R} ]}{\mathsf {k}} + \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ])
$$

> The cycle time in the queue, CTq, is the same as that developed for transport batches

# Batching for Setup Reduction

V Given the new values for the batch times and the utilization factor, the mean cycle time per job at the workstation,where a setup operation is performed before any of the individual jobs within each batch are processed, is given by

$$
\mathsf {C T} (\mathsf {I}) = \frac {(\mathsf {k} - 1)}{2} \mathsf {E} [ \mathsf {T a} (\mathsf {I}) ] + (\frac {(\frac {\mathsf {C} ^ {2} \mathsf {a} (\mathsf {I})}{\mathsf {k}} + \mathsf {C} _ {\mathsf {s}} ^ {2} (\mathsf {B})}{2}) (\frac {\mathsf {u}}{1 - \mathsf {u}}) \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] + \frac {(\mathsf {k} + 1)}{2} \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {I}) ] + \mathsf {E} [ \mathsf {R} ]
$$

E[R] and C2[R] are the mean and squared coefficient of variation of the setup operation

# Batching for Setup Reduction

The SCV for the inter-departure times from a workstation that processes jobs one-at-a-time with a batch set-up is

$$
\begin{array}{l} \mathsf {C} ^ {2} [ \mathsf {T} _ {\mathsf {d}} (\mathsf {I}) ] = \mathsf {k C} ^ {2} [ \mathsf {T} _ {\mathsf {a}} (\mathsf {B}) ] (1 - \mathsf {u} ^ {2}) + \mathsf {k} (1 - \mathsf {u}) ^ {2} - 1 + \frac {2 \mathsf {k} (1 - \mathsf {u}) (\mathsf {E} [ \mathsf {R} ] + \mathsf {E} [ \mathsf {T s} (\mathsf {I}) ])}{\mathsf {E} [ \mathsf {T a} (\mathsf {B}) ]} + \\ + \frac {\mathrm {k (E [ R ] ^ {2} (C ^ {2} [ R ] + 1) + k E [ T _ {s} (I) ] ^ {2} (C ^ {2} [ T _ {s} (I) + 1 ] + 2 E [ R ] E [ T s (I) ]}}{\mathrm {E [ T a (B) ] ^ {2}}} \\ \end{array}
$$

# Example

Consider finding the batch size k that results in the minimum cycle time for a single product with E[Ts(l)]= 0.1 hours,C²(I)= 1.5, E[R]= 0.2 hours and C2[R]= 1   
V Assume that the arrival rate of individual units is λ(l)= 5.666 per hour (E[Ta(I)]= 0.1765 hours), and C²a(l)= 3.0

# Example

Consider finding the batch size k that results in the minimum cycle time for a single product with E[Ts(l)]= 0.1 hours,C²(I)= 1.5,E[R]= O.2 hours and C2[R]= 1   
Assume that the arrival rate of individual units is X(l)= 5.666 per hour (E[Ta(l)]= 0.1765 hours), and C²a(l)= 3.0   
The workstation utilization is given by

$$
\mathsf {u} = \lambda (\mathsf {B}) \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] = \frac {5 . 6 6 6}{\mathsf {k}} (0. 2 + 0. 1 \mathsf {k})
$$

The feasibility condition is that k must be large enough so that u<1; hence, k must be greater or equal to 3

# Example

D The following table displays the computed information for each batch size over the range of k E {3,..., 9}.

![](images/b488f2a76fab3a2a13798d1e4d6a03ce7276285c0a4cbac02fe6b508a368a529.jpg)

The optimal batch size occurs at K=6 using the minimum CTs as the criterion

# Batch Service

![](images/62e29c56f5cbba601fcadd97c1e959fe719da57ecd981710e0a798d82a4bbf2b.jpg)

> Abatch server is a processor that can process several jobs simultaneously   
Service cannot start until a full batch is available

# Batch Service

> Consider a single-server workstation that processes jobs in fixed batches of size k   
> Jobs arrive individuallyand are placed in batches before proceeding into the workstation   
The mean system cycle time per job at the workstation is given by

$$
\mathsf {C T} _ {\mathsf {s}} = \frac {(\mathsf {k} - 1)}{2} \mathsf {E} [ \mathsf {T a} (\mathsf {I}) ] + \mathsf {E} [ \mathsf {T} _ {\mathsf {s}} (\mathsf {B}) ] + \left(\frac {\mathsf {C} ^ {2} [ \mathsf {T} _ {\mathsf {a}} (\mathsf {B}) ] + \mathsf {C} ^ {2} [ \mathsf {T s} (\mathsf {B}) ]}{2}\right) \left(\frac {\mathsf {u} (\mathsf {B})}{1 - \mathsf {u} (\mathsf {B})}\right) \mathsf {E} [ \mathsf {T s} (\mathsf {B}) ]
$$

Where E[T(B)] is the mean batch processing time and u(B)= >(B)E[T:(B)]. This formula needs to be adjusted according to the nature of the batch formation process.

# Batch Service

> At the end of the processing, the batch is unloaded and the individual items are moved into their subsequent workstations   
Y The SCV of the inter-departures of individuals from the batch service workstation is

$$
C _ {d} ^ {2} (I) = k C _ {d} ^ {2} (B) + k - 1
$$

Y Which can be written in terms of the basic workstation characteristics for batches as

$$
\mathsf {C} _ {\mathrm {d}} ^ {2} (\mathsf {I}) = \mathsf {k} [ (1 - \mathsf {u} ^ {2}) \mathsf {C} _ {\mathrm {a}} ^ {2} (\mathsf {B}) + \mathsf {u} ^ {2} \mathsf {C} _ {\mathrm {s}} ^ {2} (\mathsf {B}) ] + \mathsf {k} - 1
$$

# Example

V Consider a batch-processing workstation in which arivals occur from another batch server in batches of size 5 with a mean rate of 3 batches per hour and an SCV of batch inter-arival times of 0.75   
V The SCV of the batch service time is also O.75 with a workstation utilization of 84%   
The average time each job spends in the workstation is thus given by

$$
C T = 1 6. 8 + \frac {0 . 7 5 + 0 . 7 5}{2} \times \frac {0 . 8 4}{1 - 0 . 8 4} \times 1 6. 8 = 8 2. 9 5 \mathrm {m i n}
$$

> 16.8 is the service time given in minutes and is obtained by dividing the utilization factor by the arrival rate   
> The first term in the previous cycle time equation is not used since the arrivals were already in batches

# Example

V Since the SCV of the inter-arrival times and the service times are the same, it is also the SCV of the inter-departure times for batches   
V The approximation for the inter-departure SCV of individuals is given by

$$
\mathrm {C} ^ {2} _ {\mathrm {d}} (\mathrm {I}) = 5 (1 - 0. 8 4 2) (0. 7 5) + 0. 8 4 2 (0. 7 5) + 4 = 7. 7 5
$$

# Batch line exercise

V A production line consists of 2 workstations and produces 40 pieces per day with an 8-hour shift; the inter-arrival times are distributed exponentially   
V The first station consists of 3 parallel machines with a process time of 30 minutes with a standard deviation of 15 minutes   
The second station is composed of a single machine with an average process time of 8 minutes,which appears to be very worn and has breakdowns every hour with repair times that are between 4 and 12 minutes   
V The pieces leaving the line are transferred in batch of 40 pieces to a second line located in another plant about 30 km away   
V In this plant the line is made up of two single-machine workstations with variable average process times of 8 minutes and 10 minutes respectively   
V Calculate the resulting cycle time (excluding the time due only to the transfer)

# Solution

Uniform Probability Distribution   
Expected value of x

$$
E (x) = (a + b) / 2
$$

Variance of x

$$
\operatorname {V a r} (x) = (b - a) ^ {2} / 1 2
$$

![](images/8e2f318d091e08dad71faac8ed0f80ace5368f79b915d5cc1dfe2328fda7c8bb.jpg)

![](images/369afccf2a0bf6583c98491ddd4323ad4b4e5d363d6a35e3906d9569769042c7.jpg)

# Solution

![](images/4ba1c3da279c3c63936546d355b9710ae3f2ffda3a624b5e6b3b946bdc51a992.jpg)

# Solution

![](images/c5d83b59807abf2b52bf62bc378f67b7f10d7c43cfd5a1aea2e44cb017d720ae.jpg)

# Solution

![](images/6dfed05afb191ee6eefd3683d56b8b7d6205c1e0af9f015cf71e5e1afe5f4e6d.jpg)

# Batch Network Exercise

Consider three workstations: the first workstation is a setup-batch processing workstation, the second worksation uses oven-batch processing,and the third workstation is a single unit server with batch arrivals   
V The arrival rate of individuals to the fisrt workstation is according to a Poisson process (SCV=1) with a mean rate of 5 units per hour   
The batch size of the first workstation is k=3   
V The batch forming time in this analysis will be added to the cycle time for Workstation 1   
V Items remain in batches until they exit the system, so allthe probabilistic branches are made on batches   
V 2/3 of the batches leaving Workstation 1 are routed to Workstation 2 and 1/3 go to Workstation 3   
V From Workstation 2,1/4 of the batches are finished (leave the system)and the remaining 3/4 are routed to Workstation 3   
At Workstation 3 items are separated and they leave as individuals

# Batch Network Exercise

The batch setup time has a mean of 12 minutes and a variance of 1080 minutes². The individual processing time has a mean of 6 minutes and a variance of 240 minutes²   
V The oven batch processing time has a mean of 48 minutes and a service SCV of 0.75   
V The mean and standard deviation of the individual processing times are 12 and 8.458 minutes

![](images/b4c45c35fa3e83116cd9a9d41602348e41a9e7c91dbd3aaae7a6ffd74108962f.jpg)  
Oven Batch

# Workstation 1 Including Batch Forming Time

The average batch forming time, BT, to be associated with each individual item is

$$
B T _ {\mathrm {s t a r t}} = \frac {(3 - 1)}{2} \frac {1}{5} = 0. 2 \mathrm {h r}
$$

Where the 1/5 hour is the mean inter-arrival time

The arrival rate of batches toWorkstation 1 is the individual arrival rate

divided by the batch size yielding ^1(B) =5/3 per hour

SCV for the inter-arrival time of batches is C²b[Ta(1)=1/3

# Workstation 1 Including Batch Forming Time

V The batch setup time has a mean of 12 minutes and a variance of 1080 minutes2.   
V The individual processing time has a mean of 6 minutes and a variance of 240 minutes2   
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

The Workstation utilization is u = λ(B) × E[Ts,1(B)] = 0.8333   
V The batch forming time after processing is given by

$$
B T _ {\text {s t a r t}} = \frac {(3 - 1)}{2} 0. 1 = 0. 1 \mathrm {h r}
$$

Where 0.1 is the individual mean processing time

# Workstation 1 Including Batch Forming Time

Thus, the CT per job at the Workstation 1 is

$$
\mathsf {C T} (1) = \mathsf {B T} _ {\mathrm {s t a r t}} + \frac {\frac {1}{3} + 2}{2} \frac {0 . 8 3 3 3}{1 - 0 . 8 3 3 3} 0. 5 + \frac {3 + 1}{2} 0. 1 + 0. 2 + \mathsf {B T f i n} = 3. 6 1 6 \mathrm {h r}
$$

V The departing SCV is approximated by

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

V The oven batch processing time has a mean of 48 minutes and a service SCV of 0.75   
V The arrival process characteristics are those calculated previously from the Workstation 1 departure stream

$$
\mathrm {E} \left[ \mathrm {T} _ {\mathrm {a}, 2} (\mathrm {B}) \right] = 0. 9 \text {h o u r s a n d} \mathrm {C} ^ {2} _ {\mathrm {a}, 2} (\mathrm {B}) = 1. 3 2 7
$$

V The utilization for theworkstation is Uz =1.111x0.8=0.889   
The CT is CT(2)=0.8+ (1.327+0.75)_0.889 2 1-0.889 (0.8) = 7.454 hr   
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

V The SCV of the arrival stream is approximated by a weighted average of the two streams that merge yielding:

$$
\mathsf {C} ^ {2} _ {\mathsf {a}, 3} (\mathsf {B}) = \frac {0 . 5 5 6}{1 . 3 8 9} \times \mathsf {C} ^ {2} _ {\mathsf {a}, 1 \rightarrow 3} (\mathsf {B}) + \frac {0 . 8 3 3}{1 . 3 8 9} \times \mathsf {C} ^ {2} _ {\mathsf {a}, 2 \rightarrow 3} (\mathsf {B}) = 0. 4 \times 1. 1 6 4 + 0. 6 \times 0. 9 0 3 = 1. 0 0 7
$$

> The mean and standard deviation of the individual processing times are 12 and 8.458 minutes   
V The utilization factor for the workstation is: u3 = 3x1.389x0.2= 0.833/hr   
V Hence, the mean time that a job spends within Workstation 3 is

$$
\mathrm {C T} (3) = \frac {3 \times 1 . 0 0 7 + 0 . 5}{2} \frac {0 . 8 3 3}{1 - 0 . 8 3 3} 0. 2 + \frac {3 + 1}{2} 0. 2 = 2. 1 5 6 \mathrm {h r}
$$

# Network performance measures

The throughput rate of individual items for this system has to equal the arrival rate of 5 jobs per hour   
V The cycle time for the system is determined by computing the WiP at each workstation, then summing to obtain the system WIP   
> From the system WIP, using Little's Law, the cycle time for individuals is determined

![](images/807c09a566ded38a9a0bfaa1224cf61b681283bf34b4b74fb7bad24b229da5f8.jpg)

> The total WIP is 51.9 jobs and the average cycle time for individual jobs is 51.9/5 = 10.38 hours
