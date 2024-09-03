# Setting Up Your Environment

## Experiment Runner
Experiment Runner is a generic framework to automatically execute measurement-based experiments on any platform. The experiments are user-defined, can be completely customized, and expressed in python code!

**Step 1:** Fork [the repo](https://github.com/S2-group/experiment-runner/tree/master) and **clone the fork** to your computer.

**Step 2:** Follow the installation instructions [here](https://github.com/S2-group/experiment-runner/tree/master)

**Step 3:** Check if the example program ran correctly (i.e., no errors)

## [EnergiBridge](https://github.com/tdurieux/EnergiBridge)
Energibridge is a cross-platform energy measurement utility that provides support for Linux, Windows, and MacOS, as well as Intel, AMD, and Apple ARM CPU architectures.

**Step 1:** Follow the installation instructions for your platform from the [EnergiBrigde repo](https://github.com/tdurieux/EnergiBridge?tab=readme-ov-file#install).

**Step 2:** Check if EnergiBridge is installed using `energibridge -h`

**Step 3:** Track energy consumption of your first program 
```
energibridge --summary -o test.csv sleep 5
```

