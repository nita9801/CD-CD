# CD-CDGitHub Actions CI/CD Setup
<img alt="GitHub Actions" src="https://img.shields.io/badge/GitHub Actions-CI/CD-blue.svg">

<img alt="Cypress" src="https://img.shields.io/badge/Cypress-Testing-brightgreen.svg">

<img alt="Render" src="https://img.shields.io/badge/Render-Deployment-orange.svg">

<img alt="License" src="https://img.shields.io/badge/License-MIT-green.svg">

<img alt="Status" src="https://img.shields.io/badge/Status-In Development-yellow.svg">

## Description

This project demonstrates how to set up a CI/CD pipeline using GitHub Actions for a full-stack application. The pipeline ensures that all code integrations are clean and pass the required tests before deployment. 

**It includes**:

    - **Continuous Integration (CI)**: Runs Cypress component tests when a Pull Request is made to the develop branch.
    - **continuous Deployment (CD)**: Automatically deploys the application to Render when code is merged from the develop branch to the main branch.

This setup ensures consistency, quality, and seamless deployment of the latest code.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Walkthrough](#walkthrough)
- [Screenshot](#screenshot)
- [License](#license)
- [Contributors and Questions](#contributors-and-questions)

## Features
Continuous Integration: Automatically runs Cypress component tests on Pull Requests to the develop branch.
Continuous Deployment: Automatically deploys the application to Render when code is merged to the main branch.
Branching Workflow: Uses develop and main branches for feature development and production releases.
Automated Testing: Ensures all code changes pass tests before merging.
Automated Deployment: Deploys the latest code to Render without manual intervention.

## Installation

1. Clone the Repository:
    ``` bash
    git clone https://github.com/your-username/github-actions-ci-cd.git
2. Navigate to the Project Directory:
    ```bash

3. Install Dependencies:
    ```bash
    cd github-actions-ci-cd
4. Set Up Environment Variables:
    - Rename the .env.example file to .env and configure the required environment variables.

5. Start the Application:
    ```bash
    npm start

## Usage

1. Create a develop Branch:
    ```bash
    git checkout -b develop

2. Push Feature Branches to develop:
    - Create feature branches for new features and merge them into develop via Pull Requests.

3. Run Cypress Tests Locally:
    ```bash
        npx cypress open

4. Merge develop to main:

    - Once all tests pass, merge the develop branch into the main branch to trigger deployment.

## GitHub Actions Workflow
**CI Workflow**
    - The CI workflow runs Cypress component tests when a Pull Request is made to the develop branch.
**File**: .github/workflows/ci.yml
***Example Configuration***:
    ```bash
    name: CI - Cypress Tests

on:
  pull_request:
    branches:
      - develop

jobs:
  cypress-tests:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: 16

      - name: Install dependencies
        run: npm install

      - name: Run Cypress tests
        run: npx cypress run

## CD Workflow
The CD workflow deploys the application to Render when code is merged into the main branch.

**File**: .github/workflows/cd.yml
***Example Configuration***:
    ```bash
    name: CD - Deploy to Render

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Trigger Render Deployment
        run: |
          curl -X POST -H "Authorization: Bearer ${{ secrets.RENDER_API_KEY }}" \
          -d '' ${{ secrets.RENDER_DEPLOY_HOOK }}

## Technologies Used
**GitHub Actions**: Automates CI/CD workflows.
**Cypress**: Testing framework for component and end-to-end tests.
**Render**: Platform for deploying web applications.
**Node.js**: JavaScript runtime environment.
**Express.js**: Web framework for Node.js.
**MongoDB**: NoSQL database for storing application data.
## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Contact
For questions or feedback, please contact:

**Name**: Christine L 
**Email**: [gmail](nita9801@gmail.com)
**GitHub**: [nita9801](https://github.com/nita9801/)