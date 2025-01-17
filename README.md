# River Crossing Optimization
A genetic algorithm-based solution for optimizing product transportation across a river, considering time constraints and product incompatibilities.

## Project Description
This project solves an optimization problem where a set of products must be transported across a river. Each product has specific characteristics:
- Unique ID
- Expiry time
- Value
- Quantity
- List of incompatible products

### Problem Constraints
1. Maximum of two products can be transported per trip
2. Some products are incompatible and cannot be transported together
3. Each product has an expiry time
4. Each river crossing (round trip) counts as one time unit
5. If a product expires, its value is deducted from the total profit
6. If a product crosses before expiry, its value is added to the total profit

## Usage
Run the code in a Jupyter Notebook environment:

```python
# Initialize parameters and products
products, MAX_TRIPS, population_size, parent_ratio, elite_ratio, mutation_rate, inheritance_ratio, generations = init()

# Create Genetic Algorithm instance
ga = GeneticAlgorithm(products, MAX_TRIPS, population_size, parent_ratio, 
                      elite_ratio, mutation_rate, inheritance_ratio, generations)

# Run the algorithm
ga.run()
```

## Code Structure

### Classes
1. `Product` Class
   - Represents a product with its properties
   - Handles compatibility checks between products

2. `GeneticAlgorithm` Class
   - Main implementation of the genetic algorithm
   - Handles population generation, selection, crossover, and mutation
   - Implements fitness evaluation and chromosome validation

### Key Functions
- `generate_chromosome()`: Creates a valid transportation schedule
- `fitness()`: Evaluates the quality of a solution
- `selection()`: Implements elitism and roulette wheel selection
- `crossover()`: Creates new solutions from selected parents
- `mutate_chromosome()`: Introduces random variations in solutions

### Algorithm Parameters
- `population_size`: Size of population (default: 50)
- `parent_ratio`: Proportion of parents selected (default: 0.4)
- `elite_ratio`: Proportion of elite solutions preserved (default: 0.2)
- `mutation_rate`: Probability of mutation (default: 0.01)
- `inheritance_ratio`: Inheritance probability in crossover (default: 0.7)
- `generations`: Number of generations to run (default: 10)

## Output Analysis
The algorithm provides detailed analysis at each generation:
- Generated chromosomes (transportation schedules)
- Fitness values
- Chromosome validity
- Number of trips used
- Delivery percentage for each product
- Summary statistics

### Sample Output Format
```
Generation X/Y
-------------
Chromosome | Fitness | Valid | Trips Used | P1% | P2% | ...
Solution 1 |   120   |  Yes  |     8      | 100 | 75  | ...
Solution 2 |   100   |  Yes  |     7      | 80  | 100 | ...
...
Summary    |Best: 120|Valid: 45/50|Avg: 7.5
```

## Requirements
- Python 3.7+
- pandas
- Jupyter Notebook
- IPython

## Algorithm Features
1. **Early Stopping**
   - Stops if no improvement for 3 consecutive generations
   - Helps avoid unnecessary computations

2. **Solution Validation**
   - Checks expiry constraints
   - Verifies product compatibility
   - Ensures quantity limitations

3. **Adaptive Mutation**
   - Implements three mutation strategies:
     - Swap trips
     - Move products between trips
     - Remove products from trips

## Contributing
1. Fork the repository
2. Make your changes
3. Submit a Pull Request

