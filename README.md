# Backstage Dev Container

This repository contains a development container configured for Backstage development.

## Using with an existing Backstage Implementation

1. Clone this repository to get the `.devcontainer` folder:

   ```bash
   git clone <this-repo-url> backstage-devcontainer
   ```

2. Copy the `.devcontainer` folder to your existing Backstage repository:

   ```bash
   cp -r backstage-devcontainer/.devcontainer /path/to/your/backstage/repo/
   ```

3. Open your Backstage repository in VS Code

4. Click on the green button in the bottom-left corner or press `Ctrl+Shift+P` and select "Reopen in Container"

5. VS Code will build the container and reopen your project inside it

6. Once inside the container, install your Backstage dependencies:

   ```bash
   yarn install
   ```

7. Start your Backstage app:

   ```bash
   yarn dev
   ```

8. Your Backstage app will be available at:
   - Frontend: http://localhost:3000
   - Backend: http://localhost:7007

## Port Forwarding

The dev container forwards the following ports:

- 3000: Backstage frontend
- 7007: Backstage backend
- 8080: code-server web UI

## Container Features

- Node.js 18.x and Yarn pre-installed
- Python 3 with pip
- VS Code extensions for Backstage development
- Full root access for installing additional packages
