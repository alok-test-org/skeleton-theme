# GitHub import generated-CSS reproduction

This branch tests whether a Liquid stylesheet is rendered before
`config/settings_data.json` is applied and then left stale after a GitHub theme
import.

## Test procedure

1. Connect this branch as a new theme in Shopify Admin.
2. Open the first preview without using **Reset to latest commit** and without
   saving a file in Admin.
3. Record the banner and both displayed marker values.
4. Use **Reset to latest commit** or save a theme file.
5. Reload the preview and record whether the banner changes.

## Results

- **Green / CORRECT:** generated CSS contains the current values from
  `settings_data.json`.
- **Red / REPRODUCED:** live Liquid sees current `settings_data.json`, but the
  generated stylesheet contains schema defaults.
- **Amber / DIFFERENT ISSUE:** neither live Liquid nor generated CSS received
  `settings_data.json`.
