---
layout: page
title: "Setup"
permalink: /setup/
root: ..
---

# Installation Instructions



## Check to see if Conda is already installed

If you have ever installed the [Anaconda Python distribution](https://www.anaconda.com/distribution/)
on your local machine, then you already have Conda installed! Mac and Linux users can check
whether Conda is installed by running the following command in a terminal.

~~~
$ which conda
/Users/$USERNAME/miniconda3/bin/conda
~~~
{: .language-bash}

If Conda has already been installed on your machine, then this command should return the
absolute path to the conda executable.

Windows users should search for "Anaconda" to see if the "Anaconda Command Prompt" shows up as an
option, if it does then you already have Conda installed.

> ## Old version of Anaconda?
>
> If you previously installed the Anaconda Python distribution you may have an old version of Conda. You
> can check your version of Conda with the following command.
>
> ~~~
> $ conda --version
> ~~~
> {: .language-bash}
>
> If you have a version of Conda that is 4.5 (or older), then it is probably best to
[uninstall](https://docs.anaconda.com/anaconda/install/uninstall/) your Anaconda Python distribution
> and then reinstall the most recent version.
{: .callout}

## Install Python 3 version of Miniconda

If Conda has not been installed on your machine, then install the Python 3 version of
[Miniconda](https://docs.conda.io/en/latest/miniconda.html) for your OS. As the name
suggests, Miniconda is a "mini" version of the
[Anaconda Python distribution](https://www.anaconda.com/distribution/) that includes only Conda, a
Python 3 distribution, and any necessary OS-specific dependencies.

For convenience here are links to the 64-bit Miniconda installers.

* [Windows](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe)
* [Mac OSX](https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.pkg)
* [Linux](https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh)

> ## Prefer Miniconda to Anaconda
>
> We suggest installing Miniconda which combines Conda with Python 3 (and a small number of core
> systems packages) instead of the full Anaconda distribution. Installing only Miniconda will
> encourage you to create separate environments for each project (and to install only those packages
> that you actually need for each project!). Project specific environments enhance portability and
> reproducibility of your research and workflows.
>
> Besides, if you *really* want the full Anaconda distribution you can always create an new conda
> environment and install it using the following command.
>
> ~~~
> $ conda create --name my-anaconda-env anaconda=5.3
> ~~~
> {: .language-bash}
>
> We will discuss the above command in great depth in the workshop.
{: .callout}

> ## Verify downloaded executables
> 
> You should verify the files that you download by comparing their SHA-256
> hash to the expected value. The Conda website provides instructions for
> [cryptographic hash verification](https://conda.io/projects/conda/en/stable/user-guide/install/download.html#cryptographic-hash-verification) on all platforms, where
> [hashes](https://docs.conda.io/en/latest/miniconda.html) are published.
{: .callout}

### Windows installation

After you downloaded the [Windows GUI
installer](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe), double click on it and follow the
instructions (accept license, etc.).
You can use the defaults except for the "Advanced Installation Options" where you would tick on **"Add Miniconda3 to my
PATH environment variable"**.

### Mac OSX installation
After you downloaded the [Mac OSX GUI
installer](https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.pkg), double click on it and follow the
instructions (accept license, etc.).

When you are asked where to install Miniconda, you should leave the default option to "_Install for me only_". If you get
the error message “_You cannot install Miniconda in this location_” then reselect "_Install for me only_". Then you
should be able to continue to the next prompt.

The default options will modify your `$PATH` in `~/.bashrc`.

You will need to either `source ~/.bashrc` in your current shell or start a new shell/terminal for the changes to take
effect. Once correctly installed and activated your command promt should begin with `(base)`.

### Linux installation

We will walk through the steps for installing on Linux systems below as installing on Linux systems is slightly more
involved. First, download the 64-bit Python 3 install script for Miniconda (clicking the link above will download the
same script!).

~~~
wget --quiet https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
~~~
{: .language-bash}

Run the Miniconda install script. Follow the prompts on the installer screens. If you are unsure
about any setting, accept the defaults (you can change them later if necessary). The default options will modify your
`$PATH` in `~/.bashrc`.

~~~
bash Miniconda3-latest-Linux-x86_64.sh
~~~
{: .language-bash}

Once the install script completes, you can remove it.

~~~
rm Miniconda3-latest-Linux-x86_64.sh
~~~
{: .language-bash}

You will need to either `source ~/.bashrc` in your current shell or start a new shell/terminal for the changes to take
effect. Once correctly installed and activated your command promt should begin with `(base)`.

## Verifying your Conda installation

> On **Windows** you'll need to go to the "start" menu (or whatever it's called now) and open up the **Anaconda
> Powershell Prompt** before following the next instructions.

In order to verify that you have installed Conda correctly run the `conda --help` command. Output of the command should
look similar to the following.

~~~
$ conda --help
usage: conda [-h] [-V] command ...

conda is a tool for managing and deploying applications, environments and packages.

Options:

positional arguments:
  command
    clean        Remove unused packages and caches.
    config       Modify configuration values in .condarc. This is modeled
                 after the git config command. Writes to the user .condarc
                 file (/Users/drpugh/.condarc) by default.
    create       Create a new conda environment from a list of specified
                 packages.
    help         Displays a list of available conda commands and their help
                 strings.
    info         Display information about current conda install.
    init         Initialize conda for shell interaction. [Experimental]
    install      Installs a list of packages into a specified conda
                 environment.
    list         List linked packages in a conda environment.
    package      Low-level conda package utility. (EXPERIMENTAL)
    remove       Remove a list of packages from a specified conda environment.
    uninstall    Alias for conda remove.
    run          Run an executable in a conda environment. [Experimental]
    search       Search for packages and display associated information. The
                 input is a MatchSpec, a query language for conda packages.
                 See examples below.
    update       Updates conda packages to the latest compatible version.
    upgrade      Alias for conda update.

optional arguments:
  -h, --help     Show this help message and exit.
  -V, --version  Show the conda version number and exit.

conda commands available from other packages:
  env
~~~
{: .language-bash}

At the bottom of the help menu you will see a section with some optional arguments for the
`conda` command. In particular you can pass the `--version` flag which will return the version
number. Again output should look similar to the following.

~~~
$ conda --version
conda 23.1.0
~~~
{: .language-bash}

## Make sure you have the most recent version

Once Conda exists on your machine, you can update it at any time by running the following command to make sure that you
have the most recent version and patches.

~~~
$ conda update --name base --channel defaults --yes conda
~~~
{: .language-bash}


## Initializing your shell for Conda

Key parts of Conda's functionality require that it interact directly with the shell within which Conda commands are
being invoked as such each shell must be configured to make use of them. The `conda init` command initializes a shell
for use with Conda by making changes to your system that are specific and customized for each shell. Conda supports a
number of different shells and you can run `conda init --help` to see the complete list.


Mac OSX and Linux users may have already been prompted to initialize Conda for your shell when running the installation
script. If so, then you can safely skip this step.

The following initialises the Bash shell.

~~~
$ conda init bash
~~~
{: .language-bash}

Windows users should use the Anaconda Powershell Prompt which is already initialized for Conda or they can initialize
Conda for Powershell as follows.

~~~
> conda init powershell
~~~

After running `conda init` you will need to close and restart your shell for changes to take
effect. Alternatively, MacOS and Linux users can reload your `~/.bashrc` profile (which was
changed by running the `conda init` command) by running the following command.

~~~
$ source ~/.bashrc
~~~
{: .language-bash}

If you want to reverse or “undo” the changes made by `conda init`, then you can re-run the `conda init` command and pass
the `--reverse` option. Again, in order for the reversal to take effect you will likely need to close and restart your
shell session or `source ~/.bashrc`.
