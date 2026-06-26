# GitHub Actions

## What is it?
GitHub Actions is a CI/CD (Continuous Integration / Continuous Deployment) automation tool built directly into GitHub. It allows you to run scripts automatically whenever a specific event happens in your repository.

## Why do we use it?
Instead of manually running tests or deploying code every time you push, you can write a GitHub Action to do it for you. 
For example: "Every time someone opens a Pull Request, automatically run the testing suite. If the tests fail, block the Pull Request."

## Basic Syntax
Actions are configured using `.yml` (YAML) files placed in a special folder: `.github/workflows/`.

```yaml
name: Run Tests
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - run: npm install
      - run: npm test
```

## Example
The YAML code above tells GitHub:
1. Whenever someone pushes code (`on: [push]`)
2. Spin up a temporary Linux server (`ubuntu-latest`)
3. Download the code (`actions/checkout`)
4. Install dependencies (`npm install`)
5. Run the tests (`npm test`)

## Common Mistakes
- **YAML indentation errors:** YAML is extremely sensitive to spaces. One missing space can break the entire automation script.
- **Putting files in the wrong folder:** The YAML file MUST be exactly in `.github/workflows/` or GitHub will ignore it.

## Quick Summary
- Automates tasks like testing, linting, and deploying code.
- Triggered by Git events like `push` or `pull_request`.
- Configured using YAML files in `.github/workflows/`.
