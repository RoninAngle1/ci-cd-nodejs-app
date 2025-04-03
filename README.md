
# CI/CD Node.js App

This repository contains a simple Node.js application integrated with a Continuous Integration and Continuous Deployment (CI/CD) pipeline using GitHub Actions. The pipeline builds the application, runs tests, and deploys it to a container registry.

## Features
- **Node.js Application**: A basic Node.js app with API endpoints.
- **Dockerized Application**: The app is packaged into a Docker container to ensure consistency across environments.
- **CI/CD Pipeline**: Automated pipeline using GitHub Actions to build, test, and deploy the app.
- **Docker Hub Integration**: The app image is pushed to Docker Hub.

## Prerequisites

- **Docker**: Docker must be installed to build and run the app in a container.
- **Node.js**: The app uses Node.js, so Node.js should be installed for local development (although Docker handles this for deployment).
- **GitHub Account**: For CI/CD actions and deployments via GitHub Actions.

## Getting Started

To run this project locally or use it for your own CI/CD setup, follow the steps below.

### Clone the Repository
```bash
git clone https://github.com/RoninAngle1/ci-cd-nodejs-app.git
cd ci-cd-nodejs-app
```

### Install Dependencies
If you're running the app locally (without Docker), you can install the dependencies with:
```bash
npm install
```

### Running the App Locally

You can start the application locally by running:
```bash
npm start
```
This will run the app on `http://localhost:3000`.

### Building the Docker Image

If you want to build the application inside a Docker container, you can use the following Docker commands:

1. **Build the Docker image**:
   ```bash
   docker build -t 09014579884/ci-cd-nodejs-app:v1 .
   ```

2. **Run the Docker container**:
   ```bash
   docker run -p 3000:3000 09014579884/ci-cd-nodejs-app:v1
   ```
   This will expose the app on port `3000` of your machine.

### Running the CI/CD Pipeline with GitHub Actions

This repository comes with a pre-configured GitHub Actions workflow to automate the process of building, testing, and deploying the Node.js application.

#### Workflow Details:
- **Push to `main` branch**: Triggers the CI/CD pipeline whenever there is a push to the `main` branch.
- **Docker Build and Test**: The workflow builds the Docker image, runs tests, and tags the image with the `v<run_id>` and `latest`.
- **Docker Hub Deployment**: After a successful build and test, the image is pushed to Docker Hub.

### GitHub Actions Workflow
The CI/CD pipeline is configured in the `.github/workflows/ci-cd.yml` file.

## Docker Hub

The built Docker image will be pushed to Docker Hub under the name:

```
09014579884/ci-cd-nodejs-app
```

- **Tags**: The images are tagged with `v<run_id>` and `latest` to differentiate the images.

## Testing the Application

This Node.js application contains basic test scripts using **Mocha** and **Chai**. These tests are executed as part of the CI pipeline.

To run the tests locally (without Docker), simply run:
```bash
npm test
```

## Contribution

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-name`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
