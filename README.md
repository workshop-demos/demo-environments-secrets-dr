# :rocket: Environments and secrets

Demo repository for using Environments and Secrets in workflows.

- :exclamation: **This is a template repository**
- :exclamation: **This demo contains GHEC/GHES-specific features**
  - The **Environments** feature is only available for GHEC, GHES (>=v3.1), and public repositories
- **If you have a GHEC organization available**, then please click ***Use this template*** to clone the repo into that organization
- **If you do not have a GHEC organization available**, please run the demo in this repository. Just make sure to complete the **Cleanup** steps afterwards :house_with_garden:

## Usage 

### Creating environments

1. In the repository, go to **Settings** --> **Environments**
1. Create an environment (e.g. `test`)
    - No additional settings
1. Create another environment (e.g. `prod`) 
    - Add a required reviewer (you can set yourself as the required reviewer)
    - The protection rules will be used later in the demo

### Creating secrets

1. In the organization, go to **Settings** --> **Secrets** (if you have org owner access to the organization. If not, skip this step.)
    - Add an org secret (e.g. `MY_ORG_SECRET`) with an arbitrary value
    - Show how org secrets can be scoped to specific repositories
1. In the repository, go to **Settings** --> **Secrets**
    - Add a repository secret (e.g. `MY_REPO_SECRET`) with an arbitrary value
1. In the repository, go to **Settings** --> **Environments**
    - For one of the environments, add an environment secret (e.g. `MY_ENV_SECRET`)

### Using Environments and Secrets in a workflow

:bulb: Ensure that the secrets and environments added above corresponds to what is defined in the workflow.

1. Use one of the existing workflows in `.github/workflows`
1. Walk through the syntax
1. Trigger the workflow by opening a new PR and ensure it succeeds
    - E.g. edit one of the test files
1. Show the environments GUI inside the PR (the **Deployments** section)
1. Merge the PR
1. If **Required reviewers** were added to the environment, the workflow should be halted until it is reviewed
1. Show how to review a deployment, and ensure the job proceeds
1. Show where to locate all Environments and deployments for the repository
    - The **Environments** section on the repository landing page
1. Show the redaction of secrets in the workflows log

### :house_with_garden: Cleanup

1. If the workflow was run in this repository, perform the following steps:
    - Delete all secrets created
    - Delete all environments created
    - Ensure any PRs are closed/merged
    - Delete any branches created

