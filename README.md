ZeroStack preflight system check
================================

The ZeroStack pre-flight system check can be used by an administrator or ZeroStack SE to determine if the hardware in question is compatible with the ZeroStack cloud operating system.


The preflight check will ensure that your physical server will work with the Zerostack ZCOS. Once this script is run, and
all of the checks are varified, you will be able to install the ZCOS.


The preflight check will make sure the hardware adhears to the Zerostack minimal viable hardware spec.


1. Overall system configuration
2. CPU architecture
3. Storage requierments
4. Networking


Please check the Ubuntu HCL to verify your results.
[Ubuntu Server HCL](https://certification.ubuntu.com/server/)


Once all of the results have been verified, please send them to your SE.

Getting Started
---------------

In order to get the preflight check working, you will need to make sure python 2.7 or 3.x is installed on the system the preflight check will run on.


PIP will also be requierd in order to install zs-preflight and the supporting packages.


**OS Requierments**

CentOS 7

$ yum install -y epel-release,python-pip,hdparm

Ubuntu 14.04 / 16.04 / 18.04

$ apt install -y python-pip


**Pre-flight Prerequisites**

In order to get the zspreflight system working you will need to install the following packages on the sytstem you are running the preflight check from.

PIP will install all of the packages needed to run the ZS-Preflight system, if they are not present.

$ pip install paramiko


$ pip install gspread


$ pip install oauth2client


**Installing**

To install the preflight check on the system, follow these steps. Make sure all of the pre-requisite packages have been installed.


$ pip install zs-preflight


**Running the tests**

Run the pre-flight check with the following command.


$ preflight


Build and submit
----------------


**GIT - development / nightly**


1. git clone https://github.com/Zerostack-open/zs-preflight.git
2. cd zspreflight
3. python setup.py bdist_wheel


**PIP - Development**


1. sudo python -m pip install --upgrade pip setuptools wheel
2. sudo python -m pip install tqdm
3. sudo python -m pip install --user --upgrade twine


**TODO**


1. Upload data to Gsheet
2. Fire off preflight from zspreflight on a remote system


Authors
-------


**Jonathan Arrance** - *Initial work* - [Zerostack-open](https://github.com/Zerostack-open)


See also the list of [contributors](https://github.com/JonathanArrance) who participated in this project.


License
-------


This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/Zerostack-open/zs-preflight/blob/master/LICENSE) file for details