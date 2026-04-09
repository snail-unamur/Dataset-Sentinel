DOI

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
        └──project_configuration
    └──readme.md #You are here
```

## Metadata dump

## Metadata description

List of metadata available for each project:

| Metadata              | Description                                                                                |
| --------------------- | ------------------------------------------------------------------------------------------ |
| GitHub link           | URL of the project's GitHub repository                                                     |
| Line coverage         | Percentage of lines of code executed during the test suite                                 |
| Method coverage       | Percentage of methods called during the test suite                                         |
| Class coverage        | Percentage of classes instantiated or accessed during the test suite                       |
| Branch coverage       | Percentage of code branches (if/else, switch…) covered during the test suite               |
| Lines of code         | Total number of Java lines of code, calculated by [cloc](https://github.com/aldanial/cloc) |
| Stars                 | Number of GitHub stars at the time of the snapshot                                         |
| Last commit date      | Date of the most recent commit at the time of the snapshot                                 |
| Avg commits / 4 weeks | Average number of commits per week over the last 4 weeks at the time of the snapshot       |

---

## commons-configuration

### Metadata

> Snapshot: Mar 26, 2026

| Field                 | Value                                           |
| --------------------- | ----------------------------------------------- |
| GitHub                | https://github.com/apache/commons-configuration |
| Line coverage         | 89%                                             |
| Method coverage       | 96%                                             |
| Class coverage        | 91%                                             |
| Branch coverage       | 81%                                             |
| Lines of code         | 53912                                           |
| Stars                 | 212                                             |
| Last commit           | Mar 23, 2026                                    |
| Avg commits / 4 weeks | 2.75                                            |

### How we found the project

Apache produces well-regarded, high-quality Java projects. We systematically tried all "commons" projects — commons-configuration was the first to work end-to-end.

### Difficulties encountered

Being our first project, the main challenge was understanding the configuration file and how the Sentinel tool works. Documentation was sparse early on and was completed progressively. For the instrumentation module specifically:

- **Apache Rat** was blocking the execution of the test suite → skipped Apache Rat execution
- **One file contained an enum structure**, which is not well-supported by Spoon → made Spoon ignore this file
- **Some tests in the test suite were failing** → skipped those tests

---

## jackson-core

### Metadata

> Snapshot: _date not yet recorded_

| Field                 | Value                                     |
| --------------------- | ----------------------------------------- |
| GitHub                | https://github.com/fasterxml/jackson-core |
| Line coverage         | —                                         |
| Method coverage       | —                                         |
| Class coverage        | —                                         |
| Branch coverage       | 75%                                       |
| Lines of code         | 86,513                                    |
| Stars                 | 2.4k                                      |
| Last commit           | Mar 29, 2026                              |
| Avg commits / 4 weeks | 6.5                                       |

### How we found the project

We explored projects listed on Awesome Java. Jackson was among them, leading us directly to jackson-core.

### Difficulties encountered

_Not yet documented._
