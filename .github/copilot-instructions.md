# Repository instructions

## Architecture

- The app is a standalone static page in `index.html`; markup, CSS, quiz data, and JavaScript are kept together. It opens directly from disk and has no build or dependency step.
- The `questions` array is the source of truth for each quiz round. `renderQuestion()` builds the answer buttons from it; `chooseAnswer()` handles scoring, progress, and feedback; `showResults()` selects the final reaction; the restart handler resets the quiz state.

## Conventions

- Keep the page self-contained in `index.html`; do not add a server, framework, or external dependency for quiz behavior or styling.
- Add or edit quiz content in the `questions` array, keeping each answer’s `correct` value as a zero-based index into `answers` and retaining a short explanatory `fact`.
- Build answer choices as native buttons and update dynamic text through DOM `textContent`. Preserve the existing focus changes between answers, the next-question button, and the question/results headings.
- Use the existing CSS custom properties for colors and component styling. Any visual changes should retain both `prefers-color-scheme: dark` support and the reduced-motion override.

