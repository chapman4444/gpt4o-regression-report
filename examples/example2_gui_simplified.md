# Example 2: GUI segmentation logic removed despite “Do Not Simplify” rules

**Prompt:**
> Do not remove segmentation logic. Do not simplify or rewrite. Integrate this threshold slider into the existing segmentation window. Fix only the update logic.

**Expected:**
Keep advanced `segment_image()` logic and wire slider value to `threshold_value`.

**GPT-4o Output:**
- Removed entire `segment_image()` pipeline
- Deleted light normalization and regionprops
- Injected a stub `cv2.threshold()` call
- Broke segmentation presets

**Impact:**
GPT-4o disobeyed strict directives. GPT-4-turbo consistently preserved complex pipelines under the same constraints.
