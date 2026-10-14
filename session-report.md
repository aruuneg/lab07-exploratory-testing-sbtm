\# Session Report



\## Tester



ANAR BATBOLD



\## Student Code



B170910823



\## Session Information



\- Session Type: SBTM Exploratory Testing

\- Duration: 60 minutes

\- Application: Reading List

\- Charter: Reading list application functionality and robustness



\## Areas Covered



\- Add book

\- Search book

\- Delete book

\- Statistics

\- REST API



\## Tours Used



\### Couch Potato Tour



Tested empty inputs, invalid values and missing data.



\### Data Tour



Tested long strings, duplicate data and unusual values.



\### Saboteur Tour



Attempted to break functionality through invalid actions and API usage.



\## Bugs Found



\### Bug 1



Empty book title can be added.



Severity: Medium



\### Bug 2



Statistics total count does not match actual number of books shown.



Severity: Medium



\### Bug 3



Search is case-sensitive and does not find existing books when case differs.



Severity: Medium



\## Observations



The application generally works for normal scenarios but lacks input validation in some areas. Statistics appear inconsistent with displayed data. Search functionality is less user-friendly due to case sensitivity.



\## Evidence



\- Screenshot for empty title acceptance

\- Screenshot for search case sensitivity

\- API response from `/api/stats`



\## Summary



Three unique defects were found during exploratory testing. The most important issues were missing validation, incorrect statistics calculation and search behavior. Further regression testing is recommended after defects are fixed.

