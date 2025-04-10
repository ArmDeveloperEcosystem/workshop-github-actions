# Build multi architectural docker images via GitHub Actions

## Steps

### Retrieve Your Docker Username and Password

1. **Docker Username**:  
    Your Docker username is the name you use to log in to [Docker Hub](https://hub.docker.com/).

2. **Docker Personal Access Token**:  
    - Log in to [Docker Hub](https://hub.docker.com/).
    - Navigate to your account settings.
    - Go to Personal Access Token
    - Click on **Create Access Token**.
    - Provide a name for the token (e.g., `github-actions-token`).
    - Select the desired expiration date for the token.
    - Under **Access Permissions**, ensure you grant **read & write** access to repositories.
    - Click **Generate** and copy the token.  
    **Note**: Make sure to save the token securely as it will not be shown again.

### Add Docker Credentials to GitHub Actions

1. Go to your GitHub repository.
2. Click on the **Settings** tab.
3. In the left sidebar, select **Secrets and variables** > **Actions**.
4. Click the **New repository secret** button.
5. Add the following secrets:
    - `DOCKER_USER`: Your Docker username.
    - `DOCKER_PAT`: Your Docker Personal Access Token we generated above.

### Run the GitHub Actions Workflow

1. Go to the `Actions` page for your GitHub repository.
2. Trigger the `image-build.yml` workflow manually:
    - The workflow is located at [`.github/workflows/image-build.yml`](.github/workflows/image-build.yml)
    - From the `Actions` page, click **Run workflow**.
3. Monitor the workflow execution:
    - Check the progress and logs in the **Actions** tab.
    - Ensure the workflow completes successfully without errors.

Once the workflow finishes, your multi-architecture Docker images will be built and pushed to Docker Hub.
