# QA and Testing Principle
Author: Pawel Prytlua

This document decribes my view on Quality Assurance and Testing aproaches, rules, processes, princinples that can be applied in various IT projects

## History
Version 0.1 - first draft


## Avoid single points of failure (many level of tests)
- QA team shall not be made a single point of failure
- There shall be tests at many level: including, design reviews, feature reviews, static code analysis, unit test, FE test, API Tests, Integration and E2E tests
- Developers shall be involved in unit and module test, some threshold shall be set for code coverage (60-70% at least)
- Shift left if possible - implemenet test as early as possible on many levels 

