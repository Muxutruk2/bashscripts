# Bashscripts

Welcome to the **bashscripts** repository! This project contains a collection of useful Bash scripts designed to automate and simplify various tasks.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
  - [Clone the Repository](#clone-the-repository)
  - [Add `bin` Folder to PATH](#add-bin-folder-to-path)
    - [Local Installation](#local-installation)
    - [Global Installation](#global-installation)
- [Scripts](#scripts)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This repository contains several Bash scripts located in the `bin` folder. Each script is accompanied by its own documentation found in the `docs` folder.

## Installation

### Clone the Repository

To get started, clone this repository to your local machine using Git:

```bash
git clone https://github.com/yourusername/bashscripts.git
cd bashscripts
```

### Add `bin` Folder to PATH

To use the scripts from anywhere in your terminal, you need to add the `bin` folder to your PATH. There are two ways to do this: locally (for a single user) or globally (for all users).

#### Local Installation

1. Open your `.bashrc` file in a text editor:

    ```bash
    nano ~/.bashrc
    ```

2. Add the following line to the end of the file:

    ```bash
    export PATH="$HOME/bashscripts/bin:$PATH"
    ```

    Replace `/bashscripts/bin` with the actual path to the cloned repository.

3. Save and close the file.

4. Apply the changes:

    ```bash
    source ~/.bashrc
    ```

#### Global Installation

1. Open the `/etc/profile` file in a text editor with superuser privileges:

    ```bash
    sudo nano /etc/profile
    ```

2. Add the following line to the end of the file:

    ```bash
    export PATH="/path/to/bashscripts/bin:$PATH"
    ```

    Replace `/path/to/bashscripts` with the actual path to the cloned repository.

3. Save and close the file.

4. Apply the changes:

    ```bash
    source /etc/profile
    ```

## Scripts

Here is a list of available scripts:

- [getgit](docs/getgit.md): lazygit-like tool to quickly navigate to a repo inside a pre-configured repo folder
- [git_configure](docs/git_configure.md): script to configure global options like git aliases, credential manager, username and email. Forked from [here](https://github.com/miguelgfierro/Scripts)
- [setup_bashrc](docs/setup_bashrc.md): script to set up various tools to bash, cs (cd + ls), ccat (cat with color) or reimplement evince to run in the background. Forked from [here](https://github.com/miguelgfierro/Scripts)
For detailed documentation on each script, click the link or refer to the `docs` folder.

## Documentation

Each script has its own documentation located in the `docs` folder. The documentation includes usage instructions, examples, and any additional information specific to the script.

## Contributing

Contributions are welcome! If you have a script you think would be useful, feel free to submit a pull request. Please ensure your script is well-documented and follows the existing structure of the repository.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
