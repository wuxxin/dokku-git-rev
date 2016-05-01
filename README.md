# dokku-git-rev

Lets you fetch the git revision hash and git branch name used to build the app,
and makes it available in the deployment and run phases.


## requirements

- dokku 0.4.0+
- docker 1.8.x

## installation

```shell
# on 0.4.x
dokku plugin:install https://github.com/cjblomqvist/dokku-git-rev.git dokku-git-rev
```

## hooks

This plugin provides hooks:

* `pre-receive-app`: captures the current `GIT_REV` and `GIT_BRANCH` to files
* `docker-args-deploy`, `docker-args-run`: injects `GIT_REV` and `GIT_BRANCH` into the environment

## usage

On dokku deploy and run phases, `GIT_REV` and `GIT_BRANCH` variables will be added to the shell environment.

## thanks

based on:
- cbpowell (https://github.com/cbpowell/dokku-git-rev)
- cjblomqvist (https://github.com/cjblomqvist/dokku-git-rev)
- nornagon who made the initial plugin (albeit it was not really working) - this plugin is built upon his work (https://github.com/nornagon/dokku-git-rev)
- mlebkowski/puck who helped me out and made the initial verison of the receive-app based version. I based this version upon that idea and made it bug free and more stable (https://github.com/mlebkowski/dokku-git-rev/tree/fix/first-push)
