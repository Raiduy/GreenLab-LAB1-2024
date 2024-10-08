# Using Hooks in Experiment-Runner
Hooks in `experiment-runner` are specific methods within the `RunnerConfig` class. They allow you to execute actions at various points during the lifecycle of an experiment. These hooks can be used to prepare data, initiate measurements, handle results, etc.

# Hooks Descriptions
 - `before_experiment()`: called once before the entire experiment starts. It is generally used to perform any initial setup required for the experiment
 - `before_run()`: invoked before each individual run within an experiment
 - `start_run()`: called at the very start of each run
 - `start_measurement()`: triggered when the measurement phase of each run starts
 - `interact()`: used to interact with the running target system
 - `stop_measurement()`: called to stop any ongoing measurements 
 - `stop_run()` : called after a run completes
 - `populate_run_data()`: used to process and populate the run data once a run is completed
 - `after_experiment()`: called once after the entire experiment ends. It can be used to perform any cleanup or finalization required at the end of all runs
  

## Bonus Ex1 
Add Git committing commands in the `before_experiment()` hook. This will ensure all changes are backed up to the Git repository before the experiment begins

### Steps:
 - Open RunnerConfig.py

 - Find the `before_experiment()` function
 
 - Add `git add` and `git commit` commands
  
       Hint: Use the subprocess library to run Git commands



## Bonus Ex2
Move the `run_table.csv` to a targeted path

### Steps:
 - Open RunnerConfig.py

 - Find the after_experiment() function

 - Add a few lines to move the run_table.csv (which is stored in your configured result path after the experiment is done) to the targeted path (you can customize it yourself!)

       Hint: You can use the Path library from pathlib to handle file operations(the rename() or replace() methods could be helpful)


