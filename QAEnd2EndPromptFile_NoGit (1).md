# End-to-End QA Workflow with Natural Language

## Workflow Overview

This prompt guides you through a complete 7-step QA workflow using MCP servers and AI agents to go from a business requirement document to committed automated test scripts.

---

# 🎯 STEP 1: Read Business Requirement

## Prompt

I need to start a new testing workflow.

Please read the business requirement from:

`Merchant.md`

Summarize:
- Functional requirements
- Acceptance criteria
- Business rules
- Application URL
- Login credentials
- Test data
- Navigation flow
- Features to test

### Expected Output

- Summary of Merchant.md
- Acceptance Criteria
- Application URL and Credentials
- Features to Test

---

# 📄 STEP 2: Create Test Plan

Use the **playwright-test-planner** agent to:

1. Read Merchant.md
2. Explore the application using the supplied URL and credentials
3. Create a comprehensive test plan covering:
   - Happy paths
   - Negative scenarios
   - Empty fields
   - Invalid data
   - Edge cases
   - Boundary conditions
   - Navigation flow
   - UI validation

Save as:

`specs/merchant-test-plan.md`

Each scenario should contain:
- Test Case Title
- Steps
- Expected Results
- Test Data

### Expected Output

- Complete markdown test plan
- Structured scenarios
- Exploration screenshots (if needed)

---

# 🧪 STEP 3: Perform Exploratory Testing

Read:

`specs/merchant-test-plan.md`

Using Playwright MCP browser:

1. Execute every scenario manually
2. Follow each step exactly
3. Compare expected vs actual
4. Capture screenshots
5. Record findings
6. Record bugs and UI inconsistencies

### Expected Output

- Manual execution report
- Screenshots
- Findings
- Defects

---

# ⚙️ STEP 4: Generate Automation Scripts

Use **playwright-test-generator**.

Review:
- specs/merchant-test-plan.md
- Exploratory testing results

Generate Playwright automation using:
- Stable locators
- Proper assertions
- Wait strategies
- beforeEach / afterEach
- Comments where appropriate
- Multi-browser support

Save under:

`tests/merchant/`

Run the suite after generation.

### Expected Output

- Generated scripts
- Initial execution complete

---

# 🔧 STEP 5: Execute and Heal Automation Tests

Use **playwright-test-healer**.

1. Run all scripts
2. Detect failures
3. Heal:
   - Selectors
   - Waits
   - Assertions
4. Re-run
5. Repeat until stable

Document:
- Initial results
- Healing actions
- Final results

### Expected Output

- Stable suite
- Updated scripts
- Healing summary

---

# 📊 STEP 6: Create Test Report

Create:

`test-results/merchant-test-report.md`

Include:
- Executive Summary
- Manual Results
- Automation Results
- Healing Summary
- Defect Log
- Test Coverage
- Recommendations

### Expected Output

- Comprehensive report
- PASS / FAIL summary
- Coverage analysis
- Evidence

---

# 🎬 Complete Workflow Execution

```
I want to demonstrate a complete end-to-end QA workflow using natural language and MCP servers.

STEP 1 - Read Merchant.md and summarize the requirements.

STEP 2 - Create a comprehensive test plan and save it as specs/merchant-test-plan.md.

STEP 3 - Execute exploratory testing with Playwright MCP and capture screenshots.

STEP 4 - Generate Playwright automation scripts using exploratory insights.

STEP 5 - Execute, heal failures automatically, and rerun until stable.

STEP 6 - Generate a complete execution report in test-results/merchant-test-report.md.

Execute the workflow sequentially through Step 6 and provide status updates after every step.
```
