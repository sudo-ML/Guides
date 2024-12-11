## ODAT on Arch

            _  __   _  ___ 
           / \|  \ / \|_ _|
          ( o ) o ) o || | 
           \_/|__/|_n_||_| 


ODAT (Oracle Database Attacking Tool) is not included in the Blackarch Repo so if we want to use it on Arch we need to install it in a bit more of a manual fashion.

First create a Python/Virtual environment using the instructions here. https://wiki.archlinux.org/title/Python/Virtual_environment
And make sure you are inside your python virtual environment.

Now run the following:

```
git clone https://github.com/quentinhardy/odat.git
cd odat/
git submodule init
git submodule update
wget https://download.oracle.com/otn_software/linux/instantclient/2112000/instantclient-basic-linux.x64-21.12.0.0.0dbru.zip
unzip instantclient-basic-linux.x64-21.12.0.0.0dbru.zip
wget https://download.oracle.com/otn_software/linux/instantclient/2112000/instantclient-sqlplus-linux.x64-21.12.0.0.0dbru.zip
unzip instantclient-sqlplus-linux.x64-21.12.0.0.0dbru.zip
export LD_LIBRARY_PATH=instantclient_21_12:$LD_LIBRARY_PATH
export PATH=$LD_LIBRARY_PATH:$PATH
pip install cx_Oracle
pip install scapy
pip install install colorlog termcolor passlib python-libnmap
pip install install pycryptodome
pip install pyasyncore 
```

To test that installation was succesful, make sure you are inside your virtual environment AND the folder that contains odat.py and run:

`python3 odat.py -h`



