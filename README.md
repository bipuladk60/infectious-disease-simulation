# Stochastic Toy Simulation of Infectious Disease Transmission
![COVID Simulation](https://dl.dropboxusercontent.com/scl/fi/2t5uhcy0lap8fg1rlexnk/covid_simulation.gif?rlkey=ux6d3o1bvkp6gmyb1hfhtr6ni)

## Description
This project presents an agent-based model that simulates the transmission dynamics of an infectious disease within a population. Each individual in the simulation is represented by a dot and possesses unique characteristics influenced by several variables:

- **Recovery Day**: The number of days it takes for an individual to recover, representing their immunity. This is modeled using a Beta distribution to stochastically simulate varying immunity levels across the population.
- **Viral Load**: The intensity of the infection in an individual, which affects their likelihood of transmitting the virus to susceptible individuals. The viral load peaks around days 6-7 and is modeled discretely to align with the number of days the individual has been infected.
- **Transmission Probability**: The chance of the virus being transmitted from an infected individual to a susceptible one, dependent on both the distance between individuals and the viral load. This probability changes exponentially with distance.

Through this simulation, we can observe the dynamics of disease spread, including infection, recovery, reinfection, and mortality rates within a community setting.

## Features
- **Agent-based Modeling**: Each individual's progression through the disease is simulated based on personalized variables.
- **Beta Distribution for Recovery Times**: Utilizes the Beta distribution to assign recovery times, reflecting natural variability in immune response.
![Screenshot Example](https://dl.dropboxusercontent.com/scl/fi/9rkervgr5wjab5rzv017o/Screenshot-2024-04-08-at-8.35.10-PM.png?rlkey=irblkw01c6axvnrh63aoadcnt)

The plot clearly shows that the density peaks between days 15 and 16, indicating that the likelihood of the recovery period falling within this range is the highest.

- **Weighed Coin Probability**: In our simulation, disease transmission from an infected to a susceptible individual is modeled using a probabilistic approach, often described as a "weighted coin flip." Here’s how it works: We generate a random number between 0 and 1 with np.random.rand(). This number is uniformly distributed, meaning all outcomes are equally likely. Transmission occurs if this random number is less than the Transmission Probability (Tp), which is calculated based on factors like distance and viral load. The lower the Tp, the smaller the chance that the random number will fall below this threshold and result in transmission.
