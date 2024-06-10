# git_configure

The `git_configure` script is designed to set up global configurations for Git, including aliases, credential helpers, user name, and email. It has been tested on both Ubuntu and Mac OS X.

## How to Use

To use this script, simply source it in your terminal:

```bash
source $(which git_configure)
```

## What the Script Does

1. **Prompts for Git User Information**
    - Asks for the Git username.
    - Asks for the Git email, with a default option provided (username@users.noreply.github.com).

2. **Configures Global Git Settings**
    - Sets the global Git user name and email.
    - Configures several useful Git aliases:
        - `ci` for `commit`
        - `st` for `status`
        - `br` for `branch`
        - `co` for `checkout`
        - `last` for `log -1 HEAD`
        - `sub` for `submodule update --remote --merge`
    - Sets the default Git editor to `vim`.
    - Sets the Git credential helper with a cache timeout of 10 hours.

3. **SSH Key Configuration**
    - Optionally generates a new SSH key for Git if one does not already exist.
    - Displays the public SSH key with instructions for adding it to GitHub.

4. **Mac OS X Specific Configuration**
    - Sets up Git autocompletion if running on a Mac OS X system.
    - Downloads and sources the Git autocompletion script.
    - Adds the autocompletion script source line to `~/.bash_profile`.

- Ensure you have the necessary permissions to edit files like `~/.bash_profile` or `/etc/profile` when making changes to PATH or autocompletion settings.
- This script is designed to be sourced, not executed directly, to ensure that environment changes (like sourcing the autocompletion script) take effect in your current shell session.

