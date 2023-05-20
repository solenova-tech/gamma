# Gamma CI Made Easy

This GitHub Action allows you to merge your pull requests directly into the testing branch with ease. It simplifies the process of merging pull requests by automating the necessary Git commands.

## Usage

This action is triggered only when a pull request is opened, reopened, or synchronized, in other cases the action will not produce expected result. To use this action in your workflow, you can include the following snippet in your workflow file (e.g., `.github/workflows/main.yml`):

```YML
name: Merge PR to Testing Branch

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
    - name: Merge PR to Testing Branch
      uses: solenova-tech/gamma@v1.0.0 # replace version with latest from https://github.com/marketplace/actions/gamma-ci-made-easy
      with:
        target-branch: 'staging' # replace this name with your testing branch
        token: ${{ secrets.GITHUB_TOKEN }} # Read below on how to get this

```

This action requires a personal access token (PAT) with appropriate permissions to perform the merge operation. Make sure you provide the token input with a valid GitHub Personal Access Token. Create a PAT with the REPO permission using the following steps:
- Sign in to your GitHub account.
- Click on your profile icon in the top-right corner, and then click on "Settings" in the dropdown menu.
- In the left sidebar, click on "Developer settings".
- In the left sidebar, click on "Personal access tokens" to expand the collapsable sub-menu.
  - Click on the tokens (classic)
- Click on the "Generate new token" button.
  - In the sub-menu select "Generate new token (classic)"
- Provide a descriptive note for your token in the "Note" field. This will help you identify the token's purpose later.
- Select the desired scopes or permissions for the token. Scopes define the level of access the token will have. (for our use only "**repo**" permission is enough.
- If you want the token to have access only during a specific time period, you can set an expiration date for it.
- Once you have configured the note and scopes, click on the "Generate token" button.
- GitHub will generate a new Personal Access Token for you. Copy the token value.
  - After generating the token, it will be displayed only once. GitHub will not show it to you again. If you lose the token, you will need to generate a new one.
- Navigate to the main page of your repository on GitHub.
- Click on the "Settings" tab located near the top-right corner of the repository page.
- In the left sidebar, click on "Secrets and varialbes".
  - In the now new expanded sub menu, click on "Actions"
- Click on the "New repository secret" button.
- Enter a name for your secret in the "Name" field. This should be a descriptive name that helps identify the purpose of the secret. In the above example, we are using the 'GITHUB_TOKEN' as Name
- In the "Value" field, enter the actual value of the secret. This can be a password, an access token, or any other sensitive information that you want to securely store, in our case the PAT that you copied above.
- Click on the "Add secret" button to save the secret.
**Note that, PAT grants significant access to your GitHub account, so treat them like passwords and keep them secure.**

## Inputs

target-branch (optional): The branch in which you want to merge the pull request. Defaults to 'alpha'.
token (required): GitHub Personal Access Token. Make sure to provide a valid token.

## License

This project is licensed under the MIT License
