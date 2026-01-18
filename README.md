# Predator-Prey Ecosystem Simulation

A agent-based modeling simulation of a predator-prey ecosystem built using the Mesa framework. This project demonstrates emergent behaviors in ecological systems through simple agent interactions.

## Overview

This simulation creates a virtual ecosystem where prey agents move around a grid while trying to avoid predator agents. Predators hunt prey to gain energy, while prey lose their lives when caught. The simulation tracks the population dynamics and visualizes the distribution of prey lives and predator energies over time.

## Features

- **Agent-Based Modeling**: Uses Mesa framework for robust agent simulation
- **Grid-Based Movement**: Agents move on a toroidal grid with Moore neighborhood (8 adjacent cells)
- **Predator-Prey Interactions**: Realistic hunting and survival mechanics
- **Visual Analytics**: Histogram distributions of prey lives and predator energies
- **Configurable Parameters**: Easily adjust population sizes and grid dimensions

## Requirements

```
mesa
matplotlib
seaborn
```

## Installation

1. Clone this repository or download the simulation file
2. Install the required dependencies:

```bash
pip install mesa matplotlib seaborn
```

## Usage

Run the simulation directly:

```bash
python predator_prey_simulation.py
```

The simulation will:
1. Initialize 200 prey agents and 100 predator agents on a 50x50 grid
2. Run for 500 time steps
3. Display two histograms showing the final distribution of prey lives and predator energies

## How It Works

### Agent Types

**Prey Agents**
- Start with 1 unit of life
- Move randomly to adjacent cells each step
- Lose 1 life when eaten by a predator
- Die and are removed when life reaches 0

**Predator Agents**
- Start with 1 unit of energy
- Move randomly to adjacent cells each step
- Gain 1 energy when they eat a prey
- Die and are removed if energy drops below 0

### Simulation Parameters

You can modify these parameters in the code:

```python
model = World_model(X, Y, width, height)
```

- `X`: Number of prey agents (default: 200)
- `Y`: Number of predator agents (default: 100)
- `width`: Grid width (default: 50)
- `height`: Grid height (default: 50)

Adjust the number of simulation steps:

```python
for i in range(500):  # Change 500 to desired number of steps
    model.step()
```

## Customization Ideas

- Modify prey reproduction rates when they survive
- Add energy decay for predators over time
- Implement different movement strategies (e.g., prey fleeing from nearby predators)
- Track population dynamics over time with line graphs
- Add vegetation or resources for prey to consume
- Experiment with different grid sizes and population ratios

## Output

The simulation generates two visualization plots:

1. **Distribution of Prey Lives**: Shows how many prey agents have each life value
2. **Distribution of Predator Energies**: Shows the energy distribution across all predators

## Notes

- The grid uses a toroidal topology (edges wrap around)
- Agents are shuffled each step to prevent order-based bias
- Multiple agents can occupy the same cell
- Console output shows progress through simulation steps

## License

This project is open source and available for educational and research purposes.

## Contributing

Feel free to fork this project and experiment with different ecological dynamics. Potential improvements include adding data collection for time-series analysis, implementing more sophisticated behavioral patterns, or creating interactive visualizations.

## Author

Created as a demonstration of agent-based modeling using the Mesa framework.