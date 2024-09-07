# `experiment-runner` and `EnergiBridge`

This exercises will teach you how to use `EnergiBridge` together with the `experiment-runner` framework. Check the `experiment-runner` [repo](https://github.com/S2-group/experiment-runner/tree/master) for an overview of the framework. 

You will create an experiment using the framework and collect measures for different initial setups. The workflow for your experiment will be defined in the `RunnerConfig.py` file inside the experiment folder (see `experiment-runner/examples` for example experiments). 
## Setup
Start by creating your own `RunnerConfig` running (on your activated virtualenv):

```bash
$ python experiment-runner/ config-create examples/<your-example-name>
```
## Exercise 1
For now we're going to stick with a simple experiment with one single factor and one single level. Later on 
we will see how to run more interesting experiments. The focus of this exercise is to teach you how to use `EnergiBridge` as a profiler within the `experiment-runner` framework. For this, we just want a single run of 
the following command:

```bash
$ sleep 5
```
We will measure the total CPU enery and the total memory used by this program.

Edit the `create_run_table_model()` method as follows:
```python
def create_run_table_model(self) -> RunTableModel:
    """Create and return the run_table model here. A run_table is a List (rows) of tuples (columns),
    representing each run performed"""
    factor1 = FactorModel("example_factor1", ["example_treatment1"]) # just one factor with one level
    
    self.run_table_model = RunTableModel(
        factors=[factor1], data_columns=["total_cpu", "total_mem"] # we want to measure toatl cpu and memory
    )

    return self.run_table_model
```

Edit the `stop_run()` method as follows:
```python
    def stop_run(self, context: RunnerContext) -> None:
        """Perform any activity here required for stopping the run.
        Activities after stopping the run should also be performed here."""
        
        output.console_log("Config.stop_run() called!")

        self.profiler.wait()


```

Draw inspiration from the `examples` folder to:
- Run the command `$ sleep 3` using `EnergiBridge` at the start of the experiment (*Hints:* Edit `start_run()` and set `self.profiler`)
- Aggregate the raw data outputted by `EnergiBridge` to include it in the `RunTableModel` (*Hints:* edit `populate_run_data()` **paying attention to the column names in the raw data**)