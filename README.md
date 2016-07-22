
cf-sh-prompt
============

Show in the shell prompt where the Cloud Foundry CLI is currently pointing.

```
graham:~ [https://api.run.pivotal.io]$
```

Currently tested on bash, with an aspiration to work in zsh.

Installing and using
====================

Copy the file `cf-sh-prompt` from this repository to somewhere on your machine.

Run the following commands at your shell prompt in order to try the prompt out

```
. /path/to/cf-sh-prompt
PS1="\u:\W \[\$(__cf_org)/\$(__cf_space)\]\$ "
```

You would expect the output to contain your username, working directory CF org
& space. Like this:

`graham:cf-sh-prompt [paas-demo/sandbox]$ `

If you change the org or space that the CF command line points to, the prompt
will change too:

```
cf target -o backend -s production
...
graham:cf-sh-prompt [backend/production]$
```

To ensure that every shell opened from now onwards uses that prompt, add those
lines to your shell initialisation file, for example `.bashrc`.

The shell functions available are:

- `__cf_api_endpoint`: the URL of the CF API
- `__cf_org`: the CF org currently targeted
- `__cf_space`: the CF space currently targeted
- `__cf_user`: the CF user currently logged in

