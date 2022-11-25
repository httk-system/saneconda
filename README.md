# saneconda

A saner handling of Anaconda environments with the conda command.

## Setup

1. Install Anaconda without doing 'conda init' or adding anything to your `.bashrc` or `.bash_profile`.
2. Edit your `.bashrc` to contain the following:
   ```  
     export ANACONDA_PATH=/opt/anaconda3
     function conda() { source ~/Scripts/conda.source "$@" }
   ```
   where you replace `/opt/anaconda3` with the path where you have installed Anaconda, and 
   `~/Scripts/conda.source` with the path to the `conda.source` script in this repository.

 3. Open a new terminal window or log out and log in again.

After this, you can use the `conda` command more or less as usual. However, your Anaconda installation does not
affect anything in your system before you do a `conda activate <environment>` (or just `conda activate` to activate the bundled "base" conda environment for the version of Anaconda you installed). Hence, before that, your Python version remains
your system Python, no Anaconda python libraries are intermixed with your system python libraries etc. After issuing `conda activate <environment>`,
you have access to your conda environment as usual. When you do `conda deactive`, you return to an environment that is not affected by your Anaconda installation.
