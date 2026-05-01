# Solution of multiple choice questions

1) Which is the best formalism to represent the pasta production cycle,from wheat grinding to packaging?

a) UML activity diagram   
b) Flow process chart (X)   
c）BPNM   
d） IDEF0

2) Which is the right Kendallnotation to indicate a workstation in which the inter-arrival time follows a normal distribution,the processing time follows an exponential distribution,there are three machines in paralll and the queue is unlimited?

a) M/G/3/∞   
b)N/E/3/0   
c) M/G/∞/3   
d) G/M/0/3   
e) G/M/3/∞ (X)

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
d）30%

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

2) In a system the mean arrival rate is λ = 6 jobs/hours, and it is exponentially distributed. The mean service times is E[Ts] = 0.5 hours, with a squared coeficients of variation C² = 0.8. Which is the number of parallel machines needed to get a utilization lower or equal to 0.9? Considering the obtained number of parallel machines, compute the CT, the WIP and the TH of the system.

Solution:

$$ \lambda = 6 \text{ jobs/h}, \quad E[T_s] = 0.5 \text{ h}, \quad C_s^2 = 0.8, \quad C_a^2 = 1 $$

$$ u \le 0.9 \implies \frac{\lambda \cdot E[T_s]}{c} \le 0.9 \implies c \ge \frac{6 \cdot 0.5}{0.9} = 3.33 \implies c = 4 $$

$$ u = \frac{\lambda \cdot E[T_s]}{c} = \frac{6 \cdot 0.5}{4} = 0.75 $$

$$ 
\begin{aligned} 
CT &= \left( \frac{C_a^2 + C_s^2}{2} \right) \cdot \frac{u^{\sqrt{2(c+1)}-1}}{c(1-u)} \cdot E[T_s] + E[T_s] \\ 
&= \left( \frac{1 + 0.8}{2} \right) \cdot \frac{0.75^{\sqrt{2(4+1)}-1}}{4(1-0.75)} \cdot 0.5 + 0.5 \\ 
&= 0.9 \cdot \frac{0.75^{2.162}}{1} \cdot 0.5 + 0.5 = 0.742 \text{ h} 
\end{aligned} 
$$

$$ TH = \lambda = 6 \text{ jobs/h} $$

$$ WIP = TH \cdot CT = 6 \cdot 0.742 = 4.45 \text{ jobs} $$


3) A line is composed of 3 single-capacity workstations. The arrival rate of jobs to the system is 2 jobs per hour, exponentially distributed. The first workstation fails on average every 2 hours and has a recovery time of 30 min with a coefficient of variation of 1.4. The processing time (in hours) and the squared coefficient of variation of the three workstations are reported in the following table. Find the system performance measures of CT, WIP, and TH. Approximate all the results to the second decimal digit.

| WS | $E[T_s(i)]$ | $C_s^2(i)$ |
| :---: | :---: | :---: |
| 1 | 0.30 | 2 |
| 2 | 0.45 | 1 |
| 3 | 0.35 | 0.5 |

Solution:

### Workstation 1 (WS 1)

**Parametri di Base:**

$$
\lambda(1) = 2 \text{ jobs/hour}
$$

$$
c_a^2(1) = 1
$$

**Affidabilità e Guasti (Disponibilità della Macchina):**

$$
E[R(1)] = 0.5 \text{ hours}
$$

$$
c_R^2(1) = (1.4)^2 = 1.96
$$

$$
E[F(1)] = 2 \text{ hours}
$$

$$
a(1) = \frac{E[F(1)]}{E[F(1)] + E[R(1)]} = \frac{2}{2.5} = 0.8
$$

**Tempo di Processamento Effettivo:**

*Nota: Dalle formule deduciamo che il tempo di servizio naturale è 

$E[T_s(1)] = 0.3$ e $c_s^2(1) = 2$.*

$$
E[T_e(1)] = \frac{E[T_s(1)]}{a(1)} = \frac{0.3}{0.8} = 0.375 \approx 0.38 \text{ hours}
$$

$$
c_e^2(1) = c_s^2(1) + \frac{(1 + c_R^2(1))a(1)(1 - a(1))E[R(1)]}{E[T_s(1)]} = 2 + \frac{(1 + 1.96)0.8(1 - 0.8)0.5}{0.3} = 2.79
$$

**Valutazione delle Prestazioni (VUT e Legge di Little):**

$$
u(1) = \lambda(1)E[T_e(1)] = 2 \cdot 0.38 = 0.76
$$

$$
CT_q(1) = \left( \frac{c_a^2(1) + c_e^2(1)}{2} \right) \left( \frac{u(1)}{1 - u(1)} \right) E[T_e(1)] = 2.2803 \approx 2.28 \text{ hours}
$$

$$
CT(1) = CT_q(1) + E[T_e(1)] = 2.28 + 0.38 = 2.66 \text{ hours}
$$

$$
WIP_q(1) = CT_q(1)\lambda(1) = 2.28 \cdot 2 = 4.56 \text{ jobs}
$$

$$
WIP(1) = CT(1)\lambda(1) = 2.66 \cdot 2 = 5.32 \text{ jobs}
$$

### Workstation 2 (WS 2)

**Parametri di Base (Input da WS 1):**

$$
\lambda(2) = \lambda(1) = 2 \text{ jobs/hour}
$$

$$
c_a^2(2) = c_d^2(1) = 2.03
$$

**Utilizzo della Macchina:**

$$
u(2) = \lambda(2) \cdot E[T_s(2)] = 2 \cdot 0.45 = 0.9
$$

**Valutazione delle Prestazioni (VUT e Legge di Little):**

$$
CT_q(2) = \left( \frac{ c_a^2(2) + c_s^2(2) }{ 2 } \right) \cdot \left( \frac{ u(2) }{ 1 - u(2) } \right) \cdot E[T_s(2)] = 6.1357 \approx 6.14 \text{ hours}
$$

$$
CT(2) = CT_q(2) + E[T_s(2)] = 6.14 + 0.45 = 6.59 \text{ hours}
$$

$$
WIP_q(2) = CT_q(2) \cdot \lambda(2) = 6.14 \cdot 2 = 12.28 \text{ jobs}
$$

$$
WIP(2) = CT(2) \cdot \lambda(2) = 6.59 \cdot 2 = 13.18 \text{ jobs}
$$

**Variabilità in Uscita (Linking Equation):**

$$
c_d^2(2) = \left( 1 - u(2)^2 \right) \cdot c_a^2(2) + u(2)^2 \cdot c_s^2(2) = 1.1957 \approx 1.20
$$

**Variabilità in Uscita (Linking Equation):**
$$
c_d^2(1) = (1 - u(1)^2)c_a^2(1) + u(1)^2 c_e^2(1) = 1.9473 \approx 2.0
$$

### Workstation 3 (WS 3)

**Parametri di Base (Input da WS 2):**

$$
\lambda(3) = \lambda(2) = 2 \text{ jobs/hour}
$$

$$
c_a^2(3) = c_d^2(2) = 1.20
$$

**Utilizzo della Macchina:**

$$
u(3) = \lambda(3) \cdot E[T_s(3)] = 2 \cdot 0.35 = 0.7
$$

**Valutazione delle Prestazioni (VUT e Legge di Little):**
*(Nota: basandoci sui dati della tabella iniziale per 

$E[T_s(3)]$ e $c_s^2(3)$

)*

$$
CT_q(3) = \left( \frac{ c_a^2(3) + c_s^2(3) }{ 2 } \right) \cdot \left( \frac{ u(3) }{ 1 - u(3) } \right) \cdot E[T_s(3)] = 0.6942 \approx 0.69 \text{ hours}
$$

$$
CT(3) = CT_q(3) + E[T_s(3)] = 0.69 + 0.35 = 1.04 \text{ hours}
$$

$$
WIP_q(3) = CT_q(3) \cdot \lambda(3) = 0.69 \cdot 2 = 1.38 \text{ jobs}
$$

$$
WIP(3) = CT(3) \cdot \lambda(3) = 1.04 \cdot 2 = 2.08 \text{ jobs}
$$

### Prestazioni della Linea (LINE / Network)

**Throughput del Sistema:**

$$
TH = 2 \text{ jobs/hour}
$$

**Work In Process Totale (WIP):**
*(Somma dei pezzi in lavorazione e in coda in tutte le postazioni)*

$$
WIP = WIP(1) + WIP(2) + WIP(3) = 20.58 \text{ jobs}
$$

**Cycle Time Totale (CT):**
*(Calcolato applicando la Legge di Little all'intero sistema)*

$$
CT = \frac{ WIP }{ TH } = \frac{ 20.58 }{ 2 } = 10.29 \text{ hours}
$$

4) A network of server workstations is represented in the figure. The processing time data are reported in the table. The jobs arrive at the network at a rate of 6 j/h with a squared coefficient of variation of 1.5. Compute the CT, CTq, WIP, and WIPq at each workstation. The workstation 1 fails on average every 4 hours and has a recovery time of 18 min with a squared coefficient of variation of 1.4. For each workstation, consider the minimum number of parallel machines such that the utilization is below

### Queuing Network Description

**1. System Input (External Arrival):**

*   An external flow enters **Node 1** with an arrival rate:
   
    $$ \gamma_1 = 6 \text{ j/h} $$

**2. Routing Probabilities ($r_{ij}$):**

*   **From Node 1:**
    *   $r_{12} = \frac{1}{3}$ (Flow to Node 2)
    *   $r_{13} = \frac{2}{3}$ (Flow to Node 3)
*   **From Node 2:**
    *   $r_{24} = 1$ (100% of the flow goes to Node 4)
*   **From Node 3:**
    *   $r_{34} = \frac{1}{2}$ (Flow to Node 4)
    *   $r_{35} = \frac{1}{2}$ (Flow to Node 5)
*   **From Node 4:**
    *   $r_{45} = 1$ (100% of the flow goes to Node 5)

**3. System Output:**

*   **Node 5** acts as the final terminal (sink node). It collects the flows from Node 3 and Node 4 before the jobs exit the system.

| WS | $E[T_s(i)]$ | $C_s^2(i)$ |
| :---: | :---: | :---: |
| 1 | 0.1 | 1 |
| 2 | 0.4 | 2.2 |
| 3 | 0.15 | 1.5 |
| 4 | 0.23 | 1.2 |
| 5 | 0.3 | 2 |

Solution:

The server network is sequential (there are no loops). Thus, we can evaluate the workstations singularly.

### Workstation 1 (WS 1) - Calcolo Parametri Effettivi

**Dati di Partenza (Parametri di Base e Guasti):**

$$
E[T_s] = 0.1 \text{ hours}
$$

$$
c_s^2 = 1
$$

$$
E[R] = 0.3 \text{ hours}
$$

$$
c_R^2 = 1.4
$$

$$
E[F] = 4 \text{ hours}
$$

$$
\lambda = \lambda_1 = 6 \text{ jobs/hour}
$$

$$
c_a^2 = c_a^2(1) = 1.5
$$

**Affidabilità e Guasti (Disponibilità della Macchina):**
Poiché WS1 è soggetta a guasti, dobbiamo calcolarne la disponibilità ($A$) per ottenere il tempo di servizio effettivo.

$$
A = \frac{ E[F] }{ E[R] + E[F] } = \frac{ 4 }{ 4.3 } \approx 0.930233
$$

**Tempi e Variabilità Effettivi:**

$$
E[T_e] = \frac{ E[T_s] }{ A } = \frac{ 0.1 }{ 0.930233 } \approx 0.1075 \text{ hours}
$$

$$
c_e^2 = c_s^2 + \frac{ (1 + c_R^2) \cdot A \cdot (1 - A) \cdot E[R] }{ E[T_s] } = 1 + \frac{ (1 + 1.4) \cdot 0.930233 \cdot (1 - 0.930233) \cdot 0.3 }{ 0.1 } \approx 1.46728
$$

**Utilizzo della Macchina:**

$$
u = E[T_e] \cdot \lambda = 0.1075 \cdot 6 = 0.645
$$

Poiché l'utilizzo ($u = 0.645$) è inferiore a 1, una singola macchina è sufficiente per gestire il carico di lavoro in questa postazione.

**Valutazione delle Prestazioni (VUT e Legge di Little):**

$$
CT_q = \left( \frac{ c_e^2 + c_a^2 }{ 2 } \right) \cdot \left( \frac{ u }{ 1 - u } \right) \cdot E[T_e] = \left( \frac{ 1.46728 + 1.5 }{ 2 } \right) \cdot \left( \frac{ 0.645 }{ 1 - 0.645 } \right) \cdot 0.1075 = 0.28978 \text{ hours}
$$

$$
CT = CT_q + E[T_e] = 0.28978 + 0.1075 = 0.39728 \text{ hours}
$$

$$
WIP_q = CT_q \cdot \lambda = 0.28978 \cdot 6 = 1.73868 \text{ jobs}
$$

$$
WIP = CT \cdot \lambda = 0.39728 \cdot 6 = 2.38368 \text{ jobs}
$$

**Variabilità in Uscita (Linking Equation):**

$$
c_d^2 = c_d^2(1) = \left( 1 - u^2 \right) \cdot c_a^2 + u^2 \cdot c_e^2 = \left( 1 - 0.645^2 \right) \cdot 1.5 + 0.645^2 \cdot 1.46728 \approx 1.486388
$$

### Workstation 2 (WS 2) - Flusso e Parametri

**Dati di Partenza (Dal problema e dallo splitting da WS 1):**

$$
p_{1,2} = \frac{ 1 }{ 3 }
$$

$$
\lambda = \lambda_2 = p_{1,2} \cdot \lambda(1) = \frac{ 6 }{ 3 } = 2 \text{ jobs/hour}
$$

$$
E[T_s] = 0.4 \text{ hours}
$$

$$
c_s^2 = c_s^2(2) = 2.2
$$

**Utilizzo della Macchina:**

$$
u = \lambda \cdot E[T_s] = 2 \cdot 0.4 = 0.8
$$

Poiché l'utilizzo ($u = 0.8$) è inferiore a 1, una singola macchina è sufficiente.

**Variabilità in Ingresso (Equazione di Splitting):**
*(Calcoliamo l'impatto della deviazione probabilistica sul coefficiente di variazione degli arrivi)*

$$
c_a^2 = c_a^2(2) = \left( \frac{ \lambda_1 }{ \lambda_2 } \right) \cdot p_{1,2} \cdot \left( p_{1,2} \cdot c_d^2(1) + 1 - p_{1,2} \right) = \left( \frac{ 6 }{ 2 } \right) \cdot \frac{ 1 }{ 3 } \cdot \left( \frac{ 1 }{ 3 } \cdot 1.486388 + 1 - \frac{ 1 }{ 3 } \right) \approx 1.16129
$$

**Valutazione delle Prestazioni (VUT e Legge di Little):**

$$
CT_q = \left( \frac{ c_s^2 + c_a^2 }{ 2 } \right) \cdot \left( \frac{ u }{ 1 - u } \right) \cdot E[T_s] = \left( \frac{ 2.2 + 1.16129 }{ 2 } \right) \cdot \left( \frac{ 0.8 }{ 1 - 0.8 } \right) \cdot 0.4 \approx 2.689703 \text{ hours}
$$

$$
CT = CT_q + E[T_s] = 2.689703 + 0.4 = 3.089703 \text{ hours}
$$

$$
WIP_q = CT_q \cdot \lambda = 2.689703 \cdot 2 = 5.379407 \text{ jobs}
$$

$$
WIP = CT \cdot \lambda = 3.089703 \cdot 2 = 6.179407 \text{ jobs}
$$

**Variabilità in Uscita (Linking Equation):**

$$
c_d^2 = c_d^2(2) = \left( 1 - u^2 \right) \cdot c_a^2 + u^2 \cdot c_s^2 = \left( 1 - 0.8^2 \right) \cdot 1.16129 + 0.8^2 \cdot 2.2 \approx 1.826367
$$

### Workstation 3 (WS 3) - Flusso e Parametri

**Dati di Partenza (Dal problema e dallo splitting da WS 1):**

$$
p_{1,3} = \frac{ 2 }{ 3 }
$$

$$
\lambda = \lambda_3 = p_{1,3} \cdot \lambda(1) = \frac{ 2 }{ 3 } \cdot 6 = 4 \text{ jobs/hour}
$$

$$
E[T_s] = 0.15 \text{ hours}
$$

$$
c_s^2 = c_s^2(3) = 1.5
$$

**Utilizzo della Macchina:**

$$
u = \lambda \cdot E[T_s] = 4 \cdot 0.15 = 0.6
$$

Poiché l'utilizzo ($u = 0.6$) è inferiore a 1, una singola macchina è sufficiente.

**Variabilità in Ingresso (Equazione di Splitting):**

$$
c_a^2 = c_a^2(3) = \left( \frac{ \lambda_1 }{ \lambda_3 } \right) \cdot p_{1,3} \cdot \left( p_{1,3} \cdot c_d^2(1) + 1 - p_{1,3} \right) = \left( \frac{ 6 }{ 4 } \right) \cdot \frac{ 2 }{ 3 } \cdot \left( \frac{ 2 }{ 3 } \cdot 1.486388 + 1 - \frac{ 2 }{ 3 } \right) \approx 1.324258
$$

**Valutazione delle Prestazioni (VUT e Legge di Little):**

$$
CT_q = \left( \frac{ c_s^2 + c_a^2 }{ 2 } \right) \cdot \left( \frac{ u }{ 1 - u } \right) \cdot E[T_s] = \left( \frac{ 1.5 + 1.324258 }{ 2 } \right) \cdot \left( \frac{ 0.6 }{ 1 - 0.6 } \right) \cdot 0.15 = 0.317729 \text{ hours}
$$

$$
CT = CT_q + E[T_s] = 0.317729 + 0.15 = 0.467729 \text{ hours}
$$

$$
WIP_q = CT_q \cdot \lambda = 0.317729 \cdot 4 = 1.270916 \text{ jobs}
$$

$$
WIP = CT \cdot \lambda = 0.467729 \cdot 4 = 1.870916 \text{ jobs}
$$

**Variabilità in Uscita (Linking Equation):**

$$
c_d^2 = c_d^2(3) = \left( 1 - u^2 \right) \cdot c_a^2 + u^2 \cdot c_s^2 = \left( 1 - 0.6^2 \right) \cdot 1.324258 + 0.6^2 \cdot 1.5 \approx 1.387525
$$

### Workstation 4 (WS 4) - Superposizione dei Flussi

**Dati di Partenza (Dal problema e dai flussi di WS 2 e WS 3):**

$$
p_{2,4} = 1
$$

$$
p_{3,4} = 0.5
$$

**Tasso di Arrivo (Superposizione):**

$$
\lambda = \lambda_4 = p_{2,4} \cdot \lambda(2) + p_{3,4} \cdot \lambda(3) = 2 + \frac{ 4 }{ 2 } = 4 \text{ jobs/hour}
$$

$$
E[T_s] = 0.23 \text{ hours}
$$

$$
c_s^2 = c_s^2(4) = 1.2
$$

**Utilizzo della Macchina:**

$$
u = \lambda \cdot E[T_s] = 4 \cdot 0.23 = 0.92
$$

Poiché l'utilizzo ($u = 0.92$) è inferiore a 1, una singola macchina è sufficiente per gestire il carico.

**Variabilità in Ingresso (Equazione di Splitting & Superposition):**
*(Somma ponderata delle variabilità dei flussi provenienti da WS 2 e WS 3)*

$$
c_a^2 = c_a^2(4) = \left( \frac{ \lambda_2 }{ \lambda_4 } \right) \cdot p_{2,4} \cdot \left( p_{2,4} \cdot c_d^2(2) + 1 - p_{2,4} \right) + \left( \frac{ \lambda_3 }{ \lambda_4 } \right) \cdot p_{3,4} \cdot \left( p_{3,4} \cdot c_d^2(3) + 1 - p_{3,4} \right)
$$

$$
c_a^2(4) = \left( \frac{ 2 }{ 4 } \right) \cdot \left( 1.826367 + 1 - 1 \right) + \left( \frac{ 4 }{ 4 } \right) \cdot \frac{ 1 }{ 2 } \cdot \left( \frac{ 1 }{ 2 } \cdot 1.387525 + 1 - \frac{ 1 }{ 2 } \right) = 1.510065
$$

**Valutazione delle Prestazioni (VUT e Legge di Little):**

$$
CT_q = \left( \frac{ c_s^2 + c_a^2 }{ 2 } \right) \cdot \left( \frac{ u }{ 1 - u } \right) \cdot E[T_s] = \left( \frac{ 1.2 + 1.510065 }{ 2 } \right) \cdot \left( \frac{ 0.92 }{ 1 - 0.92 } \right) \cdot 0.23 \approx 3.58406 \text{ hours}
$$

$$
CT = CT_q + E[T_s] = 3.58406 + 0.23 = 3.81406 \text{ hours}
$$

$$
WIP_q = CT_q \cdot \lambda = 3.58406 \cdot 4 = 14.33624 \text{ jobs}
$$

$$
WIP = CT \cdot \lambda = 3.81406 \cdot 4 = 15.25624 \text{ jobs}
$$

**Variabilità in Uscita (Linking Equation):**

$$
c_d^2 = c_d^2(4) = \left( 1 - u^2 \right) \cdot c_a^2 + u^2 \cdot c_s^2 = \left( 1 - 0.92^2 \right) \cdot 1.510065 + 0.92^2 \cdot 1.2 \approx 1.247626
$$

### Workstation 5 (WS 5) - Superposizione e Macchine Multiple

**Dati di Partenza (Flussi in arrivo da WS 3 e WS 4):**

$$
p_{3,5} = 0.5
$$

$$
p_{4,5} = 1
$$

**Tasso di Arrivo (Superposizione):**

$$
\lambda = \lambda_5 = p_{3,5} \cdot \lambda(3) + p_{4,5} \cdot \lambda(4) = \frac{ 1 }{ 2 } \cdot 4 + 4 = 6 \text{ jobs/hour}
$$

$$
E[T_s] = 0.3 \text{ hours}
$$

$$
c_s^2 = c_s^2(5) = 2
$$

**Verifica della Stabilità e Utilizzo ($u$):**

$$
u_{\text{singola}} = \lambda \cdot E[T_s] = 6 \cdot 0.3 = 1.8
$$

Poiché l'utilizzo calcolato (1.8) è maggiore di 1, una singola macchina non è sufficiente. È necessario considerare un sistema con macchine in parallelo.
Poniamo **$c = 2$ macchine**:

$$
u = \frac{ \lambda \cdot E[T_s] }{ c } = \frac{ 6 \cdot 0.3 }{ 2 } = 0.9
$$

**Variabilità in Ingresso (Equazione di Superposition e Splitting):**
*(Somma ponderata dei coefficienti di variazione dei flussi in entrata)*

$$
c_a^2 = c_a^2(5) = \left( \frac{ \lambda_3 }{ \lambda_5 } \right) \cdot p_{3,5} \cdot \left( p_{3,5} \cdot c_d^2(3) + 1 - p_{3,5} \right) + \left( \frac{ \lambda_4 }{ \lambda_5 } \right) \cdot p_{4,5} \cdot \left( p_{4,5} \cdot c_d^2(4) + 1 - p_{4,5} \right)
$$

$$
c_a^2(5) = \left( \frac{ 4 }{ 6 } \right) \cdot \frac{ 1 }{ 2 } \cdot \left( \frac{ 1 }{ 2 } \cdot 1.387525 + 1 - \frac{ 1 }{ 2 } \right) + \left( \frac{ 4 }{ 6 } \right) \cdot \left( 1.247626 + 1 - 1 \right) \approx 1.229672
$$

**Valutazione delle Prestazioni per $m$ macchine (Formula VUT per $G/G/m$):**

$$
CT_q = \left( \frac{ c_s^2 + c_a^2 }{ 2 } \right) \cdot \left( \frac{ u^{\sqrt{ 2 \cdot c + 2 } - 1} }{ c \cdot (1 - u) } \right) \cdot E[T_s]
$$

$$
CT_q = \left( \frac{ 2 + 1.229672 }{ 2 } \right) \cdot \left( \frac{ 0.9^{\sqrt{ 2 \cdot 2 + 2 } - 1} }{ 2 \cdot (1 - 0.9) } \right) \cdot 0.3 \approx 2.097192 \text{ hours}
$$

**Calcolo Cycle Time (CT) e Work In Process (WIP):**

$$
CT = CT_q + E[T_s] = 2.097192 + 0.3 = 2.397192 \text{ hours}
$$

$$
WIP_q = CT_q \cdot \lambda = 2.097192 \cdot 6 = 12.47515 \text{ jobs}
$$

$$
WIP = CT \cdot \lambda = 2.397192 \cdot 6 = 14.27515 \text{ jobs}
$$

### Prestazioni della Linea (LINE / Network)

Il Work In Process (WIP) totale della linea è dato dalla somma dei WIP delle singole Workstation.

**Work In Process Totale (WIP):**

$$
WIP = WIP_1 + WIP_2 + WIP_3 + WIP_4 + WIP_5
$$

$$
WIP = 2.38368 + 6.179407 + 1.870916 + 15.25624 + 14.27515 = 39.9654 \text{ jobs}
$$

**Throughput (TH) e Cycle Time (CT):**
Il Cycle Time viene calcolato applicando la Legge di Little all'intero sistema. Il throughput della linea corrisponde al throughput della postazione finale (WS 5), ovvero $TH = 6$ jobs/hour.

$$
TH = 6 \text{ jobs/hour}
$$

$$
CT = \frac{ WIP }{ TH } = \frac{ 39.9654 }{ 6 } \approx 6.660899 \text{ hours}
$$

5) Consider the single server workstations network represented in figure. The processing times for each workstation are given in the table. For each workstation, compute the utilization and the SCV of arrival

### Queuing Network Description

**1. System Input (External Arrival):**
*   An external flow enters the system just before **Node 1** with an arrival rate of **5 j/h** (5 jobs per hour).

**2. Routing from Node 1:**
*   After processing at Node 1, the flow splits into two paths:
    *   **1/3** of the flow is routed to **Node 2**.
    *   **2/3** of the flow is routed to **Node 3**.

**3. Routing from Node 2:**
*   All jobs leaving Node 2 proceed directly to **Node 4** (implied probability of 1).

**4. Routing from Node 3 (The Feedback Loop):**
*   The flow leaving Node 3 splits equally into two distinct paths:
    *   **1/2** of the flow proceeds forward to **Node 4**.
    *   **1/2** of the flow is routed **backwards** to the beginning of the system. It merges with the initial external arrival stream (5 j/h) before re-entering **Node 1**. 

**5. System Output (Node 4):**
*   **Node 4** acts as the sink or final terminal for this network. It collects the forward-moving flows from both Node 2 and Node 3 before the jobs exit the system.

| WS | $E[T_s(i)]$ | $C_s^2(i)$ |
| :---: | :---: | :---: |
| 1 | 0.09 | 1.2 |
| 2 | 0.35 | 1.4 |
| 3 | 0.15 | 2 |
| 4 | 0.18 | 1.8 |

Solution:

### Workstation Arrival Rates (Traffic Equations)

To compute the workstation utilization, we first need to compute the exact arrival rates ($\lambda_i$) for each node, taking the feedback loop into account:

$$
\lambda_1 = 5 + 0.5 \lambda_3
$$

$$
\lambda_2 = \frac{1}{3} \lambda_1
$$

$$
\lambda_3 = \frac{2}{3} \lambda_1
$$

$$
\lambda_4 = \lambda_2 + \frac{1}{2} \lambda_3
$$

The values of $\lambda_i$ are evaluated by solving the following system of linear equations:

$$
\begin{cases}
\lambda_1 - 0.5 \lambda_3 = 5 \\
-\frac{1}{3} \lambda_1 + \lambda_2 = 0 \\
-\frac{2}{3} \lambda_1 + \lambda_3 = 0 \\
-\lambda_2 - \frac{1}{2} \lambda_3 + \lambda_4 = 0
\end{cases}
$$

### Risoluzione del Sistema di Equazioni

Il sistema di equazioni per i tassi di arrivo può essere scritto e risolto in **forma matriciale**:

$$
\underbrace{ \begin{bmatrix} 1 & 0 & -\frac{1}{2} & 0 \\ -\frac{1}{3} & 1 & 0 & 0 \\ -\frac{2}{3} & 0 & 1 & 0 \\ 0 & -1 & -\frac{1}{2} & 1 \end{bmatrix} }_{A} \cdot \underbrace{ \begin{bmatrix} \lambda_1 \\ \lambda_2 \\ \lambda_3 \\ \lambda_4 \end{bmatrix} }_{\boldsymbol{\lambda}} = \underbrace{ \begin{bmatrix} 5 \\ 0 \\ 0 \\ 0 \end{bmatrix} }_{b}
$$

Il sistema $A \boldsymbol{\lambda} = b$ può essere risolto calcolando la matrice inversa $\boldsymbol{\lambda} = A^{-1}b$:

$$
\boldsymbol{\lambda} = A^{-1}b = \begin{bmatrix} 1.5 & 0 & 0.75 & 0 \\ 0.5 & 1 & 0.25 & 0 \\ 1 & 0 & 1.5 & 0 \\ 1 & 1 & 1 & 1 \end{bmatrix} \begin{bmatrix} 5 \\ 0 \\ 0 \\ 0 \end{bmatrix} = \begin{bmatrix} 7.5 \\ 2.5 \\ 5 \\ 5 \end{bmatrix}
$$

---

**Metodo per Sostituzione**

Vale la pena notare che, per risolvere questo specifico problema, possiamo procedere anche per semplice sostituzione:

$$
\begin{cases}
\lambda_1 = 5 + 0.5 \lambda_3 \\
-\frac{2}{3} (5 + 0.5 \lambda_3) + \lambda_3 = 0 \implies \lambda_3 = 5 \\
-\frac{1}{3} \lambda_1 + \lambda_2 = 0 \\
-\lambda_2 - \frac{1}{2} \lambda_3 + \lambda_4 = 0
\end{cases}
$$

Quindi, una volta ottenuto il valore di $\lambda_3$, tutti gli altri valori possono essere calcolati a cascata:

*   **$\lambda_3 = 5$**

*   **$\lambda_1 = 5 + 0.5 \cdot \lambda_3 = 7.5$**

*   **$\lambda_2 = \frac{1}{3} \cdot \lambda_1 = 2.5$**

*   **$\lambda_4 = \lambda_2 + 0.5 \cdot \lambda_3 = 2.5 + 0.5 \cdot 5 = 5$**

### Utilizzo delle Workstation (Utilization)

Una volta noti i tassi di arrivo ($\lambda_i$), possiamo valutare l'utilizzo di ciascuna postazione calcolando $u_i = \lambda_i \cdot E[T_s(i)]$:

$$
u_1 = \lambda_1 \cdot E[T_s(1)] = 7.5 \cdot 0.09 = 0.675
$$

$$
u_2 = \lambda_2 \cdot E[T_s(2)] = 2.5 \cdot 0.35 = 0.875
$$

$$
u_3 = \lambda_3 \cdot E[T_s(3)] = 5 \cdot 0.15 = 0.75
$$

$$
u_4 = \lambda_4 \cdot E[T_s(4)] = 5 \cdot 0.18 = 0.90
$$

---

### Variabilità in Ingresso e in Uscita

Infine, dobbiamo calcolare lo Squared Coefficient of Variation (SCV) degli arrivi per ogni singola workstation. L'equazione generale di interconnessione (Linking Equation) per i flussi è:

$$
c_a^2(i) = \frac{\gamma_i}{\lambda_i} c_a^2(0,i) + \sum_{k=1}^{N} \frac{\lambda_k}{\lambda_i} p_{k,i} \left( p_{k,i} c_d^2(k) + 1 - p_{k,i} \right)
$$

Dove i termini della variabilità in uscita $c_d^2$ dalle singole macchine sono calcolati come:

$$
c_d^2 = \left( 1 - u^2 \right) c_a^2 + u^2 c_s^2
$$

### Calcolo della Variabilità (SCV) con Feedback

A causa del loop tra le workstation 1 e 3, non è possibile procedere in modo puramente sequenziale. Sostituendo $c_d^2 = (1 - u^2)c_a^2 + u^2 c_s^2$ nelle equazioni di interconnessione, otteniamo il seguente sistema lineare per i termini $c_a^2(i)$:

**Equazioni di Bilancio della Variabilità:**

$$
c_a^2(1) = 5/7.5 + (5/7.5 \cdot 0.5) \cdot [ 0.5 \cdot ( (1 - 0.75^2) c_a^2(3) + 0.75^2 \cdot 2 ) + 0.5 ]
$$

$$
c_a^2(2) = (7.5/2.5 \cdot 1/3) \cdot [ 1/3 \cdot ( (1 - 0.675^2) c_a^2(1) + 0.675^2 \cdot 1.2 ) + 2/3 ]
$$

$$
c_a^2(3) = (7.5/5 \cdot 2/3) \cdot [ 2/3 \cdot ( (1 - 0.675^2) c_a^2(1) + 0.675^2 \cdot 1.2 ) + 1/3 ]
$$

$$
c_a^2(4) = 0.5 \cdot [ (1 - 0.875^2) c_a^2(2) + 0.875^2 \cdot 1.4 ] + 0.5 \cdot [ 0.5 \cdot ( (1 - 0.75^2) c_a^2(3) + 0.75^2 \cdot 2 ) + 0.5 ]
$$

---

### Risoluzione del Sistema Ridotto (WS 1 e WS 3)

Per risolvere il sistema "a mano", isoliamo le equazioni interdipendenti delle postazioni 1 e 3:

1.  **$c_a^2(1) = 1.0208 + 0.07292 \cdot c_a^2(3)$**
2.  **$c_a^2(3) = 0.6978 + 0.3629 \cdot c_a^2(1)$**

Sostituendo la seconda nella prima, otteniamo i seguenti valori risolutivi:

*   **$c_a^2(1) = 1.1008$**
*   **$c_a^2(3) = 1.0973$**

Di conseguenza, possiamo calcolare i restanti valori di variabilità per le altre postazioni:

*   **$c_a^2(2) = 1.048675$**
*   **$c_a^2(4) = 1.310102$**

6) Consider a single server network with 3 workstations. There are 2 products, A and B. On average, there are every hour 5 A jobs and 4 B jobs (SCV of arrival 0,6 for A and 1,7 for B). After the WS1 process, 100% of A and 30% of B go into WS2. Knowing that 70% of B from WS1 and 100% of the products from WS2 go into WS3, compute the line TH, CT and WIP. The processing times data are given in the table.

### **Multi-Product Process Flow Description**

This diagram illustrates a multi-product queuing network involving three workstations (Nodes 1, 2, and 3) and two distinct job types, **Job A** and **Job B**.

---

#### **1. External Input**
*   Both **Job A** and **Job B** enter the system at **Node 1**.

#### **2. Routing from Node 1 (Splitting)**
After processing at Node 1, the flows are directed based on job type:
*   **Job A:** 100% of the Job A flow is routed directly to **Node 2**.
*   **Job B:** This flow is split into two paths:
    *   **30% of Job B** is routed to **Node 2**.
    *   **70% of Job B** is routed directly to **Node 3**.

#### **3. Workstation 2 (Node 2)**
*   **Input:** Node 2 receives the entire flow of Job A and a 30% fraction of the Job B flow.
*   **Output:** 100% of the items processed at Node 2 are then routed to **Node 3**.

#### **4. Workstation 3 (Node 3 - Sink)**
*   Node 3 is the final workstation where all system flows converge.
*   It receives the direct **70% flow of Job B** from Node 1.
*   It also receives the **combined output from Node 2** (which contains all of Job A and the remaining 30% of Job B).

| WS | $E[T_s]$ A (min) | $E[T_s]$ B (min) | $C_s^2$ A | $C_s^2$ B |
| :---: | :---: | :---: | :---: | :---: |
| **1** | 2 | 7 | 0.9 | 1.1 |
| **2** | 7 | 15 | 1.2 | 0.8 |
| **3** | 10 | 1 | 1 | 1 |

Solution:

## 1. Analisi dei Tassi di Arrivo ($\lambda$)
Calcoliamo i tassi di arrivo per ogni workstation (WS) basandoci sul diagramma di flusso (**image_59c893.png**).

*   **Ingressi esterni:**
    *   $\lambda_A = 5 \text{ jobs/h} = 0.08333 \text{ jobs/min}$
    *   $\lambda_B = 4 \text{ jobs/h} = 0.06667 \text{ jobs/min}$
*   **WS 1:** $\lambda_1 = \lambda_A + \lambda_B = 9 \text{ jobs/h} = \mathbf{0.15 \text{ jobs/min}}$
*   **WS 2:** $\lambda_2 = \lambda_A + (0.3 \cdot \lambda_B) = 5 + 1.2 = 6.2 \text{ jobs/h} = \mathbf{0.10333 \text{ jobs/min}}$
*   **WS 3:** $\lambda_3 = \lambda_2 + (0.7 \cdot \lambda_B) = 6.2 + 2.8 = 9 \text{ jobs/h} = \mathbf{0.15 \text{ jobs/min}}$

---

## 2. Caratterizzazione delle Workstation (Parametri Aggregati)
Dobbiamo calcolare il tempo di servizio medio ($E[T_s]$) e il coefficiente di variazione ($c_s^2$) pesati sul mix di prodotti.

### **Workstation 1**
*   **Tempo medio:** $E[T_s(1)] = \frac{5}{9}(2) + \frac{4}{9}(7) = \mathbf{4.222 \text{ min}}$
*   **Saturazione:** $u_1 = 0.15 \cdot 4.222 = \mathbf{0.6333}$
*   **Variabilità:** $E[T_s^2(1)] = \frac{5}{9}[2^2(0.9+1)] + \frac{4}{9}[7^2(1.1+1)] = 49.955$
*   **SCV Servizio:** $c_s^2(1) = \frac{49.955}{4.222^2} - 1 = \mathbf{1.802}$

### **Workstation 2**
*   **Tempo medio:** $E[T_s(2)] = \frac{5}{6.2}(7) + \frac{1.2}{6.2}(15) = \mathbf{8.548 \text{ min}}$
*   **Saturazione:** $u_2 = 0.10333 \cdot 8.548 = \mathbf{0.8833}$
*   **Variabilità:** $E[T_s^2(2)] = \frac{5}{6.2}[7^2(1.2+1)] + \frac{1.2}{6.2}[15^2(0.8+1)] = 165.322$
*   **SCV Servizio:** $c_s^2(2) = \frac{165.322}{8.548^2} - 1 = \mathbf{1.262}$

### **Workstation 3**
*   **Tempo medio:** $E[T_s(3)] = \frac{5}{9}(10) + \frac{4}{9}(1) = \mathbf{6.000 \text{ min}}$
*   **Saturazione:** $u_3 = 0.15 \cdot 6 = \mathbf{0.9000}$
*   **Variabilità:** $E[T_s^2(3)] = \frac{5}{9}[10^2(1+1)] + \frac{4}{9}[1^2(1+1)] = 112$
*   **SCV Servizio:** $c_s^2(3) = \frac{112}{6^2} - 1 = \mathbf{2.111}$

---

## 3. Analisi della Variabilità dei Flussi ($c_a^2$)

*   **WS 1 (Arrivo):** $c_a^2(1) = \frac{5}{9}(0.6) + \frac{4}{9}(1.7) = \mathbf{1.089}$
*   **WS 1 (Uscita):** $c_d^2(1) = (1-0.6333^2)1.089 + 0.6333^2(1.802) = \mathbf{1.374}$
*   **WS 2 (Arrivo):** $c_a^2(2) = \frac{6.2}{9}(1.374) + (1 - \frac{6.2}{9}) = \mathbf{1.258}$
*   **WS 2 (Uscita):** $c_d^2(2) = (1-0.8833^2)1.258 + 0.8833^2(1.262) = \mathbf{1.261}$
*   **WS 3 (Arrivo):** $c_a^2(3) = \frac{6.2}{9}(1.261) + \frac{2.8}{9}[0.7(1.374) + 0.3] = \mathbf{1.261}$

---

## 4. Prestazioni della Linea (VUT & Little)

Utilizziamo la formula di Kingman per il tempo in coda: $CT_q = \left( \frac{c_a^2 + c_s^2}{2} \right) \left( \frac{u}{1-u} \right) E[T_s]$.

| WS | $CT_q$ (min) | $CT$ (min) | $WIP$ (jobs) |
| :--- | :--- | :--- | :--- |
| **1** | $10.54$ | $14.76$ | **2.21** |
| **2** | $81.56$ | $90.11$ | **9.32** |
| **3** | $91.06$ | $97.06$ | **14.37** |

---

## 5. Risultati Finali

*   **Throughput (TH):** $9 \text{ jobs/h}$
*   **WIP Totale:** $2.21 + 9.32 + 14.37 = \mathbf{25.90 \text{ jobs}}$
*   **Cycle Time (CT):** $\frac{25.90}{9} = \mathbf{2.88 \text{ h}}$

**Riepilogo finale: [9 jobs/h, 2.88 h, 25.90 jobs]**
