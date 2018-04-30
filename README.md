# ypsilon
Automated Use Case Testing

# What is Ypsilon
Ypsilon is an Automated Security Use Case Testing Environment using real malware to test SIEM use cases in an closed environment. Different tools such as Ansible, Cuckoo, VirtualBox, Splunk and ELK are combined to determine the quality of a SIEM use case by testing any number of malware against a SIEM use case. Finally, a test report is generated giving insight to the quality of an use case.

![Ypsilon Architecture](https://github.com/P4T12ICK/ypsilon/blob/readme_changes/images/ypsilon_architecture.png)

Cuckoo in combination with VirtualBox is used to analyze the malware and test the use cases. The Cuckoo environment consists of analysis virtual machine, which will be infected by malware, and a SIEM virtual machine, which collects the logs and triggers the use cases. In the moment, only Splunk is supported as SIEM solution but supporting further SIEMs such as ELK is planned. 
Sigma is used as the generic description language for SIEM solutions. Ansible is the heart of the Ypsilon project. Ansible controls  the use case testing process consisting of the following steps:
- Generating a Splunk or ELK (planned) Use Case from the generic Sigma description language by using a Sigma converter.
- Preparing VirtualBox and Cuckoo
- Submitting a malware to Cuckoo
- Trigger the Use Case
- Revert the virtual machines to a snapshot
- Generate a report (in development)

Ypsilon is for Use Case development what Jenkins is for software development.


# Ypsilon Project
The Ypsilon project repository consists of the Ansible playbook, which controls the automated use case testing. Furthermore, the tools needs to be configured as described in the wiki, in order to be able to control the tools.

## Configuration 
The configuration of the tools is described in the wiki.  

## Installation
The following tools need to be installed and configured:
- Ansible
- VirtualBox
- Cuckoo
- Sigma
- Splunk
- TexLive

More information about installation and configuration of these tools can be found in the wiki.


## How to Use
The Ypsilon project consists of an Ansible playbook, which is executed by the following command:
```shell
test
```

# Credits
This is a private project completely developed by Patrick Bareiss with feedback by colleagues and friends.

# License
The content of this repository is released under the GNU General Public License.

