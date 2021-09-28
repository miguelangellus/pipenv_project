# pipenv_project
Getting Started With Pipenv

Basic commands
Pipenv is a huge replacement as both to the pyenv as pip --the Package Installer for Python, together.
Developed by the lib request's same team, the Pipenv owns powerful features and tools that allow you to make work much easier when integrating these resources. 
I'll bring for you some of the pipenv basic commands, and some analogies for a better comprehension to you.
Despite different features, even so, it's still necessary for the Pyenv to proceed to the isolation of the Python version and environment, instead of using the standard Python from your operational system, also Pip for accessing and installing the indexes from the pypi.org site.
1. pip --version
2. pip install --update pip
3. pip install pyenv????? Definitely no, would be, but it's not so simple as it seems.
   Follow these steps below to catch this Python versions controller for running under your device.
   1. sudo apt update
   2. sudo apt install -y build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm gettext libncurses5-dev tk-dev tcl-    dev blt-dev libgdbm-dev git python-dev python3-dev aria2
      Don't feel scared of that, Sudo asks you for your superuser password for being typed; apt is the Linux repository; install is the action; -y is the               parameter that defines yes for all installing packages. For example, an essential build, Wget and curl for web requests, Python versions for developers,           some libs, the Git version controller. Whether you already have any of these items, in the output log you'll see which items have yet been satisfied or will       have the newest version had been updated.
   3. curl -L https://raw.githubusercontent.com/pyenv/pyenv-installer/master/bin/pyenv-installer | bash
   4. nano ~/.bashrc   --nano, gedit, vim, emacs, or even you can take your IDE as editor, just navigate to file through its path. So, edite and save changes.
      Once starts with dot, .bashrc is a held file that keep your environment variables with security, to access held files you will need the comand ls -a (-a stands to all).
   5. export PYTHON_BUILD_ARIA2_OPTS="-x 10 -k 1M"
      export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init --path)"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
5. pyenv --version
6. pyenv install -l (for accesing the list of availables systems to install)
7. pyenv install 3.9.7 (asking to install the latest Python version, according to the list)
8. pyenv versions (lists what systems are available to checkout/switch between versions) 
  * system (set by /home/johndoe/.pyenv/version)
    3.9.7
9. pyenv global 3.9.7
    system (set by /home/johndoe/.pyenv/version)
  * 3.9.7
9. If you want back to the Python of the system, just $ pyenv global system, but you won't want to do that, you will?
10. 
open your terminal, no matter where you are
1- $ mkdir ~/Desktop/pipenv-project && cd ~Desktop/pipenv-project
2- $ pip install pipenv or sudo apt install pipenv
2- $ pipenv install
4- Kind of different ways for you to ensure that installation:
* pipenv --version
* which pipenv
* find / -name pipenv -type f
* pip uninstall pipenv --in this case won't want to proceed to do that, so answer n for not accepting the uninstalling. 
3- pipenv shell
3- pipenv graph
5- pipenv deph
(pipenv_project) miguelangellus@ubuntu21-vbox:~/Desktop/pipenv_project$ pipenv
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
