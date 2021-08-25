# Configure your Git user-name/email

You need to configure you Git user-name and email before you can run any Git operations (commit, push, etc).

**Note:** If you set your global configuration, repository-specific configuration is optional. However, repository-spcecific configuration is helpful when you need different config for different repositories.

## Different configuration levels (system/global/local):
Git configuration variables can be stored at three different levels. Each level overrides values at the previous level.

1. **System level** - applied to every user on the system and all their repositories.
	- *view*: `git config --list --system`
	- *set*: `git config --system <conf>.<sc> <val>`
	- *edit ***system*** config file*: `git config --edit --system`.

	**Note:** `config --edit` launches the default editor with the specified-level of current cofiguration. You can make changes to it and save it for the config. to take effect from next use.

2. **Global level** - values specific personally to you (the user).
	- *view*: `git config --list --global`
	- *set*: `git config --global <conf>.<sc> <val>`
	- *edit ***global*** config file*: git config --edit --global
3. **Repository level** - specific to that single repository.
	- *view*: `git config --list --local`
	- *set*: `git config --local <conf>.<sc> <val>` [`--local` optional]
	- *edit ***repository*** config file*: `git config --edit --local` [`--local` optional]

### To set your global username/email configuration:
1. Open the command line.
2. Set your username: \
`git config --global user.name "FIRST_NAME LAST_NAME"`
3. Set your email address: \
`git config --global user.email "user@example.com"`

### To set repository-specific username/email configuration:
1. From the command line, change into the repository directory.
2. Set your username: \
`git config user.name "FIRST_NAME LAST_NAME"`
3. Set your email address: \
`git config user.email "user@example.com"`
4. *Optional:* verify your configuration by displaying your configuration file. \
`cat .git/config`

### Save git credentials (username/password):
1. Save your git credentials in a file (store mode): \
*Store mode:* saves the credentials to a plain-text file on disk, and they never expire. \
`git config credential.helper 'store --file ~/.my-credentials'`
2. Save credentials in cache (get purged every 15 mins): \
`git config credential.helper cache`

**Reference:** [link](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage)