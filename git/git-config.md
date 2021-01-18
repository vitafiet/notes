# Configure your Git user-name/email

You need to configure you Git user-name and email before you can run any Git operations (commit, push, etc).

**Note:** If you set your global configuration, repository-specific configuration is optional. However, repository-spcecific configuration is helpful when you need different config for different repositories.

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

### View/Edit your configuration in a text editor.

Run the below commands for Git to launch the default editor with current cofiguration.
You can make changes to it and save it for the config. to take effect from next use.

**Local config:** `git config --local --edit` \
**Global config:** `git config --global --edit`