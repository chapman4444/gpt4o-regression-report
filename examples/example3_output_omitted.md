# Example 3: Output omitted despite “full script” directive

**Prompt:**
> Fix the tabs vs spaces error. Output full script in one block. Do not split.

**Expected:**
Return full corrected file with consistent indentation.

**GPT-4o Output:**
- Only returned a partial function body
- Removed formatting, comments, and structure
- Broke layout despite explicit “fix only” and “full script” directives

**Impact:**
Breaks production script workflows where full file context must be preserved.
