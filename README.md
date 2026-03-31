# Dataset-Sentinel

Dataset containing all analyzed projects for the sentinel experiment (https://github.com/JeromeMaquoi/sentinel-experiments)

## Introduction

The sentinel experiment is a pipeline-based tool for making experiments on projects. For now, the pipeline consists of those modules:

- EnergyMeasurementsModule: measures the actual energy consumption of Java applications using JoularJX
- SpoonInstrumentConstructorModule: instruments Java source code to track constructor invocations using Spoon and sends the data to a backend for storage and analysis

In this dataset, we gathered all the measures retrieved by these two modules on the projects we found.

## meta-data description

There is the list of the metadata we have :

- Github link to the project
- doi: the doi of the data gathered for this project
- line coverage
- method coverage
- class coverage
- branch coverage
- number of lines of code: this number is calculated by cloc (https://github.com/aldanial/cloc) (only Java lines)
- number of stars of the project
- date of the last commit
- average number of commits in the last 4 weeks

## commons-configuration

### meta-data

On the day of Mar 26, 2026, the meta-data were:

- Github link to the project: https://github.com/apache/commons-configuration
- doi:
- line coverage: 89%
- method coverage: 96%
- class coverage: 91%
- branch coverage: 81%
- number of lines of code:
- number of stars of the project: 212
- date of the last commit: Mar 23, 2026
- average number of commits in the last 4 weeks: 2.75

### How we found the project

As Apache produces famous and qualitative Java project, we have tried all the "commons" project, and commons-configuration worked.

### Difficulties encountered

As it twas the first projevct we have done, we had to understand how the configuration file and the sentinel tool work. This was particulary hard at the beginning when there was only a small documentation (which had been completed later during the project). For the first part of the project (the measurment tool), there was no other difficulties. For the second part (instrument constructor tool), we had come little problems:

- Apache rat was blocking the execution of the test suite, so the solution was to skip the Apache rat execution
- One file contained an enum structure, which is not well-superted by Spoon, so we made Spoon ignore this file
- Some tests in the test suite failed, so we had to skip them

## jackson-core

### meta-data

On the day of ..., 2026, the meta-data were:

- Github link to the project: https://github.com/fasterxml/jackson-core
- doi:
- line coverage:
- method coverage:
- class coverage:
- branch coverage: 75%
- number of lines of code: 86513
- number of stars of the project: 2.4k
- date of the last commit: Mar 29, 2026
- average number of commits in the last 4 weeks: 6.5

### How we found the project

We tried someprojects from Java Awesome, including jackson, which leade us to jackson-core.

### Difficulties encountered
