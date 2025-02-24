![#SIR Pandemic Simulation](assets/sir_logo.png)
---
This project is a simulation of a pandemic based on the classic SIR (Susceptible, Infected, Removed) model. It is implemented in **C++**, using numerical methods to model disease spread in a population. The simulation demonstrates data modeling, object-oriented programming, and numerical algorithm implementation.

## Requirements

- A C++ compiler supporting C++11 or later (GCC, Clang, MSVC)
- CMake (optional for project management)
- Standard Template Library (STL)

## Installation & Compilation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/jeffrunningit/SIR-model-pendemic-prediction-cpp.git
    cd SIR-pandemic-simulation-cpp
    ```

2. **Compile the program** (using `g++`):
    
    ```sh
    g++ -std=c++11 -o sir_simulation sir_simulation.cpp
    ```
    
    Or using CMake:
    
    ```sh
    mkdir build && cd build
    cmake ..
    make
    ```

3. **Run the simulation:**

    ```sh
    ./sir_simulation
    ```


## How It Works

The simulation initializes a fixed number of individuals in a 2D space. Each individual has a state (**Susceptible, Infected, or Removed**) and moves within the defined area. The model updates at discrete time steps, checking for infections using spatial proximity calculations.

- **Infection Handling:** Individuals within the infection radius of an infected individual may become infected based on a probability factor.
- **State Transitions:** An infected individual transitions to the "Removed" state after an infectious period.
<!-- - **Performance Optimization:** The implementation uses a spatial partitioning technique for efficient neighbor search. -->


# The SIR Model: A Mathematical Approach to Epidemic Spread

The **Susceptible-Infectious-Recovered (SIR) model** is a fundamental mathematical framework used to describe the spread of infectious diseases. It categorizes a population into three compartments:

- **Susceptible (S)**: Individuals who can contract the disease.
- **Infected (I)**: Individuals who have the disease and can transmit it.
- **Recovered (R)**: Individuals who have recovered and gained immunity.

## Differential Equations of the SIR Model
The SIR model is governed by the following differential equations:

```math
\frac{dS}{dt} = -\beta S I
```
```math
\frac{dI}{dt} = \beta S I - \gamma I
```
```math
\frac{dR}{dt} = \gamma I
```

where:
- **$\beta$** (infection rate) represents the rate at which susceptible individuals become infected.
- **$\gamma$** (recovery rate) is the rate at which infected individuals recover and move to the recovered compartment.

The basic reproduction number, **$R_0$**, is given by:
```math
R_0 = \frac{\beta}{\gamma}
```
If **$R_0 > 1$**, the disease spreads; if **$R_0 < 1$**, the outbreak diminishes.

## Simulation Parameters Analogy in Real-Life 
1. **Infection Radius**: In spatial models, this represents how far an infected person can spread the disease. It is analogous to physical distancing—larger infection radii correspond to high-contact environments.
2. **Infection Probability**: This measures how likely a susceptible person becomes infected upon contact. It depends on factors such as immunity and pathogen strength.
3. **Infectious Duration $1/\gamma$**: This defines how long an individual remains infectious before recovery. It correlates to real-world disease recovery periods.

## Applications and Significance
The SIR model is used in epidemiology to predict disease outbreaks, inform public health policies, and simulate containment strategies. By adjusting parameters, we can assess the impact of interventions like vaccination, social distancing, and quarantine measures. 

In summary, the SIR model provides a mathematical foundation to understand how diseases spread, how interventions alter transmission, and how outbreaks can be controlled.

## Further Reading

For more detailed explanation of the SIR model and epidemiological modeling, consider these resources:

- Beckley R, Weatherspoon C, Alexander M, Chandler M, Johnson A, Bhatt GS (2013). "Modeling epidemics with differential equations". Tennessee State University Internal Report

- Wikipedia page on [Compartmental models in epidemiology](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SIR_model)

