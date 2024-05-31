
### Installing Tamarin on your machine

 Please install and use the latest release version 1.8.0. of the Tamarin prover for this lab.
 Instructions to install and use Tamarin can be found in the [Installation section](https://tamarin-prover.com/manual/master/book/002_installation.html) of the Tamarin manual.



#### Code editors that support Tamarin syntax

* If you want to use syntax highlighting, we suggest using [Visual Studio Code](https://code.visualstudio.com) with [this extension](https://marketplace.visualstudio.com/items?itemName=gilcu3.tamarin) (search for extension with ID gilcu3.tamarin).

* There is also syntax highlighting for [Sublime Text 3](https://github.com/tamarin-prover/editor-sublime) available. You can install syntax highlighting using "Package Control."

* Some more options are described in the [installation section](https://tamarin-prover.com/manual/master/book/002_installation.html) of the Tamarin manual.

#### Remarks and common issues

* If you use Windows as your main operating system, you will need to either use a VM or install Tamarin via the [Linux for Windows Subsystem](https://docs.microsoft.com/en-us/windows/wsl/install). Some common issues with installing Tamarin on WSL are listed below.
* If you compile Tamarin directly or use Homebrew, be sure to check the resulting binary is on your system $PATH.
* We tested the installation using Homebrew on Apple’s M1 chips but not on M2.
* Installing Tamarin with Homebrew might result in some “Too many open files” error. Try
to re-run the installation with brew.
* Tamarin only runs on WSL2. Check your version with wsl -l -v. You can change the version to WSL2 with wsl --set-version <distro name> 2.
* If you manually install the Haskell Stack, you could encounter problems regarding zlib. In that case, install libghc-zlib-dev with your package manager.
* If you manually install Maude, make sure that you install Maude 2.7.1. Installing Maude with your package manager might result in an earlier version. Also, Tamarin does not support newer versions, such as 3.2.
* After manually installing maude, check that it works by calling maude.linux64. Install missing packages with your package manager.
* Make sure to add Maude to your path.

#### Checking that Tamarin is working correctly
Once you have installed the tool, download the file `sig.spthy` from Github. 

Run `tamarin-prover --prove sig.spthy` in the repository where you stored the file and you should get the outcome:

```
summary of summaries:
analyzed: sig.spthy
executable (exists-trace): verified (6 steps) signature_sent_by_agent (all-traces): verified (5 steps)
```