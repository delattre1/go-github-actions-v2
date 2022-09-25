<a name="readme-top"></a>
<!-- TABLE OF CONTENTS -->
<details>
<summary>Table of Contents</summary>
  <ol>
    <li><a href="#references">References</a></li>
    <li><a href="#requirements">Requirements</a></li>
    <li><a href="#configs">Configs</a></li>
    <li><a href="#pipeline-description">Pipeline Description</a></li>
    <li><a href="#running-github-actions-locally">Running Locally</a></li>
    <li><a href="#verification">Verification</a></li>
  </ol>
</details>

<!-- REFERENCES -->
# References:
> [GitHub Actions for Go Developers!](https://www.youtube.com/watch?v=KVrL_UHJ7kQ)

> [Build CI/CD pipelines in Go](https://dev.to/gopher/build-ci-cd-pipelines-in-go-with-github-actions-and-dockers-1ko7)

> [Install github cli](https://github.com/cli/cli)

<!-- REQUIREMENTS -->
# Requirements:
## Install `act` to run your [GitHub Actions](https://developer.github.com/actions/) locally. 
[Act Link](https://github.com/nektos/act)

## Install Docker

`act` depends on `docker` to run workflows.

If you are using macOS, please be sure to follow the steps outlined in [Docker Docs for how to install Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/).

If you are using Windows, please follow steps for [installing Docker Desktop on Windows](https://docs.docker.com/docker-for-windows/install/).

If you are using Linux, you will need to [install Docker Engine](https://docs.docker.com/engine/install/).

## Install GitHub CLI 
- [Installation options](https://github.com/cli/cli/blob/trunk/README.md#installation)
- [Usage instructions](https://cli.github.com/manual/)

## Install [golangci-lint](https://github.com/golangci/golangci-lint)
- [Locally](https://golangci-lint.run/usage/install/#local-installation)
- [CI Environment](https://golangci-lint.run/usage/install/#ci-installation)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- CONFIGS -->
# Configs:

## Setting up github secrets via github-cli
``` bash
# Reference https://cli.github.com/manual/gh_secret
$ gh secret set DOCKER_USERNAME
$ gh secret set DOCKER_ACCESS_TOKEN
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- PIPELINE DESCRIPTION -->
# Pipeline Description

- Run project

  lorem
- Run tests

  lorem
- Apply linter 

  lorem
- Upload docker image to DockerHub

  The deploy job requires the test job to run first so that if the tests fail, the Docker image will not be built. If the test job does pass, the remaining steps will run. The first step extracts the version number from a git tag that has the following format vX.X.X.

  The next two steps setup the environment so that Docker images can be built. Finally, a step is run that signs into your Docker Hub account using the credentials stored in GitHub Secrets, then the Docker image is built and pushed to Docker Hub.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- RUNNING LOCALLY -->
# Running [GitHub Actions](https://developer.github.com/actions/) locally!

## To create a PR from current branch to master via cli:
``` bash
# Reference: https://cli.github.com/manual/gh_pr_create
# First create a pull request
$ gh pr create --title "title" --body "msg" --base master --head branch-to-merge
  > ? Body <Received>
  > ? What is next? Submit
  > https://github.com/delattre1/go-github-actions-v2/pull/1 
# Merge the PR
$ gh pr merge 1 --admin
  > ✓ Merged pull request #1
```

## GIF PLACEHOLDER RUNNING




<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- VERIFICATION -->
# Verification
## Use CLI to check if tests also passes on [GitHub Actions](https://developer.github.com/actions/)
> Only doing that via CLI because I don't have access to repo webpage
``` bash
$ gh workflow list
  > golang-pipeline  active  35710284
$ gh workflow view golang-pipeline
```

