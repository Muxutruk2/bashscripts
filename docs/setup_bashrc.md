# setup_bashrc.sh

The `setup_bashrc.sh` script adds several useful functions to your `.bashrc` file, enhancing your command-line experience with custom commands like `cs`, `ccat`, and more. This script has been tested on Ubuntu and Mac OS X.

## How to Use

To set up the `.bashrc` script, source it in your terminal:

```bash
source $(which setup_bashrc.sh)
```

**Note:** This script must be sourced, not executed directly, to ensure the `.bashrc` updates take effect in your current shell session.

## Functionality

The script adds the following functions and configurations to your `.bashrc`:

- **Hide user name and host in terminal**
    ```bash
    export PS1="\w$ "
    ```

- **Run `ls` every time a terminal opens**
    ```bash
    ls
    ```

- **`cs` (cd + ls)**
    Changes directory and lists contents:
    ```bash
    function cs () {
        cd $1
        ls -a
    }
    ```

- **`tp` (transfer path)**
    Saves the current path to a hidden file:
    ```bash
    function tp () {
        pwd > ~/.sp
    }
    ```

- **`gtp` (goto transfer path)**
    Changes directory to the previously saved path:
    ```bash
    function gtp () {
        cs `cat ~/.sp`
    }
    ```

- **`ccat` (cat with color)**
    Displays files with syntax highlighting:
    ```bash
    function ccat () {
        source-highlight -fesc -i $1
    }
    ```

- **`evince` and `gedit`**
    Opens `evince` and `gedit` in the background:
    ```bash
    function evince () {
        /usr/bin/evince $* 2> /dev/null & disown
    }
    function gedit (){
        /usr/bin/gedit $* 2> /dev/null & disown
    }
    ```

- **`up`**
    Moves up N directories:
    ```bash
    function up () {
      LIMIT=$1
      P=$PWD
      for ((i=1; i <= LIMIT; i++))
      do
          P=$P/..
      done
      cs $P
      export MPWD=$P
    }
    ```

## Special Instructions for Cygwin (Windows)

If using Cygwin on Windows, add the following line at the beginning of the script to fix newline issues:
```bash
(set -o igncr) 2>/dev/null && set -o igncr;
```

## Contributors

- Miguel Gonzalez-Fierro
- Gustav Henning
- Frederic Dauod
