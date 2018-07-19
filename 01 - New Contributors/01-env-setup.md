
If you haven't already done so then a good place to start would be to sign up for a Fuse Online account and try out the product from the customers's perspective.
https://www.redhat.com/en/technologies/jboss-middleware/fuse-online

You can also find a Getting Started Guide for Fuse on OpenShift here:
https://developers.redhat.com/products/fuse/hello-world/#fndtn-rhel


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


## Next Steps

You're now ready to contribute! We highly encourage you go through the docs in `02 - Syndesis UI` to become familiar with our best practices.
