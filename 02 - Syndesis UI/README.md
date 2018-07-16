# Contributing to the UI

## Minishift Instance

**NOTE: The Minishift section is a work in progress (WIP) and may not be up-to-date.**

You'll first need to get your Minishift instance set up to contribute to Syndesis and have it running locally with all the proper resources.

### Initial setup

```
$ brew install docker-machine-driver-xhyve
$ brew cask install minishift
$ git pull https://github.com/syndesisio/syndesis.git # or own fork
$ syndesis/tools/bin/syndesis --full-reset # installs minishift, a VM containing OpenShift
$ minishift config set memory 4096
$ minishift config set cpus 4
```

### Get the Latest Changes

```
$ git checkout master
$ git pull upstream master
$ git checkout <branch>
$ git rebase master
```

### First Time Setup

`$ syndesis minishift --full-reset`

### Day-to-Day
If you DON'T want to delete your Minishift instance (you want to use an existing one).

**Start of the Day**
`$ minishift start`

Required regardless.
Log in, point OpenShift to use Minishift resources.
Please note that you need to have the `oc` binary available in your `PATH`. To do that, see here: https://docs.openshift.org/latest/cli_reference/get_started_cli.html

For macOS, I recommend using Homebrew: `brew install openshift-cli`

```
$ oc login -u developer
$ eval $(minishift oc-env)
$ eval $(minishift docker-env)
```

The eval's set a number of environment variables, like change the `$PATH` and `$DOCKER_HOST`, so each time you do a syndesis build it's good to make sure those are invoked.

**End of the Day**

`$ minishift stop`

If you don't do this and put your laptop to sleep, you'll get weird behavior from the same running Minishift instance the next day.

Open in Browser from Console

```
$ yarn start:minishift
$ open https://$(oc get routes syndesis --template "{{.spec.host}}")
```


