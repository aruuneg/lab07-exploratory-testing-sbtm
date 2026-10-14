# Session Report

## Tester Information

- Name: ANAR BATBOLD
- Student Code: B170910823

## Session Information

- Session Type: Session-Based Test Management (SBTM)
- Application: Reading List
- Duration: 60 minutes
- Date: 2026-10-14

---

# Charter Summary

Objective:

Explore the Reading List application and identify functional, usability, data validation, and API-related defects.

Tours selected:

- Couch Potato Tour
- Data Tour
- Saboteur Tour

Reason for selection:

These tours focus on missing validation, unusual input values, incorrect data handling, and unexpected application behavior.

---

# Timeline

## 14:00 – 14:10

- Reviewed charter
- Started application
- Explored available functionality
- Reviewed book creation, search, deletion and statistics features

## 14:10 – 14:25 (Couch Potato Tour)

Activities:

- Tested empty inputs
- Tested missing title values
- Tested normal book creation

Findings:

- Empty title was accepted and stored successfully

Bug Reference:

- Bug #1

---

## 14:25 – 14:40 (Data Tour)

Activities:

- Added books with different names
- Tested lowercase search
- Tested uppercase search
- Tested long text input

Findings:

- Search functionality was case-sensitive

Bug Reference:

- Bug #3

---

## 14:40 – 14:50 (Saboteur Tour)

Activities:

- Investigated API endpoints
- Compared UI information with API statistics
- Checked consistency between displayed data and backend data

Findings:

- Statistics API returned an incorrect total count

Bug Reference:

- Bug #2

---

## 14:50 – 15:00

Activities:

- Reproduced discovered issues
- Captured screenshots
- Collected API evidence
- Prepared bug reports

---

# Defects Found

## Bug #1

Title:

```text
Empty book title can be added
```

Severity:

```text
Medium
```

Status:

```text
Reproduced
```

---

## Bug #2

Title:

```text
Statistics total count does not match displayed books
```

Severity:

```text
Medium
```

Status:

```text
Reproduced
```

---

## Bug #3

Title:

```text
Search is case-sensitive
```

Severity:

```text
Medium
```

Status:

```text
Reproduced
```

---

# Obstacles Encountered

1. Determining whether statistics inconsistency was caused by the UI or the API required additional API investigation.
2. Search behavior initially appeared correct until different text casing was tested.
3. Several defects required repeated execution to verify reproducibility.

---

# Coverage

Areas covered during the session:

- Book creation
- Search
- Statistics
- User interface messages
- REST API behavior

Areas not covered:

- Performance
- Security
- Concurrent access
- Cross-browser compatibility

---

# Session Assessment

The exploratory session successfully identified three independent defects. The most serious issue was the statistics inconsistency because it affects the accuracy of information presented to users. Missing validation for empty titles can reduce data quality. Case-sensitive search negatively affects usability and user experience. The selected tours were effective for discovering validation, data consistency, and usability defects. Additional exploratory sessions focusing on API robustness and security would likely uncover further issues.