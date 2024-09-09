# GitLab CI/CD Workflow for Runtime Action Iac

This GitLab CI/CD workflow runs the Runtime Action Iac with the specified parameters.

## Inputs

The following environment variables must be configured in your GitLab CI/CD settings:

- `FEATURES_LEVEL_LOG`: Log Level (required)
- `CLIENT_ID`: CLIENT ID (required)
- `CLIENT_KEY`: CLIENT KEY (required)
- `CLIENT_REALM`: CLIENT REALM (required)
- `REPOSITORY_NAME`: Git Repository Name (optional, default: `${CI_PROJECT_NAME}`)
- `AWS_ACCESS_KEY_ID`: AWS ACCESS KEY ID from console (optional)
- `AWS_SECRET_ACCESS_KEY`: AWS SECRET ACCESS KEY from console (optional)
- `AWS_SESSION_TOKEN`: AWS SESSION TOKEN from console (optional)
- `AWS_REGION`: AWS REGION (required)
- `AWS_ROLE_ARN`: AWS ROLE ARN (optional)
- `RUN_TASK_ID`: Runtime Run Task Id (required)
- `PATH_TO_MOUNT`: Path to mount inside the docker (optional, default: `${CI_PROJECT_DIR}`)
- `BASE_PATH_OUTPUT`: Base Path Output (optional)
- `CONTAINER_URL`: IAC Container URL (optional, default: `stackspot/runtime-job-iac:latest`)
- `CHECKOUT_BRANCH`: Whether or not checkout is enabled (optional, default: `false`)

## Usage

To use this workflow, add the above environment variables to your GitLab CI/CD settings and include the `.gitlab-ci.yml` file in your repository.

```yaml
include:
  - local: '.gitlab-ci.yml'