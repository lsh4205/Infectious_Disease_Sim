# Infectious_Disease_Simulation
Simulate two infectious disease models, Well-Mixed SIR model and SIR model with Vaccinated group.
# Project Description
In our model, there are three types of people:
1. **susceptible** people, who have never had the disease;
2. **infected** people, who currently have the disease;
3. and **recovered** people, who had the disease once but no longer have
it.

> The disease can only spread from infected people to susceptible people. An infected person stays sick for some period, but then recovers;
once they have recovered, they can never get sick again.
Let’s assume the behavior of the disease is governed by the following mathematical model. Denote time by a continuous variable $t ≥ 0$, and let the state of the system be represented by the three-dimensional vector

```math
x = x(t)=
\begin{pmatrix}
S(t) \\
I(t) \\
R(t)
\end{pmatrix}
```
> where $S(t), \ I(t)$, and $R(t)$ denote the fractions of the population who are susceptible, infected, or recovered, espectively, at time $t$. Further assume no one is born or dies, so that 
```math
S(t) + I(t) + R(t) = 1
``` 

> Suppose the state $x$ evolves as an ordinary differential equation, 
``` math
Dx = f(x),
```
> where $f(x)$  is the vector function, 
``` math
f(x) = 
\begin{pmatrix}
-τ ⋅ S(t)⋅I(t) \\ 
τ ⋅ S(t) ⋅ I(t) - \frac{I(t)}{k}\\ 
\frac{I(t)}{k}
\end{pmatrix}
```
> The parameter $τ ≥ 0$ measures how quickly the disease can spread, with higher values corresponding to faster rates of spread. The parameter $κ > 0$ measures how quickly an infected person recovers, with higher values corresponding to slower (longer) recovery times.

## 1. Implement “Well-Mixed” SIR Model.
> If the infection lasts $k$ days, then we might assume as an approximation that the rate of recovery is equal to the number infected divided by $k$.  Thus, on average, $1/k$ of the infected individuals recover each day.

> From textbook, the author let $τ$ be the proportion of encounters between an infected individual and a susceptible individual that transmit the infection.  Then the rate of new infections should increaseas any of the parameters $I$, $S$, or $τ$ increases, so we model this rate as $τ\cdot I(t)\cdot S(t)$.

> Let the initial conditions be $I(0) = 0.01$ (initial infected population
of 1%), $S(0) = 0.99$, and $R(0) = 0$.

> Run a simulation until $I(t) < 10^{−4}$, the “Stopping Condition” for this experiment. At what time t does this condition occur? Report your stopping time results to two digits after the decimal point.Create a plot that shows how $S(t)$, $I(t)$, and $R(t)$ vary in time. 

### 1.1. Result of SIR-model
$τ$ is the proportion of encounters between an infected individual and a susceptible individual that transmit the infection.

The rate of recovery is equal to the number infected divided by $k$.  Thus, on average, $1/k$ of the infected individuals recover each day.

#### (a) $τ = 0.8$ and $k = 4$, (b) $τ = 0.4$ and $k = 4$, (c) $τ = 0.8$ and $k = 8$.
<img src="https://github.com/lsh4205/Infectious_Disease_Sim/assets/63761734/901f8f85-e3c9-4718-aa3f-ac5533c1b8d1" width="32%" height="32%">
<img src="https://github.com/lsh4205/Infectious_Disease_Sim/assets/63761734/3e947f26-f8e5-462a-a082-e63c833d691c" width="32%" height="32%">
<img src="https://github.com/lsh4205/Infectious_Disease_Sim/assets/63761734/77852948-7745-41cc-a8c7-f5999c13570b" width="32%" height="32%">

> (a) Peaks in Infected group at $10.0$ days with $32.69%$ and Stopping time: $51.47$ days.
> (b) Peaks in Infected group at $24.0$ days with $8.77%$ and Stopping time: $95.69$ days.
> (c) Peaks in Infected group at $10.0$ days with $55.28%$ and Stopping time: $81.95$ days.
