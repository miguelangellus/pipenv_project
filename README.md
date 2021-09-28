# pipenv_project
### Getting Started With Pipenv

### Basic commands
Pipenv is a huge replacement as both to the pyenv as pip --the Package Installer for Python, together. \
Developed by the lib request's same team, the Pipenv owns powerful features and tools that allow you to make work much easier when integrating the resources. \
I'll bring for you some pipenv basic commands, and some analogies for a better comprehension to you. \
Despite different features, even so it's still necessary for the Pyenv to proceed to the isolation of the Python versions and their script environments, instead of using the standard Python of your operating system for supporting the coming Pipenv features, also even pypi.org to lead around your requirements, and requesting them of the index lists from the pypi.org site, as though the pip install command was simply an alias for the pipenv callings. For instance, instead of `pip install package`, now it's replaced to `pipenv install package`.
1. `pip --version`
2. `pip install --update pip`
3. pip install pyenv????? Definitely no, or even it could be, but it's not that a too single command as it seems. \
   Follow these steps below to catch this Python versions manager for running under your devices.
   * `sudo apt update`  --fetching, merging, pulling and installing the newest features to your Linux System from the apt repository.   
   * Additional third-party packages non-linux-apt-directly associated, actually not found in the apt repository. \
     `sudo apt install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm gettext libncurses5-dev tk-dev tcl-dev blt-dev libgdbm-dev git python-dev python3-dev aria2` \
      Don't feel scared of that, `sudo` asks you for your superuser password for being typed; `apt` is the Linux repository; `install` is the action; `-y` is just the parameter that defines **yes** for all installing packages. For example, the `essential buildings` will install, `wget` and `curl` for web requests, `Python` versions for `-dev`elopers, some `libs`, the `Git` version controller. \
      Whether you already have any of these items, in the output log you'll see which items have yet been satisfied or you'll have the newest version had been updated. \
   * Do you recall the above package `curl`? Thanks to the third-party packages list, the lib pyenv could be installed. \
     `curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash`
   * Some environment variables configurations for you to append to file `~/.bashrc` 
     `nano ~/.bashrc`  --nano, gedit, vim, emacs, or even you can take your IDE as editor, just navigate to file through its path. So, edit the file and save changes --look at the footer instructions.
      Once some file starts with a dot, like `.bashrc`, it means it's a `hidden file` which keeps the environment variables safe. To have access to hidden files you will need the command `ls -a` (-a stands to -all).
   * Scroll until the end of the `.bashrc` file and paste these following lines.
      ```
      export PYTHON_BUILD_ARIA2_OPTS="-x 10 -k 1M"
      export PATH="~/.pyenv/bin:$PATH"
      eval "$(pyenv init --path)"
      eval "$(pyenv init -)"
      eval "$(pyenv virtualenv-init -)"
      ```
     you might just read, run `cat ~/.bashrc` or `cat ~/.bashrc >> ~/Desktop/bashrc-file.txt` to take the readable file a snapshot `>>`
   - Run `source ~/.bashrc` for parsing to your terminal the proof of work execution for the newest exports over the environment variables file.
Now, test the commands `pyenv --version`  `which pyenv`  `echo $PATH` are commands you have to try. Restart the terminal if you need.
Once you have the expected output acceptions fully running for you, --you made it! --have a drink, you deserve a break.
4. `pyenv update` --once a while 
5. `pyenv install -l ` --for accessing the list of available systems to install
6. `pyenv install 3.9.7` --asking to install the latest Python version, according to the above list
7. `pyenv versions` --lists what systems are available to checkout/switch between versions
   ```
   * system (set by /home/johndoe/.pyenv/version)
     3.9.7
   ```
8. `pyenv global 3.9.7` --to checkout/switch between versions
   ```
   system (set by /home/johndoe/.pyenv/version)
   * 3.9.7
   ```
9. Case if you want back to the Python of the system, just run `pyenv global system`, but you won't want to do that, you will?

### Finally, Pipenv. The subject of this issue
Open your terminal `ctrl + alt + t`. \
Actually there are several ways to do that, but we won't want further ado to ourselves. \
So, once within the terminal, and no matter where you are, type: \
1- `mkdir ~/Desktop/pipenv-project && cd ~Desktop/pipenv-project` \
2- `pip install pipenv` or `sudo apt install pipenv` \
3- `pipenv install`  -- this creates the initial configuration \
4- Kind of different ways for you to ensure that installation: \
* `python3 --version`  --in that case 3.9.7
* `pipenv --version`
* `which pipenv`
* `which python3 --version`
* `find / -name pipenv -type f`
* `pip uninstall pipenv`  --in that case you won't want to proceed to do that, so answer `n` for not accepting the uninstalling. \
5- `pipenv shell`  --to run the pipenv virtual environment. Just to recall, if it was in pip command: `source .venv/bin/activate` \
6- `pipenv graph`  -- \
7- Have an overall look at the following context:
```
(pipenv_project) johndoe@ubuntu21-vbox:~/Desktop/pipenv_project$ pipenv
Usage: pipenv [OPTIONS] COMMAND [ARGS]...

Options:
  --where                         Output project home information.
  --venv                          Output virtualenv information.
  --py                            Output Python interpreter information.
  --envs                          Output Environment Variable options.
  --rm                            Remove the virtualenv.
  --bare                          Minimal output.
  --completion                    Output completion (to be executed by the
                                  shell).

  --man                           Display manpage.
  --support                       Output diagnostic information for use in
                                  GitHub issues.

  --site-packages / --no-site-packages
                                  Enable site-packages for the virtualenv.
                                  [env var: PIPENV_SITE_PACKAGES]

  --python TEXT                   Specify which version of Python virtualenv
                                  should use.

  --three / --two                 Use Python 3/2 when creating virtualenv.
  --clear                         Clears caches (pipenv, pip, and pip-tools).
                                  [env var: PIPENV_CLEAR]

  -v, --verbose                   Verbose mode.
  --pypi-mirror TEXT              Specify a PyPI mirror.
  --version                       Show the version and exit.
  -h, --help                      Show this message and exit.


Usage Examples:
   Create a new project using Python 3.7, specifically:
   $ pipenv --python 3.7

   Remove project virtualenv (inferred from current directory):
   $ pipenv --rm

   Install all dependencies for a project (including dev):
   $ pipenv install --dev

   Create a lockfile containing pre-releases:
   $ pipenv lock --pre

   Show a graph of your installed dependencies:
   $ pipenv graph

   Check your installed dependencies for security vulnerabilities:
   $ pipenv check

   Install a local setup.py into your virtual environment/Pipfile:
   $ pipenv install -e .

   Use a lower-level pip command:
   $ pipenv run pip freeze

Commands:
  check      Checks for PyUp Safety security vulnerabilities and against PEP
             508 markers provided in Pipfile.

  clean      Uninstalls all packages not specified in Pipfile.lock.
  graph      Displays currently-installed dependency graph information.
  install    Installs provided packages and adds them to Pipfile, or (if no
             packages are given), installs all packages from Pipfile.

  lock       Generates Pipfile.lock.
  open       View a given module in your editor.
  run        Spawns a command installed into the virtualenv.
  scripts    Lists scripts in current environment config.
  shell      Spawns a shell within the virtualenv.
  sync       Installs all packages specified in Pipfile.lock.
  uninstall  Uninstalls a provided package and removes it from Pipfile.
  update     Runs lock, then sync.
