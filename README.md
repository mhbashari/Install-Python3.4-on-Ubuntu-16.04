# Install Python3.4 on Ubuntu-16.04
The last version of python is bundled with ubuntu 16.04. But at this time there are some famous packages incompatible with version 3.5. There is no guaranty but By Following this instruction you almost certainly  can build and use the python version 3.4 on ubuntu16.04.Before start I give my thanks to [tecadmin.net](http://bit.ly/py34biu1604) for its great step by step guide, but I do some edition on it. So let to do:

## Install Required Packages
* Install some packages from launchpad:
    * `$ sudo apt-get install build-essential checkinstall`
    * `$ sudo apt-get install libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev`
    * `$ sudo apt-get install libssl-dev openssl`
    * `$ sudo apt install lzma lzma-dev liblzma-dev` Python 3.4.5 - according to @ilya-khaustov [Contribution](https://github.com/mhbashari/Install-Python3.4-on-Ubuntu-16.04/issues/1)
    
## Download and extract Python Source Code
* download https://www.python.org/ftp/python/3.4.4/Python-3.4.4.tar.xz:
    * `$ wget https://www.python.org/ftp/python/3.4.4/Python-3.4.4.tgz`
* extract it by:
    * `$ sudo tar xzf Python-3.4.4.tgz`
    
## Compile
Pay attention to **altinstall** :
* `$ cd Python-3.4.4`
* `$ sudo sudo ./configure --prefix=/opt/python3.4 --with-zlib-dir=/usr/local/lib/ --with-ensurepip=install`
* `$ sudo make altinstall`
    
With using the **altinstall** switch you are sure that the previous installed version(s) of python is not affected or damaged.

## Check the Python Version (Installation test)
* `$ python3.4 -V`

If all is done correctly you see `Python 3.4.4`. But if you don't, the next steps should be helpful.


## Make shortcut from Python executable binary
If you done this instruction without any changes your 3.4 executable binary has been placed in `/opt/python3.4` in `nautilus` right click on **python3.4** executable and select **make link**. The new shortcut created. Copy this shortcut to `/usr/bin` and go to previous step

## Make pip3.4 globally accessible
If don't access to the pip3.4 do this:

* in `/usr/bin` directory find `pip3` file
* duplicate and name `pip3.4`, on the first line you see `#!/usr/bin/python3`
* change to `#!/usr/bin/python3.4` and save. (if you want to skip the previous step use `/opt/python3.4` instead)

Any issue ?
