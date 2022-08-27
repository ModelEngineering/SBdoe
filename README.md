# SBdoe
Tool for designing and running computational experiments in systems biology.

# Features
* **Experiment designer** provides a way to specify features, levels, and experiments (specifications of features and levels to evaluate).
* **Experiment runner** executes one or more previously specified experiments and collections statistics. Experiments can be run in parallel using ``dask``.
* **Experiment planner** provides time estimates for running a set of experiments.

# Concepts
* A **factor** is something that is changed in an experiment, such as start concentration of a species and algorithm for parameter estimation.
* A **level** for a factor is a value that is assigned the factor for an experiment.
* **Factor space** has dimensions of factors, and the coordinates for a factor are its levels.
* A **condition** is a collection of pairs factor and level.
* A **work unit** is a collection of conditions. Typically, conditions are chosen as a hypercube in factor space.
