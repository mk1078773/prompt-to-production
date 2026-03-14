# skills.md


skills:
  - name: classify_complaint
    description: Classifies a single municipal complaint into category, priority, reason, and flag per schema.
    input: Dict or string with complaint description (single row data).
    output: Dict with `category`, `priority`, `reason`, `flag`.
    error_handling: If ambiguous, set category to "Other", flag "NEEDS_REVIEW", reason explains ambiguity.

  - name: batch_classify
    description: Processes entire input CSV, classifies each row using classify_complaint, writes output CSV.
    input: Input CSV file path (e.g., "../data/city-test-files/test_pune.csv").
    output: Output CSV file path (e.g., "results_pune.csv") with added columns.
    error_handling: Logs errors per row, continues processing, flags invalid rows with NEEDS_REVIEW.
