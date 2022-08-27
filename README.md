# SBdoe
Tool for designing and running computational experiments in systems biology.

# Features
* **Experiment designer** provides a way to specify features, levels, and experiments (specifications of features and levels to evaluate).
* **Experiment runner** executes one or more previously specified experiments and collections statistics. Experiments can be run in parallel using [``dask``](https://www.dask.org/).
* **Experiment planner** provides time estimates for running a set of experiments.

# Glossary of terms
* A **factor** is something that is changed in an experiment, such as start concentration of a species and algorithm for parameter estimation.
* A **level** for a factor is a value that is assigned the factor for an experiment.
* **Factor space** has dimensions of factors, and the coordinates for a factor are its levels.
* A **condition** is a collection of pairings of factors with their level so that all factors are assigned a level.
* An **experiment** is the execution of a condition that produces a collection of results.
* A **work unit** is a collection of experiments. Typically, the conditions for experiments are chosen as a hypercube in factor space.

# Application Programming Interface (API)
The user specifies (or manually creates) ``Factor`` objects that have attributes of ``name`` and data type for their ``level``.
A ``Condition`` is a dictionary of ``Factor`` keys whose value is the level for the ``Factor``.
An ``Experiment`` is a condition paired with an ``ExeprimentExecution``, a function that can interpret a condition,
run an experiment, and produce an ``ExperimentResult``.
A ``Workunit`` is a collection of ``Experiments`` that are submitted to the ``ExperimentScheduler``, which provides capabilities for monitoring progress and halting execution.
``ExperimentScheduler`` returns 0 or more ``ExperimentResult``.
