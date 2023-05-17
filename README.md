# Gamma: Streamline Continuous Integration with Automated Branch Merging ✨🚀

This repository aims to streamline the Continuous Integration (CI) flow, ensuring efficient code deployment and testing. By implementing a robust workflow, you can automate the process of merging feature branches into designated environments, such as 'staging,' 'alpha,' 'beta,' or 'pre-prod.'

## Quick Start 🏁🚀

To quickly implement automated branch merging in your project, follow these steps:

1. Copy the `.github/workflows/mergePr.yml` file from this repository to the same directory in your project.
2. Rename the file from `mergePr.yml` to your preferred name (e.g., `merge_alpha.yml`).
3. Modify the content of the workflow file to suit your specific requirements.

## How It Works 🛠️⚙️

This workflow automates the process of merging code changes into the designated branch, such as 'alpha.' Here's what happens under the hood:

- When a pull request (PR) is created on either the `main` or `master` branch, or new code changes are pushed to an already opened PR, the workflow will automatically merge all the code into the `alpha` branch.
- It is important to ensure that there are no conflicting changes in the code being merged.

> **NOTE:** If you want to use a branch with a different name instead of `alpha`, you can modify the `.github/workflows/mergePr.yml` file. Just change the word `alpha` on lines [1, 16] to your preferred branch name.

## Benefits of Automation ✅🔍

By automating the merging of feature branches, you can achieve several benefits:

- **Efficiency:** Eliminate the manual effort required to merge each feature branch, saving valuable time for developers and streamlining the CI process. ⏰💪
- **Consistency:** Ensure that the designated environment (e.g., 'alpha') consistently reflects the latest code changes, minimizing discrepancies between branches. 🔄✨
- **Reliability:** Reduce the risk of human error during manual merges, enhancing the overall reliability of the CI workflow. 🚫❌🙅‍♂️
- **Scalability:** As your project grows and more feature branches are created, automation allows for seamless integration and testing in the designated environment. 📈🚀

By adopting this automated branch merging approach, you can enhance your CI process and facilitate the seamless integration of new features. Don't let manual merges slow you down—automate your workflow today! 💪🚀
