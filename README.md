# Dataset-Sentinel

Dataset containing all analyzed projects for the sentinel experiment

## Introduction

This project ...

## meta-data description

There is the list of the metadata we have :

- line coverage
- method coverage
- class coverage
- branch coverage
- number of lines of code: this number is calculated by cloc (https://github.com/aldanial/cloc)
- Github link to the project
- number of stars of the project
- date of the last commit
- average number of commits in the last 4 weeks

## commons-configuration

### meta-data

On the day of Mar 26, 2026, the meta-data were:

- line coverage: 89%
- method coverage: 96%
- class coverage: 91%
- branch coverage: 81%
- number of lines of code: https://github.com/apache/commons-configuration
- number of stars of the project: 212
- date of the last commit: Mar 23, 2026
- average number of commits in the last 4 weeks: 2.75

### How we found the project

### Difficulties encountered

As it twas the first projevct we have done, we had to understand how the configuration file and the sentinel tool work. This was particulary hard at the beginning when there was only a small documentation (which had been completed later during the project). For the first part of the project (the measurment tool), there was no other difficulties. For the second part (instrument constructor tool), we had come little problems:

- Apache rat was blocking the execution of the test suite, so the solution was to skip the Apache rat execution
- One file contained an enum structure, which is not well-superted by Spoon, so we made Spoon ignore this file
- Some tests in the test suite failed, so we had to skip them
