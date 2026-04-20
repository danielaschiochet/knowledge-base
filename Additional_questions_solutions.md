# Solution of multiple choice questions

1) Which is the best formalism to represent the pasta production cycle,from wheat grinding to packaging?

a) UML activity diagram   
b) Flow process chart (X)   
c）BPNM   
d） IDEFO

2) Which is the right Kendallnotation to indicate a workstation in which the inter-arrival time follows a normal distribution,the processing time follows an exponential distribution,there are three machines in paralll and the queue is unlimited?

e) M/G/3/∞   
f)N/E/3/0   
g) M/G/∞/3   
h) G/M/0/3   
i) G/M/3/∞ (X)

3) Which of the folowing definitions best describes the concept of maintenance in production systems?

a)replacement of a component after a failure   
b) application of predictive algorithms to identify the causes of failures   
c)set of activities aimed at ensuring that each element of the system can perform its function correctly (X)   
d) signing of a contract with a company specializing in the repair of systems

4) At which level of the hierarchy are the data concerning the realt time monitoring of the production machines used to take decisions?

a） strategical  
b) tactical   
c）operational (X)

5)A workstation has a processing rate of6j/h.The inter arrival time of jobs to the workstation is 20 min.Which is the utilization of the workstation?

a) 90%   
b) 70%   
c) 50% (X)   
d） 30%

6) Which of the following statements regarding PLM systems is correct?

a) PLM systems are used to manage the plant production monitoring   
b） PLM systems are used to keep track of the different revisions of a product (X)   
c) PLM systems are used only in the design phase of a new product   
d） PLM systems are used in companies which do not perform product design

# Solution of open questions and exercises

1) Describe the main concepts of the Group Technology and indicate some advantages with respect to the functional layout.

Group technology has the goal of determining the similarity of the products by analysing their processing functions.Following this approach,the machines of the factory are grouped into cels of machines needed to produce similar job types.The functional approach instead group machines depending on their function.

The main advantages of the group technology are the following:

reduced processing time due to the reduced setup times between part types and the specialization of operators   
·reduced WIP and variability in each production cell   
·reduced material handling and transport because items move inside a single cell.

2) In a system the mean arrival rate isλ = 6 jobs/hours,and it is exponentially distributed. The mean service times is E[Ts] = 0.5 hours,with asquared coeficients of variation C² = 0.8.Which is the number of parallel machines needed to get a utilization lower or equal to O.9? Considering the obtained number of parallel machines, compute the CT,the WIP and the TH of the system.

$$
\lambda = 6 \text {j o b s / h o u r s , E [ T s ]} = 0. 5 \text {h o u r s , C _ {s} ^ {2}} = 0. 8
$$

$$
u <   = 0. 9 \rightarrow \text {t h u s} \lambda^ {*} E [ T s ] / c <   = 0. 9 \rightarrow c > = \lambda^ {*} E [ T s ] / 0. 9 = 6 ^ {*} 0. 5 / 0. 9 = 3. 3 3 \rightarrow c = 4
$$

$$
u = \lambda^ {*} E [ T s ] / c = 6 ^ {*} 0. 5 / 4 = 0. 7 5
$$

$$
\begin{array}{l} C T = \left(c _ {a} ^ {2} + c _ {s} ^ {2}\right) / 2 * u ^ {\wedge} (\operatorname {s q r t} (2 c + 2) - 1) / (c (1 - c)) ^ {*} E [ T s ] + E [ T s ] = \\ = 1. 8 / 2 * 0. 7 5 ^ {\wedge} (\operatorname {s q r t} (1 0) - 1) / \left(4 * 0. 2 5\right) * 0. 5 + 0. 5 = 0. 7 4 2 h \\ \end{array}
$$

$$
\mathrm {T H} = 6 \mathrm {j / h}
$$

$$
W I P = T H ^ {*} C T = 6 ^ {*} 0. 7 4 2 = 4. 4 5 \mathrm {j}
$$

3)Aline is composed by 3 workstations, named A, Band C.Thefirst and the third have a single machine,while the second has two paralel machines (B1 and B2). By analysing the Dashboard of the simulation model shown in the figure,answer the folowing questions. Times are expressed in seconds,unless otherwise specified.

![](images/3dccf3c415e6976bb400b0c4ab610c1731974e3fec23f0bada6ae5538692fdef.jpg)

![](images/c04ba27b744ea2aeb82f500d88f1e1eaa282752e9565cea2f7122d02ef54523d.jpg)

4) Consider a factory with the processflow as given in the follwing table.There are two machines in WS 1 and 2,and one machine in WS 3 and 4.The arrival rate at WS1is 5j/h exponentially distributed.Computethe CT and WIP of the WS and of the system.

![](images/70abc46ea813bdb360f396cefe85f58aca6438c2b4153b0b72fc1dbc94476408.jpg)

![](images/fb828772944497460cf60a3d5756f07a9b6219926b0b6cebb4e1beec34071154.jpg)

![](images/dfcdeb401759fd7494132994c7e718f2c670d73c7e5ccd4bc275ec11da865428.jpg)

$$
\lambda_ {1} = \lambda_ {2} = 1 0 \frac {j}{h}, \quad \lambda_ {3} = \lambda_ {4} = 5 \frac {j}{h}
$$

$$
W L _ {1} = 5 \frac {1 0}{6 0} + 5 \frac {8 . 6}{6 0} = 1. 5 5 \quad u _ {1} = \frac {1 . 5 5}{2} = 0. 7 7 5
$$

$$
W L _ {2} = 5 \frac {7 . 5}{6 0} + 5 \frac {1 0}{6 0} = 1. 4 6 \quad u _ {2} = \frac {1 . 4 6}{2} = 0. 7 3
$$

$$
u _ {3} = 5 \frac {7 . 5}{6 0} = 0. 6 3 \quad u _ {4} = 5 \frac {1 0 . 9}{6 0} = 0. 9 1
$$

$$
E [ T s (1) ] = W L _ {1} / \lambda_ {1} = 0. 1 5 5 * 6 0 = 9. 3 \min
$$

$$
E [ T s (2) ] = W L _ {2} / \lambda_ {2} = 0. 1 4 6 ^ {*} 6 0 = 8. 7 6 \min
$$

$$
E [ T s (3) ] = 7. 5 \min , E [ T s (4) ] = 1 0. 9 \min
$$

$$
\begin{array}{l} C s (1) ^ {2} = \left[ \left(5 / 1 0 ^ {*} (1 0 / 6 0) ^ {2} * (1 + 0. 7 9) + 5 / 1 0 ^ {*} (8. 6 / 6 0) ^ {2} * (1 + 0. 9 7) \right] / 0. 1 5 5 ^ {2} - \right. \\ 1 = 0. 8 7 7 \\ C s (2) ^ {2} = [ (5 / 1 0 ^ {*} (7. 5 / 6 0) ^ {2} * (1 + 1. 2 2) + 5 / 1 0 ^ {*} (1 0 / 6 0) ^ {2} * (1 + 1. 2 6) ] / 0. 1 4 6 ^ {2} - 1 \\ = 1. 2 8 6 \\ \end{array}
$$

$$
C s (3) ^ {2} = 1. 4 7
$$

$$
C s (4) ^ {2} = 0. 7 6
$$

$$
\left\{ \begin{array}{l} c _ {a _ {1}} ^ {2} = \frac {5}{1 0} 1 + \frac {5}{1 0} c _ {d _ {3}} ^ {2} \\ c _ {a _ {2}} ^ {2} = c _ {d _ {1}} ^ {2} \\ c _ {a _ {3}} ^ {2} = 0. 5 c _ {d _ {2}} ^ {2} + 1 - 0. 5 \\ c _ {a _ {4}} ^ {2} = 0. 5 c _ {d _ {2}} ^ {2} + 1 - 0. 5 = c _ {a _ {3}} ^ {2} \end{array} \right.
$$

$$
\left\{ \begin{array}{l} c _ {a _ {1}} ^ {2} = \frac {5}{1 0} 1 + \frac {5}{1 0} \big \{\big [ (1 - 0. 6 3 ^ {2}) c _ {a _ {3}} ^ {2} + 0. 6 3 ^ {2} \cdot 1. 4 7 2 \big ] \big \} \\ c _ {a _ {2}} ^ {2} = (1 - 0. 7 7 5 ^ {2}) \cdot c _ {a _ {1}} ^ {2} + 0. 7 5 5 ^ {2} \cdot (0. 8 7 7 + s q r t (2) - 1) / s q r t (2) \\ c _ {a _ {3}} ^ {2} = \big \{0. 5 \cdot \big [ (1 - 0. 7 3 ^ {2}) \cdot c _ {a _ {2}} ^ {2} + 0. 7 3 ^ {2} \cdot (1. 2 8 6 + s q r t (2) - 1) / s q r t (2) \big ] + 1 - 0. 5 \big \} \\ c _ {a _ {4}} ^ {2} = c _ {a _ {3}} ^ {2} \end{array} \right.
$$

$$
\left\{ \begin{array}{l} c _ {a _ {1}} ^ {2} = \frac {5}{1 0} 1 + \frac {5}{1 0} \left(0. 9 2 7 + 0. 6 c _ {a _ {3}} ^ {2}\right) \\ c _ {a _ {2}} ^ {2} = 0. 5 5 + 0. 4 c _ {a _ {1}} ^ {2} \\ c _ {a _ {3}} ^ {2} = 0. 5 \cdot \left[ 0. 6 4 + 0. 4 6 7 c _ {a _ {2}} ^ {2} \right] + 1 - 0. 5 \\ c _ {a _ {4}} ^ {2} = c _ {a _ {3}} ^ {2} \end{array} \right.
$$

$$
\left\{ \begin{array}{l} c _ {a _ {1}} ^ {2} = 1. 2 8 4 \\ c _ {a _ {2}} ^ {2} = 1. 0 9 \\ c _ {a _ {3}} ^ {2} = 1. 0 6 8 \\ c _ {a _ {4}} ^ {2} = 1. 0 6 8 \end{array} \right.
$$

$$
C T _ {1} = \left(\frac {1 . 2 8 4 + 0 . 8 7 7}{2}\right) \left(\frac {0 . 7 7 5 ^ {s q r (2 ^ {\star} 2 + 2) - 1}}{2 (1 - 0 . 7 7 5)}\right) \cdot 0. 1 5 5 + 0. 1 5 5 = 0. 4 1 2 h
$$

$$
W I P _ {1} = \lambda_ {1} C T _ {1} = 4. 1 2 j
$$

$$
C T _ {2} = \left(\frac {1 . 0 9 + 1 . 2 8 6}{2}\right) \left(\frac {0 . 7 3 ^ {s q r (2 * 2 + 2) - 1}}{2 (1 - 0 . 7 3)}\right) \cdot 0. 1 4 6 + 0. 1 4 6 = 0. 3 5 h
$$

$$
W I P _ {2} = \lambda_ {2} C T _ {2} = 3. 5 j
$$

$$
C T _ {3} = \left(\frac {1 . 0 6 8 + 1 . 4 7 2}{2}\right) \left(\frac {0 . 6 3}{1 - 0 . 6 3}\right) \cdot \frac {7 . 5}{6 0} + \frac {7 . 5}{6 0} = 0. 3 2 h
$$

$$
W I P _ {3} = \lambda_ {3} C T _ {3} = 1. 6 j
$$

$$
C T _ {4} = \left(\frac {1 . 0 6 8 + 0 . 7 5 8}{2}\right) \left(\frac {0 . 9 1}{1 - 0 . 9 1}\right) \cdot \frac {1 0 . 9}{6 0} + \frac {1 0 . 9}{6 0} = 1. 8 5 h
$$

$$
W I P _ {4} = \lambda_ {4} C T _ {4} = 9. 2 5 j
$$

$$
W I P _ {n e t w o r k} = 1 8. 4 7 j, C T _ {n e t w o r k} = \frac {W I P}{T H} = \frac {1 8 . 4 7}{5} = 3. 6 9 4 h
$$

5)Aline consists of 2 single capacity workstations.The arrival rate of job A to the system is 4 jobs per hour, exponentially distributed.Thearrival rateofjobBto the system is5 jobsper hour,also exponentiallydistributed. After WS1,allthe jobs are moved to the second workstation.The processing time data of both the job types are reported in the following table.Which is the arrval rate and the square coefficient of variation of the arriving jobs in the workstation 2?

![](images/2d9b8403ca6b6100ad63ada3c72c5ce429359cfc18fd572d6951545764ebc7ee.jpg)

![](images/1150ad6b08cde426c9408751818d3d5e8482819665827adfe5803c17a5909f26.jpg)

Parameters of WS1

入a=4+5=9, Equal to the total rate of the arriving jobs in the workstation 2

$$
\mathrm {c} _ {\mathrm {a}} ^ {2} = 4 / 9 * 1 + 5 / 9 * 1 = 1
$$

$$
E [ T s (1) ] = 4 / 9 * 0. 1 + 5 / 9 * 0. 0 5 = 0. 0 7 2 2
$$

$$
c _ {s} ^ {2} (1) = [ 4 / 9 ^ {*} 0. 1 ^ {\wedge} 2 ^ {*} (1 + 1) + 5 / 9 ^ {*} 0. 0 5 ^ {\wedge} 2 ^ {*} (1 + 2) ] / 0. 0 7 2 2 ^ {\wedge} 2 - 1 = 1. 5 2
$$

$$
u = 4 ^ {*} 0. 1 + 5 ^ {*} 0. 0 5 = 0. 6 5
$$

$$
\mathrm {c} _ {\mathrm {d}} ^ {2} (1) = (1 - 0. 6 5 ^ {\wedge} 2) ^ {*} 1 + 0. 6 5 ^ {\wedge} 2 * 1. 5 2 = 1. 2 2
$$

6) Considera two-server system with non-identical machines, exponentially distributed inter-arrival and service times,and alimit offour jobs.The mean inter-arival rate isλ.The mean service rates areY<μ.Jobs cannot be split across machines. When there is not a queue of waiting jobs and the faster machine completes processing first,the job on the slower machine is immediately moved to the faster machine to complete processing.

(a) Develop the steady-state diagram of the number of jobs in the system and the flow rates between states.   
(b) Develop the system of equations describing the steady-state probabilities of being in each state.

![](images/d4518d1a2d77d92def56ea99146c858ff5b7d9c18aacceb4f6969edbe9ba3bb1.jpg)  
(a)   
(b)

$$
\left\{ \begin{array}{l} \lambda p _ {0} = \mu p _ {1} \\ \lambda p _ {1} = (\mu + \gamma) p _ {2} \\ \lambda p _ {2} = (\mu + \gamma) p _ {3} \\ p _ {0} + p _ {1} + p _ {2} + p _ {3} = 1 \end{array} \right.
$$

7) Complete the lower part of the VSM diagram represented in the figure with the timeline and compute the average values of WIP,TH and CT of the line assuming a customer demand of 500 items/day. Consider that each day has 8 working hours.

![](images/e26b414137273c264f1bf7da4635ffe488b11f4292f9785405c01898d476a83e.jpg)

![](images/d6ca96213fe976a2d224547325829aa644228dfe15f75f76ae0c35cad52ca87b.jpg)

![](images/4b2ae96a3f2dc24e5a16dc6f19f96bd74a9f8c3923a105ab6740d2091e0633dc.jpg)

![](images/8b893d3da203211ca1f1116fc1c24974f42366472c55058fd1eb0d018dcced27.jpg)

![](images/06a4975a9ffd7e66f847cdb096f6d745b6c8f3360d1a8bd1fa836ee4b1132079.jpg)

![](images/34792c653cefe58c60e8c857b9e4eac3715949f666f63abaa54e9d9e3e08f617.jpg)

![](images/9ba69abebd994595595d9224f12e7b85318fa772747adabf70500deaa66c59aa.jpg)

![](images/b50d631b9ebc6fb6273f71685f04f39382a83f532d3a2f39067622435d9ab874.jpg)

TH=5000 p/g = 5000/8= 625 p/h = 625/60= 10.42 p/min

WIP = TH * CT, CT=WIP/TH

CTq1 = WIP1/TH = 1860/10.42 = 178.56 min

CTq2 = WIP2/TH = 120/10.42 = 11.52 min

CTq3 = WIP2/TH = 120/10.42 = 11.52 min

CTq4 = WIP4/TH = 240/10.42 = 23.04 min

CTq5 = WIP5/TH = 240/10.42 = 23.04 min

$$
C T q 6 = W I P 6 / T H = 1 2 0 / 1 0. 4 2 = 1 1. 5 2 \min
$$

$$
C T q 7 = W I P 7 / T H = 1 8 0 / 1 0. 4 2 = 1 7. 2 5 \min
$$

$$
C T q 8 = W I P 7 / T H = 1 8 0 / 1 0. 4 2 = 1 7. 2 5 \min
$$

Production Lead Time = sum CT queues + CT machines = 293.7 +8 = 301.7 min

Value Added Time = 8 min

WIP = CT*TH = 301.7 min * 10.42 p/min = 3143,7 items
