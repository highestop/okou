# Collapsed sidebar spacing evidence

For [vm0-ai/okou#35356](https://github.com/vm0-ai/okou/issues/35356).

- `before-expanded.png` and `before-collapsed.png` are the reporter-provided, privacy-redacted screenshots.
- `spacing-comparison.png` combines 2x crops of the local Chromium screenshots, with labels. It shows the measured gap changing from 0 px to 8 px.
- `reproduced-before.png` and `after-*.png` use synthetic test data, not the reporter's account.
- The local review boots the production Router using the repository's `setupPage` and sidebar test fixtures, exercises the actual hide/show controls, exports the resulting DOM, and paints it in Chromium using the production Tailwind stylesheet. These are local rendered review captures, not a deployed preview.
- The baseline is upstream `fc6e4f2d`; the fix only changes `sidebar-layout.tsx` and `workspace-inset.tsx`.
- `geometry.json` records browser measurements at desktop widths of 1280 and 768 px and mobile widths of 390 and 767 px. The expanded list and reopened list keep their existing left inset; mobile remains edge-to-edge; there is no horizontal overflow.

The screenshot files are separate from the code PR.
