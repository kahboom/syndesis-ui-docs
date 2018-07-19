# Contributing to the UI

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

