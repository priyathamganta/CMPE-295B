# Smart Security Function Orchestration for Intrusion detection


# Code files necessary : snort_test.py, deployment.py.

# Container image: dharmadheeraj/sdnnfv-latest


# NOTE: To add Openflow rules as response to alerts from Snort,  Ryu library must be changed, and Ryu should be built again. Do the following to achieve this.
a.	Install Ryu controller following the general instructions from https://ryu.readthedocs.io/en/latest/getting_started.html
b.	Copy and replace the provided snortlib.py file to the directory ryu/ryu/lib.
c.	To build the ryu application, run the command in the main ryu directory, “python setup.py install” or “python3 setup.py install” based on the python version used.

# Steps to run the code:
a.	Start running the controller by running the command “ryu-manager snort_test.py”.
b.	Start the orchestration service by running the command “python3 deployment.py”.
c.	Add two switches to the controller and check if the containers are deployed or not on both the switches.
d.	Ping between two nodes and verify the set of rules with which Snort started to validate the working of the model.
e.	Ping stops working after 1 packet. This confirms the packet flowing through Snort container and flow rules added to switches to drop alerts flagged by container.
