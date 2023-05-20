# Gamma CI Made Easy

This GitHub Action allows you to merge your pull requests directly into the testing branch with ease. It simplifies the process of merging pull requests by automating the necessary Git commands.

## Usage

To use this action in your workflow, you can include the following snippet in your workflow file (e.g., `.github/workflows/main.yml`):

```YML
name: Merge PR to Testing Branch

on:
  pull_request:
    types:
      - opened
      - reopened
      - synchronize

jobs:
  merge-pr:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Merge PR to Testing Branch
      uses: solenova-tech/gamma@v1.0.0 # replace version with latest from https://github.com/marketplace/actions/gamma-ci-made-easy
      with:
        target-branch: 'staging' # replace this name with your testing branch
        token: ${{ secrets.GITHUB_TOKEN }} # Read below on how to get this

```

This action requires a personal access token (PAT) with appropriate permissions to perform the merge operation. Make sure you provide the token input with a valid GitHub Personal Access Token.

## Inputs

target-branch (optional): The branch in which you want to merge the pull request. Defaults to 'alpha'.
token (required): GitHub Personal Access Token. Make sure to provide a valid token.

## Note

This action is triggered only when a pull request is opened, reopened, or synchronized, in other cases the action will not produce expected result

## License

This project is licensed under the [MIT License]('https://www.umairjibran.com')
