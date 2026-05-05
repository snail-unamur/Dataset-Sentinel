[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19481968.svg)](https://doi.org/10.5281/zenodo.19481968)

# Dataset-Sentinel

Dataset containing all analyzed projects for the Sentinel experiment — [sentinel-experiments](https://github.com/JeromeMaquoi/sentinel-experiments)

## Introduction

The Sentinel experiment is a pipeline-based tool for running experiments on Java projects. It currently consists of two modules:

- **EnergyMeasurementsModule**: measures the actual energy consumption of Java applications using JoularJX.
- **SpoonInstrumentConstructorModule**: instruments Java source code to track constructor invocations using Spoon, and sends the data to a backend for storage and analysis.

This dataset gathers all measures retrieved by these two modules across the projects analyzed.

## Repository hierarchy

```bash
organization
└──repository
    └──project_1
        └──joular.zip
        └──instrument_constructor.zip
        └──project_configuration.yml
    └──readme.md #You are here
```

The data are zipped because they are to big to be published on Zenodo.

For example, if you want to find the Joular's data for commons-configuration, you should follow the directory located at:

```bash
commons-configuration/joularjx_measurements_commons-configuration_525bd980b07dba983d931baeff573c0aa9880821.zip
```

and unzip the folder.

## Metadata dump

## Metadata description

List of metadata available for each project:

| Metadata                       | Description                                                                                                   |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------- |
| GitHub link                    | URL of the project's GitHub repository                                                                        |
| Commit SHA                     | SHA of the last commit                                                                                        |
| JDK version                    | JDK version required to run the project                                                                       |
| Total / Failed / Ignored tests | Detailed test results                                                                                         |
| Lines of code (LOC)            | Total Java LOC, calculated by [jacoco](https://github.com/jacoco/jacoco)                                      |
| Class coverage                 | % of classes instantiated during the test suite, by [jacoco](https://github.com/jacoco/jacoco)                |
| Method coverage                | % of methods called during the test suite, by [jacoco](https://github.com/jacoco/jacoco)                      |
| Line coverage                  | % of lines executed during the test suite, by [jacoco](https://github.com/jacoco/jacoco)                      |
| Branch coverage                | % of branches (if/else, switch…) covered during the test suite, by [jacoco](https://github.com/jacoco/jacoco) |
| Stars                          | Number of GitHub stars at the time of the snapshot                                                            |
| Last commit date               | Date of the most recent commit at the time of the snapshot                                                    |
| Avg commits / 4 weeks          | Average commits per 4-week period at the time of the snapshot                                                 |

---

## commons-configuration

### Metadata

> Snapshot: April 30, 2026

| Field                          | Value                                           |
| ------------------------------ | ----------------------------------------------- |
| GitHub                         | https://github.com/apache/commons-configuration |
| Commit SHA                     | 525bd980b07dba983d931baeff573c0aa9880821        |
| JDK version                    | 17.0.10                                         |
| Total / Failed / Ignored tests | 3012 / 0 / 2                                    |
| Lines of code (LOC)            | 53912                                           |
| Line coverage                  | 88% (9499 / 10735)                              |
| Class coverage                 | 97% (285 / 294)                                 |
| Method coverage                | 91% (2941 / 3240)                               |
| Branch coverage                | 82% (3579 / 4320)                               |
| Stars                          | 213                                             |
| Last commit                    | April 30, 2026                                  |
| Avg commits / 4 weeks          | 4.75                                            |

### How we found the project

Apache produces well-regarded, high-quality Java projects. We systematically tried all "commons" projects — commons-configuration was the first to work end-to-end.

### Difficulties encountered

Being our first project, the main challenge was understanding the configuration file and how the Sentinel tool works. Documentation was sparse early on and was completed progressively. For the instrumentation module specifically:

- **Apache Rat** was blocking the execution of the test suite → skipped Apache Rat execution
- **One file contained an enum structure**, which is not well-supported by Spoon → made Spoon ignore this file
- **Some tests in the test suite were failing** → skipped those tests

---

## jackson-core (WIP)

### Metadata

> Snapshot: April 30, 2026

| Field                          | Value                                     |
| ------------------------------ | ----------------------------------------- |
| GitHub                         | https://github.com/fasterxml/jackson-core |
| Commit SHA                     | 701cd6af465c586aa9b33e95294acde034bd17af  |
| JDK version                    | 17.0.10                                   |
| Total / Failed / Ignored tests | 1638 / 0 / 2                              |
| Lines of code (LOC)            | 18.889                                    |
| Class coverage                 | 97% (142 / 146)                           |
| Method coverage                | 82% (2144 / 2605)                         |
| Line coverage                  | 82% (15435 / 18.889)                      |
| Branch coverage                | 75% (8010 / 10583)                        |
| Stars                          | 2.4k                                      |
| Last commit                    | April 30, 2026                            |
| Avg commits / 4 weeks          | 7.75                                      |

### How we found the project

We explored projects listed on Awesome Java. Jackson was among them, leading us directly to jackson-core.

### Difficulties encountered

As the sentinel experiment code base is using jackson core, there was confusion between the jackson core project we were analysing and the code used in the sentinel experiment project, which was causing a class duplication error.
