# Conda Cheat Sheet
Managing environments with Conda through the command line.

Creating an environment:
```
conda create --name <env_name> python=<version>
```

Activating an environment:
```
conda activate <env_name>
```

Installing Packages:
```
conda install <package_name>
```

Listing installed packages:
```
conda list
```

Exporting an environment:
```
conda env export > environment.yml
```

Importing an environment:
```
conda env create -f environment.yml
```