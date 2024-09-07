## Using git Inside PyCharm
PyCharm will automatically look for and use `git` if is already installed on your system. 
This short guide provides steps and references for installing and using `git` directly
from PyCharm. This can be a great productivity booster because we don't even have to leave
our IDE to commit code.  

### Basic Overview
1. install `git` for your platform. 
2. Launch (or re-launch) PyCharm. 
3. Reference [PyCharm documentation](https://www.jetbrains.com/help/pycharm/set-up-a-git-repository.html#clone-repo) for using `git` for help on common tasks.

### Installing `git` on Windows
1. Download the [correct package for your architecture](https://git-scm.com/download/win) (most likely 64-bit).  *If you 
happen to have an ARM architecture, get the 64-bit package*
2. Run the installer with mostly default options.  See recommended changes below

    3. Choose the editor carefully.  Choosing Notepad.exe is safe.
    4. Choose the option of override the default branch name to `main` instead of master. 
    This is current best-practice.
    5. PATH option: be sure to use "Recommended" as it allows 3rd party applications to 
    access git (required for PyCharm)
    6. All other options leave as-is.

### Installing `git` on macOS
The official `git` package requires that you install a package manager.  Homebrew is the best option these days, so the steps below include this.  You can also use MacPorts, but this is less widely used.  See the [official `git` site ](https://git-scm.com/download/mac)for confirmation of this approach.


!!! note 
    these instructions require use of the Terminal.  Use ⌘-Space to search and type "terminal" to open the terminal.**

1. Install [Homebrew](https://brew.sh) (You copy and paste a command into the terminal to install). *Note that this could take some time*.
2. In the terminal, type `brew install git`

!!! warning
    Installing Homebrew can take some time.  This is expected so don't close your 
    terminal until it completes. 

### Using git in PyCharm
- refer to [PyCharm's Documentation](https://www.jetbrains.com/help/pycharm/set-up-a-git-repository.html#clone-repo)
- Note that you may need to restart PyCharm to get it to recognize your new `git` installation.

!!! note
    Private repositories require that you authenticate in order to clone a repository.

### Authentication For GitHub Repos
Private GitHub repositories require that you authenticate with GitHub prior to cloning 
or pushing on a repository. 

JetBrains has put together a [guide on GitHub](https://www.jetbrains.
com/help/pycharm/github.html#register-existing-account). **Choose the "Log in via 
GitHub" option.**
