# 🧪 Final Group Test Report Template — Word Puzzle Game Plus

**Level:** Intermediate QA | **Week 5:** Test Management

**Course:** Software Testing & Quality Assurance  
**Module:** Test Management (Week 5)  
**Project Type:** Group Assessment  
**Submission Date:** 2025-10-28

## Team Information

| Role | Name | Responsibilities |
|------|------|------------------|
| Test Manager | Ojutiwon Anuoluwapo Mautin | Planning, scheduling, coordination, metric tracking |
| Risk Analyst | Steven Gulu | Risk identification, prioritization, test design linkage |
| Test Executor | Too Kelvin| Execution, evidence capture, defect logging |

## Group Rules

- Each student must belong to only one group.
- Duplicate membership or multiple submissions will result in invalidation.
- Every group member must contribute towards this project

## Project Overview

**System Under Test:** Word Puzzle Game Plus  
**Technology Stack:** HTML, CSS, JavaScript  
**Environment:** Chrome Browser (Desktop)

### Features Under Test

| Feature | Description | Risk Category |
|---------|-------------|---------------|
| Reset Game | Clears score and progress instantly | |
| Leaderboard | Stores top 3 scores in localStorage | |
| Bonus Round | Every 3 puzzles → doubles score | |

## Test Plan

### Objectives
- Ensure all core features (Reset Game, Leaderboard, Bonus Round) function as expected.

- Validate usability, responsiveness, and data persistence in Chrome (Desktop).

- Identify and log defects, risks, and usability issues for resolution.

### Scope

**In Scope:**
- 1. Reset Game Button
  Does it clear the board properly?
  Does it reset the score and timer?

- 2. Leaderboard Feature
  Is the score saved correctly in localStorage?
  Does it show the top scores in the right order?

- 3. Bonus Round
  Does the multiplier apply correctly?
  Is the bonus triggered at the right time?
- 4. UI/UX on Chrome Desktop
  Are buttons clickable?
  Is the layout responsive and readable?

**Out of Scope:**
- Mobile browser testing

- Backend/database testing (no server-side logic)
---

## 🛠 Test Tools & Resources

### 🔧 Tools

| Tool | Purpose |
|------|---------|
| **Google Chrome (Desktop)** | Primary browser for executing and validating tests |
| **GitHub Issues** | Defect logging, tracking, and collaboration |
| **Markdown (.md files)** | Writing test plans, reports, and documenting results |
| **Screenshots & Snipping Tool** | Capturing evidence of test execution and defects |
| **LocalStorage Inspector (Chrome DevTools)** | Verifying leaderboard data persistence |
| **VS Code / Text Editor** | Reviewing HTML source code |
| **GitHub Project Board (optional)** | Organizing tasks, assigning roles, tracking progress |

### 📚 Resources

| Resource | Description |
|----------|-------------|
| **System Under Test (SUT)** | Word Puzzle Game Plus deployed in Chrome |
| **Team Members** | Test Manager, Risk Analyst, Test Executor |
| **Test Cases Document** | List of test scenarios and expected outcomes |
| **Final Report Template** | Provided by PLP for Week 5 QA submission |
| **Course Materials** | Week 5 module on Test Management for guidance |
---
### Schedule

| Phase | Planned Duration | Actual Duration | Status |
|-------|------------------|-----------------|--------|
| Test Planning | one day | 4 hours | completed |
| Risk Analysis | one day | 5 hours | completed |
| Test Design | one day | 6 hours | completed |
| Test Execution | one day | 6 hours | completed |
| Defect Reporting | 4 hours | 3 hours | completed |
| Final Reporting | 4 hours | 4 hours | completed |

## Risk Analysis

### Identified Risks

| ID | Feature | Risk Description | Likelihood | Impact | Priority | Mitigation Strategy |
|----|---------|------------------|------------|--------|----------|---------------------|
| R1 | Reset Game | Reset button may not clear all game state properly | Medium | High | High | Test state clearing thoroughly, verify all variables reset |
| R2 | Leaderboard | localStorage may fail to persist scores across sessions | Low | High | Medium | Test persistence, verify browser compatibility |
| R3 | Bonus Round | Score multiplication logic may have calculation errors | Medium | Medium | Medium | Test arithmetic operations, verify timing triggers |
| R4 | UI/UX | Buttons may become unresponsive or layout may break | Low | Medium | Low | Test responsiveness, verify click handlers |
| R5 | Data Integrity | Score manipulation or negative scores possible | Medium | High | High | Test boundary conditions, validate input sanitization |
| R6 | Performance | Game may freeze or become slow with repeated actions | Low | Low | Low | Test stress scenarios, monitor performance |

### Risk Coverage Analysis

- **Tested Risks:** 5 out of 6 risks (83% coverage)
- **Untested Risks:** 1 risk (Performance - R6)
- **High Priority Risks Tested:** 3 out of 3 (100%)

### Risk-Coverage Pie Chart

```
Risk Coverage Distribution:
┌─────────────────────────────────────┐
│  Tested Risks: 83% (5/6)            │
│  ████████████████████████████████   │
│                                     │
│  Untested Risks: 17% (1/6)          │
│  ██████                             │
└─────────────────────────────────────┘
```

## Test Design & Execution

### Risk-Based Test Cases Designed

| ID | Feature | Objective | Steps | Expected Result | Risk Priority | Risk Link |
|----|---------|-----------|-------|----------------|--------------|-----------|
| TC-01 | Reset Game | Verify reset button clears all game state | 1. Play game, score points<br>2. Click Reset button<br>3. Verify score = 0, solved = 0 | Score = 0, Solved = 0, new puzzle loaded | High | R1 |
| TC-02 | Reset Game | Verify reset preserves leaderboard data | 1. Achieve high score<br>2. Click Reset<br>3. Check leaderboard | Leaderboard remains unchanged | High | R1 |
| TC-03 | Leaderboard | Verify localStorage persistence across sessions | 1. Achieve score<br>2. Refresh browser<br>3. Check leaderboard | Scores persist after refresh | Medium | R2 |
| TC-04 | Leaderboard | Verify top-3 sorting logic | 1. Achieve scores 5, 12, 8<br>2. Check leaderboard order | Scores sorted descending | Medium | R2 |
| TC-05 | Bonus Round | Verify score doubling at 3rd puzzle | 1. Solve 3 puzzles<br>2. Verify score multiplication | Score doubles when 3rd puzzle solved | Medium | R3 |
| TC-06 | Bonus Round | Verify bonus timing accuracy | 1. Solve puzzles in sequence<br>2. Track bonus triggers | Bonus triggers exactly every 3 puzzles | Medium | R3 |
| TC-07 | Data Integrity | Test negative score handling | 1. Use hints to reduce score<br>2. Verify minimum score | Score cannot go below 0 | High | R5 |
| TC-08 | Data Integrity | Test hint penalty calculation | 1. Use hint<br>2. Verify point deduction | Hint costs 2 points immediately | High | R5 |

### Additional Test Cases

| ID | Feature | Objective | Steps | Expected Result | Type |
|----|---------|-----------|-------|----------------|------|
| TC-09 | UI/UX | Test button responsiveness | 1. Click all buttons<br>2. Verify responses | All buttons respond to clicks | Usability |
| TC-10 | Negative Test | Test empty input submission | 1. Leave input empty<br>2. Click Submit | Error message displayed | Negative |
| TC-11 | Negative Test | Test invalid word submission | 1. Enter wrong word<br>2. Click Submit | Error message displayed | Negative |
| TC-12 | UI/UX | Test keyboard navigation | 1. Press Enter key<br>2. Verify submission | Enter key submits guess | Usability |

### Test Design Summary
- **Total Test Cases Designed:** 12
- **Risk-Based Tests:** 8 (67% - exceeds minimum requirement of 5)
- **Negative Tests:** 2 (meets requirement)
- **Usability Tests:** 2 (exceeds minimum requirement of 1)
- **High Priority Risk Coverage:** 100% (all high-priority risks covered)

## Defects

| ID | Issue Title | Severity | Risk ID | Status | GitHub Link |
|----|-------------|----------|---------|--------|-------------|
| | | | | | |

## Metrics

- Test Case Pass Percent: 
- Defect Density: 
- Risk Coverage Percent: 
- Regression Success Rate: 

### Defect Summary

- Total Defects Logged: 
- Critical High: 
- Fix Rate: 

## Test Control & Project Management

### Phases

| Phase | Deliverable | Actual Output | Variance | Owner |
|-------|-------------|---------------|----------|-------|
| | | | | |

**Progress Tracking Method:**  
**Change Control Notes:**

## Lessons Learned

- Most Defect Prone Feature: 
- Risk Analysis Impact: 
- Team Communication Effectiveness: 
- Improvements for Next Cycle: 

## Attachments

- 

## Sign Off

| Name | Role | Initials | Date |
|------|------|-----------|------|
| Ojutiwon Anuoluwapo Mautin | Test Manager | Anu |  |
| Steven Gulu | Risk Analyst | SG | 2025-01-27 |
| Too Kelvin | Test Executor | TK |  |

## Overall Summary

**Statement:** 

**Test Status:** ☐ Completed / ☐ In Progress / ☐ Deferred
