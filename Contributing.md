# Contributing to ASCII Engine

Thanks for your interest in improving ASCII Engine. Contributions are welcome — please read this fully before submitting anything.

---

## How contributions work

This project uses **pull requests**. You propose a change, the author reviews it, and it only goes live if approved and merged. Nothing is merged automatically.

**You do not need permission to submit a pull request**, but you do need to follow the rules below or it will be closed without review.

---

## Before you start

- Check the [open issues](../../issues) and [open pull requests](../../pulls) to make sure someone isn't already working on the same thing.
- For large changes, open an issue first to discuss the idea before writing code. This saves everyone time.
- Keep changes focused. One feature or fix per pull request.

---

## What is accepted

- Bug fixes
- Performance improvements
- New character sets
- Accessibility improvements
- Browser compatibility fixes
- Documentation corrections

## What will be rejected

- Removing the "Created by Sippinnrippin ZF" credit from the UI or any file
- Adding external dependencies, CDN scripts, or any network requests
- Changing the license or copyright notices
- Large redesigns without prior discussion in an issue
- Anything that breaks the single-file, no-server architecture

---

## How to submit a pull request

1. Fork the repository to your own GitHub account
2. Make your changes in a new branch — **do not commit directly to `main`**
3. Test your changes in Chrome, Firefox, and at least one other browser before submitting
4. Fill out the pull request template fully when you open the PR
5. Wait for review — the author will respond when available

---

## Code style

- Keep it in the single HTML file — no build tools, no bundlers, no separate JS/CSS files
- Use `'use strict'` and stay inside the existing IIFE
- Validate all user inputs, handle all errors safely
- Match the existing code style — spacing, naming, comment format
- No `console.log` left in submitted code

---

## License agreement

By submitting a pull request you confirm that:

- The code is your own original work
- You agree to the terms in the [LICENSE](LICENSE) file
- You grant the project author the right to use and modify your contribution

Contributions that are merged become part of the project and are covered by the project license.

---

## Questions

Open an issue if you're unsure about anything before starting work.
