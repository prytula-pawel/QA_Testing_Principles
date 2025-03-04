# QA and Testing Principle
**Author**: Pawel Prytula
**Last updated**: 03/03/2025

This document decribes my view on Quality Assurance and Testing aproaches, rules, processes, princinples that can be applied in IT projects in various industries. This is a generic document and principles and it’s weights my differ from project to project depending on many factor like project phase and maturity, project size, industry, available technology, QA team size, available budget or time contraints. 

## Document History
**Version 0.1** - first draft, document structure


## Avoid single points of failure (many level of tests)
- QA team shall not be made a single point of failure
- There shall be tests at many level: including, design reviews, feature reviews, static code analysis, unit test, FE test, API Tests, Integration and E2E tests
- Developers shall be involved in unit and module test, some threshold shall be set for code coverage (60-70% at least)
- Shift left if possible - implemenet test as early as possible on many levels 

## Manual first / automation later
- Good feature understanding and manual test first are important for automation to be effective
- Tester/QA shall be involved as soon as possible in feature design and implementation to be able to give valid feedback regarding functionalities and planned solution
- Well written and detailed test cases in comprehensive test plan shall be a baseline for further automation
- Topic that cannot be fully covered by automation (external automation, remote desktop accesses, integration to 3rd party software) can be mock or partially mock and if needed they need to be executed manually
- The higher the level of test the less mocking shall be involved (UT, FE only test sill ok, but no mocking in Integration E2E Tests)

## Browser/OS Support
- Check end customer needs & environment to narrow down possible use of OSes and browsers (some industries will only have PCs for example or use tabled often)
- Check browser stats page per region: **https://gs.statcounter.com**
- Choose 1 or 2 browser and OS as leading and run majority of test on them (for example Chrome & Windows), runs some smoke or ad hoc test on other combination from time to time

## Test Environments 
- There shall be at least 2 ENV Staging and Production, preferable 3, Staging, Integration, Production
- To assure stable test runs for manual or automated tests Integration shall be fairly stable or some test user/apps/setup can be created on Produciton
- Integration shall be as close as possible to Prod in relation to configuration etc.

## CI/CD machinery 
- CI/CD machine shall cover different level of test including final integration or E2E
- the CI machine (for testing) shall be build from scratch gradually, starting with basic smoke test
- It does not have to be automatically triggered with every build from the start  - if test are not stable/mature enough let them run on time-interval basics (some fixed time-slots to run during the day), then gradually transform to be build-triggered
- Improve CI loop test with feedback from bug triage, from customer, etc.
- CD without well-developed, comprehensive test at many levels does not make sense and can cause more troubles then benefits (frequent rollback due to blocker bugs etc.)

## Testing Strategy
(smoke, regression, feature, exploratory - schedule, duration, etc)
Build different test sets (smoke, regression, full)

## Bug handling process 
- Bug ticket flow shall be adjusted to company specific flow but in general:
- bugs shall be raised by QA team and or PM/Designers
- top prio production issues can have different flow as they need to be fixed ASAP
- in ideal world bug shall go through Bug Triage where Priority and Severity ranks are added/updated
- bug tickets is then assigned to a relevent sprint and/or developer (depedning on Priority and Severity)
- after bugfix is ready bug ticket is assigned back to QA team which shall always be the party officially confirming the fix (no self-closure by dev team)
- ideally bugs reports tickets shall always be closed by the reporter - so some exception are possible to the previous bullet-point (design bug closed by desinger)
- bug is first tested internally on Staging/Test Environment before being release to PROD (if possible)
- after PROD release bug fix is re-confirmed on PROD env
- High prio / blocker bugs shall have special flow (for example patch release could be released outside or regular release schedule -> see: Release Process)

## Release Process
- Release shall be planned in regular intervals (major, minor)
- Each release shall have clearly defined list of changes (features, bug-fixed, improvement), preferable as list of commits
- Hot fix release (patch) - does not have to be planned but shall only include top priority bug fixes or other crucial changes (security)
- We shall stick to the schedule and do not make to many exceptions

## Bug Triage & Test improvements based on bugs
- Bug triage / review meeting shall be held regularly in the project
- PM, QA Lead, Dev Lead shall participate (at least + more people if needed but the audience shall be relatively small)
- Each new raised bug since the last meeting shall be review in context of priority and severity and possibly assigned to a team (if possible, depending on strategy pull/push -> see Bug Handling Process)
- Top prio blocker bugs can be handled different way (prioritized outside of the meeting)
- In case there is a big push on developing new features in the project and bugs are being neglected, some improvements shall be introduce to keep bug fixing flow alive and do not allow number of defects to grow constantly (timeboxing, fixing low hanging fruits, etc)
- During the meeting or on later fix after the bug fix some improvements shall be initiated in test scenarios to extend the coverage to allow the bug to be found next time (manual or automated)

## Feature & Desing reviews by QA
- QA team / Testers shall be involve in the feature development as soon as possible (when design and requirements are being specified)
- Keeping Requ/Desing up to date after changes (limit number of US)

## Test case / test plan reviews
- Test cases shall be review internally in QA a team (both manual and automated)
- There shall be multiple focus on the review, considering factor as: logical flow of the TCes (including preconditions), test plan covering all needed reqs, test data validity and consistency, covering of any negative scenarios/flows etc
- In case of the new features - influencing the functionality of already existing features, some wider review might be needed to incorporate new feature into existing TC or add new TC for the feature and adjust old ones

## Requirements coverage
- Requirement coverage matrix
- Traceability of requirements to Test Case (bidirectional)

## Create QA corner for a Project (Docu)
- Using documentation management tool in the project (Confluence, Notion, etc) create a page for QA team
- This section shall cover all the basic that are needed for every QA: list of required tools, seting up env, test process and flows etc
- Docu needs to be update frequently to keep it up to date

## QA Team organization
- QA Lead
- DEV to test ratio ⅓ to ⅕ as average
- QA in project shall always be a whole team effort

## Error handling in the app/ Input field validation
- or in geneal any validation?
- where to place it FE or BE if BE then meaningful message shall be displayed to the user













