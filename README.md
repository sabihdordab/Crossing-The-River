# Genetic Algorithm for Shipment Optimization

This project implements a genetic algorithm to optimize shipment planning, ensuring products are grouped into valid trips while maximizing overall value. The solution adheres to constraints such as product incompatibilities and delivery limits.

---

## Features

1. **Product Representation**:
   - Each product has attributes like ID, expiry date, value, quantity, and incompatibilities with other products.
   - Products cannot be shipped together if they are incompatible.

2. **Genetic Algorithm Implementation**:
   - **Chromosome Representation**: A chromosome represents a list of trips, where each trip contains valid product groupings.
   - **Fitness Function**: Evaluates chromosomes based on total product value delivered and constraint satisfaction.
   - **Selection Methods**: Combines elitism and roulette wheel selection to choose parents.
   - **Crossover and Mutation**: Generates offspring by combining and altering parent chromosomes.
   - **Validation**: Ensures all chromosomes meet delivery and compatibility constraints.

3. **Population Analysis**:
   - Provides insights into the population's fitness, validity, and delivery performance using pandas.

4. **Extensibility**:
   - Supports custom configurations for products, genetic parameters, and constraints.

---

## Configuration

You can customize the following parameters:

- **Genetic Algorithm Settings**:
  - `POPULATION_SIZE`: Number of chromosomes in each generation.
  - `MUTATION_RATE`: Probability of mutation in a chromosome.
  - `CROSSOVER_RATE`: Probability of crossover between parent chromosomes.
  - `MAX_GENERATIONS`: Maximum number of generations.

- **Shipment Constraints**:
  - `MAX_TRIPS`: Maximum trips allowed in a chromosome.
  - Product incompatibilities, quantities, and values.

---

## Example Output

The program will display detailed information, including:

- Initial population fitness and validity.
- Fitness improvements over generations.
- Best solution:
- ...