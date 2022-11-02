# nbdev_tutorial

## Instalation using WSL

1. Install WSL (using windows store)
2. Install anaconda - follow steps in [this blog](https://emilykauffman.com/blog/install-anaconda-on-wsl)
3. create new conda env using `conda create --name env_name python=3.10`
4. Activate your new env using `conda activate [env name]`
5. install nbdev and few other packages 
    1. `conda install -c fastai nbdev`
    2. `conda install jupyter ipykernel pandas scikit-learn`
6. register your env with jupyter: `python -m ipykernel install --user --name=[your env name]`
7. install quarto:
    1. I've used [linux tarball](https://quarto.org/docs/download/)
    2. after selecting your download method you will get list of commands to run, in my case it was:
        1. `wget https://github.com/quarto-dev/quarto-cli/releases/download/v1.2.258/quarto-1.2.258-linux-amd64.tar.gz`
        2. `mkdir ~/opt`
        3. `tar -C ~/opt -xvzf quarto-1.2.258-linux-amd64.tar.gz`
        4. `mkdir ~/bin`
        5. `ln -s ~/opt/quarto-1.2.258/bin/quarto ~/bin/quarto`
        6. `( echo ""; echo 'export PATH=$PATH:~/bin\n' ; echo "" ) >> ~/.bashrc`
        7. `source ~/.bashrc`
        8. `quarto check` - you should get all ok (except R) and it should report your conda repo version of python
8. create github repo and clone it to folder where you want to keep your project files - `git clone [repo url]`
9. navigate to your project dir and run `nbdev_new`