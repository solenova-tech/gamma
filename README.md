# Gamma

This repo is aimed at streamlining the Continuous Integration flow, how?

Well, we have our stable branch that is deployed on prod, we can not test there, we need either 'staging'/'alpha'/æbeta'/'pre-prod'/'any name you prefer' environments, if we have a CD set up that deploys let's say 'alpha' branch to said environment, how do we make sure that the alpha has the latest code?

We can manually merge every feature branch in it, or we could automate it 💡

This workflow is how you can automate it.

## Breakdown

This is what happens under the hood.

When a PR is created on either the `main` or `master` branch or new code changes are pushed to the already opened PR, the workflow will merge all that code to the `alpha` branch, you just have to make sure that there are no conflicting changes.

NOTE: if you want a branch with a different name, just change `alpha` in the `.github/workflows/merge_pr.yml`
