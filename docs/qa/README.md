# Thepraggyverse Quality Loop

Use this directory for feature discovery, test generation, execution, remediation tracking, and regression evidence.

Source files:

- `features.csv` - canonical feature ledger.
- `test-cases.csv` - canonical test case ledger.
- `defects.csv` - canonical defect ledger.
- `quality-summary.md` - compact status and risk summary.

## Rules

- Base observed behavior on actual code and verified runtime behavior.
- Separate observed behavior from intended behavior when requirements are unclear.
- Record assumptions instead of pretending certainty.
- Do not fix defects until remediation is explicitly authorized or covered by a confirmed plan.
- Do not declare completion unless feature coverage, test execution, defect status, and regression criteria are all satisfied.
- Keep screenshots, logs, and bulky generated evidence out of git unless explicitly approved.

## Phases

1. Feature discovery.
2. Test generation.
3. Test execution.
4. Remediation after approval.
5. Regression testing.
6. Recursive quality loop until exit criteria are met.

## Exit Criteria

- No undiscovered user-facing features remain in the chosen scope.
- Every feature has test coverage.
- Every test in scope has been executed or explicitly blocked.
- Every defect is fixed, waived, or assigned to a later confirmed plan.
- No open critical or high-severity defects remain unless the owner explicitly waives them.
