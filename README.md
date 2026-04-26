# Optimization Algorithms Benchmark with CEC2017

A comprehensive benchmark comparison of metaheuristic optimization algorithms evaluated on the CEC2017 test function suite.

## Overview

This project implements and compares various population-based optimization algorithms:

- **TLBO** (Teaching-Learning-Based Optimization)
- **PSO** (Particle Swarm Optimization)
- **PSO-Hybrid** (PSO with Gaussian Mutation)
- **ABC** (Artificial Bee Colony)
- **Genetic Algorithm** (GA)

All algorithms are evaluated on the **CEC2017 benchmark suite** to assess their optimization performance across 30 real-world optimization problems.

## Features

✨ **Multi-algorithm comparison** - Evaluate and compare 5 different metaheuristic approaches  
📊 **CEC2017 Benchmark Suite** - Test on standardized, challenging optimization problems  
📈 **Convergence Analysis** - Track convergence history and performance metrics  
📉 **Statistical Results** - Compute mean and standard deviation across 30 independent runs  
🎯 **Performance Metrics** - Analyze best fitness values and convergence behavior  

## Project Structure

```
.
├── Working_File.ipynb              # Main Jupyter notebook with all algorithms and benchmarks
├── TLBO_results.csv               # Results from TLBO algorithm runs
├── PSO_Classique.csv              # Results from standard PSO runs
├── PSO_Hybride.csv                # Results from hybrid PSO runs
├── Algorithme_Genetique.csv       # Results from genetic algorithm runs
├── output.png                      # Visualization of results
├── results/                        # Directory containing detailed results
└── README.md                       # This file
```

## Requirements

- Python 3.7+
- NumPy
- Matplotlib
- CEC2017 test functions (included as dependency)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/optimization-benchmark.git
cd optimization-benchmark
```

2. Install dependencies:
```bash
pip install numpy matplotlib cec2017
```

3. Ensure the CEC2017 package is properly configured:
```bash
# The notebook expects the cec2017-py-master directory in the parent folder
```

## Usage

### Running the Notebook

1. Open the Jupyter notebook:
```bash
jupyter notebook Working_File.ipynb
```

2. Execute all cells to:
   - Load CEC2017 test functions
   - Run all optimization algorithms
   - Generate performance results
   - Create visualizations

### Using Individual Algorithms

#### TLBO (Teaching-Learning-Based Optimization)
```python
from Working_File import TLBO
best_fitness, history = TLBO(func, D=30, pop_size=30, max_evals=30000)
```

#### Standard PSO
```python
from Working_File import pso_standard
best_solution, history = pso_standard(func, rng, D=30, N=30, Tmax=1000)
```

#### Hybrid PSO with Mutation
```python
from Working_File import pso_hybrid
best_solution, history = pso_hybrid(func, rng, D=30, N=30, Tmax=1000, p_mut=0.05)
```

#### Artificial Bee Colony
```python
from Working_File import ABC
best_solution, history = ABC(func, rng, D, N, LB, UB, Tmax)
```

## Algorithm Details

### TLBO (Teaching-Learning-Based Optimization)
- **Teacher Phase**: Students learn from the best solution (teacher)
- **Learner Phase**: Students learn from random peers
- **Mutation Phase**: Gaussian mutation for diversity
- **Fitness evaluations**: Up to 30,000 evaluations per run

### PSO Variants
- **Standard PSO**: Classic velocity-position update with inertia weight
- **Hybrid PSO**: PSO combined with Gaussian mutation for enhanced exploration
- **Parameters**: c1=2.0, c2=2.0, inertia w linearly decreases from 0.9 to 0.4

### ABC (Artificial Bee Colony)
- **Employed Bees Phase**: Explore neighborhood around current solutions
- **Onlooker Bees Phase**: Select solutions based on fitness and exploit promising areas
- **Scout Bees Phase**: Abandon poorly performing solutions and reinitialize

### Genetic Algorithm
- **Selection**: Tournament selection
- **Crossover**: Single-point or multi-point crossover
- **Mutation**: Gaussian mutation

## Results

The project generates:

- **CSV Results Files**: Mean and standard deviation of best fitness values
- **Convergence Curves**: Visual comparison of algorithm performance
- **Statistical Analysis**: Mean and standard deviation across 30 runs

### Sample Output
```
F1: mean=1.2345e+02, std=4.5678e+01
F2: mean=5.6789e+02, std=1.2345e+02
...
```

## Benchmark Details

- **Dimension (D)**: 30
- **Population Size (N)**: 30
- **Maximum Evaluations**: 30,000 per run
- **Search Space**: [-100, 100]^D
- **Number of Runs**: 30 independent executions per function
- **Test Functions**: 30 CEC2017 benchmark functions

## Performance Comparison

Results show the comparative performance of different algorithms across various function types:
- **Unimodal functions** (simple landscape)
- **Multimodal functions** (many local optima)
- **Hybrid composition functions** (complex real-world problems)

## Visualization

The project generates convergence plots and performance comparisons for visual analysis of algorithm behavior.

## Citation

If you use this benchmark in your research, please cite:

```bibtex
@article{liang2013problem,
  title={Problem Definitions and Evaluation Criteria for the CEC 2017 Competition on Constrained Real-Parameter Optimization},
  author={Liang, JJ and Qu, BY and Gong, DW and Yao, XB},
  year={2017}
}
```

## Contributing

Contributions are welcome! Please feel free to:
- Add new optimization algorithms
- Improve existing implementations
- Enhance visualization and analysis
- Add new benchmark suites

## License

This project is licensed under the MIT License - see LICENSE file for details.

## Contact

For questions or discussions about this project, please open an issue on GitHub.

## Acknowledgments

- CEC2017 benchmark suite creators
- Research on metaheuristic optimization algorithms
- Open-source community for NumPy, Matplotlib, and Jupyter

---

**Note**: Make sure the CEC2017-py package is installed and properly configured before running the notebook. Adjust the `cec_path` in the first cell if your CEC2017 directory is in a different location.
