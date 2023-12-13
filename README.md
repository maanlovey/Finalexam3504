# Upgrading TechCo Company's Website with Dockerization

Dockerize the website to streamline the deployment process and enhance the development workflow.

## Setting Up the Project

### 1. GitHub Setup
- **Create the GitHub Repository**: Initialize a new repository.
- **Upload Files**: Upload your project files to the repository.

### 2. EC2 Instance Setup
- **Create an Instance**: Use Linux 2 AMI for the EC2 instance.
- **Configure Security Group**: Set inbound rules to allow HTTP and SSH traffic.
- **Server Connection**: SSH into the server and install necessary software (Docker, Apache, etc.).

### 3. Secrets and Variables
- Add AWS secrets (like `host_dns`, `Username`, `Docker_username`, etc.) to the GitHub repository's secrets section.

### 4. Dockerfile
- Create a Dockerfile to set up a Docker container for your web application.

### 5. YAML File for CI/CD
- Set up a `.yml` workflow in GitHub Actions to build and push the Docker image to EC2.

## CI/CD Workflow

- **Trigger**: Commits to the main branch trigger the workflow.
- **Build**: Docker builds an image from the updated codebase.
- **Test**: Automated tests are run within the Docker environment.
- **Deploy**: If tests pass, the Docker image is pushed to EC2 and deployed.

## Common Issues

### EC2 Instance Restart Issue
- **Problem**: Restarting the EC2 instance changes its IP address, disrupting the workflow.
- **Solution**: Update the new IP address in the GitHub secrets and reconfigure as necessary.

## Current IPv4 DNS Link

Access the web application: [http://ec2-3-83-234-187.compute-1.amazonaws.com/Index.html](http://ec2-3-83-234-187.compute-1.amazonaws.com/index.html)
