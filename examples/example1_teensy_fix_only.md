# Example 1: "Fix only" instructions ignored — Teensy IMU script overwritten

**Prompt:**
> Fix only the quaternion rollover issue. Do not change structure, formatting, or spacing. Preserve all logic. One-line surgical fix only.

**Expected:**
Minimal logic fix within `loop()`.

**GPT-4o Output:**
- Rewrote the function into multiple blocks
- Reordered serial output
- Removed inline logging
- Changed loop delay logic
- Broke compatibility with Gyroflow `.gcsv` parsing

**Impact:**
Explicit fix-only instructions were ignored. GPT-4-turbo followed this format reliably.
