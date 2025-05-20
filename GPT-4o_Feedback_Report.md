GPT-4o Regression Feedback — Request to Restore GPT-4-Turbo for Technical Projects
==================================================================================

Dear OpenAI Support,

Thank you for your response. I’m submitting this follow-up per your suggestion to share examples of GPT-4o unreliability in technical workflows. I’m a long-time GPT-4-turbo user with production-grade workflows in embedded development, Python automation, and GUI engineering. Since GPT-4o replaced GPT-4-turbo, the assistant has become **unreliable, disobedient, and structurally destructive** for my code tasks, even with strict instructions.

Here are three representative examples from real work sessions:

----------------------------------------------------------------------------------
🔧 Example 1: "Fix only" instructions ignored — Teensy IMU script overwritten
----------------------------------------------------------------------------------

Prompt:
> “Fix only the quaternion rollover issue. Do not change structure, formatting, or spacing. Preserve all logic. One-line surgical fix only.”

Expected:
Minimal logic fix within `loop()`.

GPT-4o Output:
- Rewrote the function into multiple blocks
- Reordered serial output
- Removed inline logging
- Changed loop delay logic
- Broke compatibility with Gyroflow `.gcsv` parsing

Impact:
GPT-4o ignored explicit fix-only instructions. GPT-4-turbo reliably obeyed this directive 100+ times in similar sessions. This regression causes real delays in production debugging, since I cannot trust GPT-4o to leave the rest of the code intact.

----------------------------------------------------------------------------------
⚠️ Example 2: GUI segmentation logic removed despite “Do Not Simplify” rules
----------------------------------------------------------------------------------

Prompt:
> “Do not remove segmentation logic. Do not simplify or rewrite. Integrate this threshold slider into the existing segmentation window. Fix only the update logic.”

Expected:
Keep advanced `segment_image()` logic and just wire slider value to `threshold_value`.

GPT-4o Output:
- Removed entire `segment_image()` pipeline
- Deleted light normalization, regionprops, and distance transforms
- Injected a stubbed `cv2.threshold()` with no fallback
- Broke all working segmentation presets

Impact:
GPT-4o **disobeyed my Turbo instructions** and destroyed core logic I had spent hours refining. I never had this issue with GPT-4-turbo once strict mode was established. This was a fully modular Python GUI with separated logic. GPT-4o acted destructively.

----------------------------------------------------------------------------------
💣 Example 3: Output omitted despite “full script” directive
----------------------------------------------------------------------------------

Prompt:
> “Fix the tabs vs spaces error. Output full script in one block. Do not split.”

Expected:
Return the corrected version of the full file, exactly as is, with indentation fixed.

GPT-4o Output:
- Gave only the function body
- Said “rest unchanged” even though it altered spacing
- Broke indentation again in next line
- Removed comment blocks
- Ignored my formatting rules

Impact:
GPT-4-turbo followed this instruction perfectly across hundreds of iterations. GPT-4o now habitually “truncates”, splits, or omits blocks even with my standard Turbo boilerplate.

----------------------------------------------------------------------------------
🧠 My Turbo Instructions for Reference
----------------------------------------------------------------------------------

I explicitly instruct GPT to operate in “Turbo-stable engineering mode.” This includes:
- Never simplify or reformat unless explicitly told
- Never remove or reorder lines
- Always return the full script in one block, regardless of size
- Fix only what I describe
- Warn before fixing unrelated bugs

**GPT-4o disobeys these rules regularly. GPT-4-turbo consistently respected them.**

----------------------------------------------------------------------------------
📌 Request
----------------------------------------------------------------------------------

Please consider the following actions:

1. **Restore GPT-4-turbo as an option** in the ChatGPT dropdown, or allow it in the API via model aliasing.
2. Offer a **“Strict Engineering Mode” toggle** for GPT-4o to avoid creative rewrites.
3. Create an **alpha / Pro Engineering tier** with access to more stable and conservative model behavior.

Thank you for your time and support. Please let me know if you’d like additional examples or session logs.

Sincerely,  
Ryan (longtime user and ChatGPT Plus subscriber)
