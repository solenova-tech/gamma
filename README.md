# Gamma CI Made Easy

This GitHub Action allows you to merge your pull requests directly into the testing branch with ease. It simplifies the process of merging pull requests by automating the necessary Git commands.

## Usage

This action is triggered only when a pull request is opened, reopened, or synchronized, in other cases the action will not produce expected result. To use this action in your workflow, you can include the following snippet in your workflow file (e.g., `.github/workflows/main.yml`):

```YML
name: Merge PR to Testing Branch

permissions:
  contents: write

on:
  pull_request:
    branches:
      - master
      - main
    types:
      - opened
      - reopened
      - synchronize

jobs:
  merge-pr:
    runs-on: ubuntu-latest

    steps:
    - name: Checks out code
      uses: actions/checkout@v3

    - name: Merge PR to Testing Branch
      uses: solenova-tech/gamma@v1.0.0 # replace version with latest from https://github.com/marketplace/actions/gamma-ci-made-easy
      with:
        target-branch: 'staging' # replace this name with your testing branch
```

## Inputs

`target-branch` (optional): The branch in which you want to merge the pull request. Defaults to 'alpha'.

## License

This project is licensed under the MIT License
