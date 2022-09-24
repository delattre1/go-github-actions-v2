# Overview [![push](https://github.com/delattre1/go-github-actions-v2/workflows/push/badge.svg?branch=master&event=push)](https://github.com/delattre1/go-github-actions-v2/actions)

> References:
> GitHub Actions for Go Developers! - https://www.youtube.com/watch?v=KVrL_UHJ7kQ
> Build CI/CD pipelines in Go       - https://dev.to/gopher/build-ci-cd-pipelines-in-go-with-github-actions-and-dockers-1ko7

Run your [GitHub Actions](https://developer.github.com/actions/) locally! Why would you want to do this? Two reasons:

Install github cli
https://github.com/cli/cli

Setting up github secrets via github-cli
``` bash
$ # Reference https://cli.github.com/manual/gh_secret
$ gh secret set DOCKER_USERNAME
$ gh secret set DOCKER_ACCESS_TOKEN
```

# Installation

Install act to run github actions locally
https://github.com/nektos/act


## Necessary prerequisites for running `act`

`act` depends on `docker` to run workflows.

If you are using macOS, please be sure to follow the steps outlined in [Docker Docs for how to install Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/).

If you are using Windows, please follow steps for [installing Docker Desktop on Windows](https://docs.docker.com/docker-for-windows/install/).

If you are using Linux, you will need to [install Docker Engine](https://docs.docker.com/engine/install/).

`act` is currently not supported with `podman` or other container backends (it might work, but it's not guaranteed). Please see [#303](https://github.com/nektos/act/issues/303) for updates.


Display workflows:
``` bash
$ gh workflow list
> golang-pipeline  active  35710284
$ gh workflow view golang-pipeline
```

To create a PR from current branch to master via cli:

``` bash
$ # Reference: https://cli.github.com/manual/gh_pr_create
$ gh pr create --title "title" --body "msg" --base master --head devexp-development
> ? Body <Received>
> ? What's next? Submit
> https://github.com/delattre1/go-github-actions-v2/pull/1 
$ gh pr merge 1 --admin
> ✓ Merged pull request #1
```
