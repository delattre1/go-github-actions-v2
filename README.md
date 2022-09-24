Install github cli
https://github.com/cli/cli

Setting up github secrets via github-cli
``` bash
$ # Reference https://cli.github.com/manual/gh_secret
$ gh secret set DOCKER_USERNAME
$ gh secret set DOCKER_ACCESS_TOKEN
```

Install act to run github actions locally
https://github.com/nektos/act


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
