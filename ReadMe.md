# 20210713 TechFieldDay - Future Cloud - Cisco Identity Services Engine (ISE) in AWS with Ansible Automation

ISE 3.1 will be available as a native Amazon Machine Image (AMI) and customers want to use automation tools to provision their deployments whether on-premises, using cloud providers, or hybrid. This session will demonstrate how you can use the new **[`cisco.ise`](https://ciscoise.github.io/ansible-ise/main/html/plugins/index.html)** Ansible modules to generate configurations from existing deployments and begin to incorporate them into their daily policy management and lifecycle orchestration.

## Presentation and Demos

[![Cisco Identity Services Engine (ISE) in AWS with Ansible Automation](https://img.youtube.com/vi/H1TQnNT2Rkk/0.jpg)](https://www.youtube.com/watch?v=H1TQnNT2Rkk "Cisco Identity Services Engine (ISE) in AWS with Ansible Automation")

Watch the TechFieldDay presentation and demo from the recording in YouTube.

## Quick Start

If you want to play with the `cisco.ise` Ansible collection, this is a summary of the commands you will need to run to get started.

```bash
# Use a virtual environment to prevent conflicts with other projects
pip install --upgrade pip
pip install pipenv
pipenv install --python 3.9
pipenv shell

# Install Python packages
python -m pip install ansible
python -m pip install ciscoisesdk
python -m pip install jmespath  # required for community.general JSON queries


# Install Ansible collections
ansible-galaxy collection install cisco.ise
ansible-galaxy collection install community.general

# set a nice prompt and some environment variables to eliminate warnings
source source_me.sh
```

If you have any problems installing Python or Ansible, see **[](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)**


Clone this repository to your local lab or sandbox environment :  

```bash
git clone https://github.com/1homas/20210713_ISE_TechFieldDay.git

cd 20210713_ISE_TechFieldDay
```



## Deploy

The steps below assume you will be cloning this repository into the DevNet Sandbox and running it there. If you use them in your own lab then you will need to create a different `hosts` file and update the `credentials.yaml` file for your environment.

```bash
ansible-playbook -i hosts.dCloud.ini Deploy/Deploy_ISE_Tasks.yaml 

ansible-playbook -i hosts.DevNet.ini Deploy/Deploy_ISE_Tasks.yaml 

ansible-playbook -i hosts.AWS.ini Deploy/Deploy_ISE_Tasks.yaml
```



## Resources

- [`ciscoisesdk` Python Package](https://pypi.org/project/ciscoisesdk/) : [API Docs](https://ciscoisesdk.readthedocs.io/en/latest/api/api.html) | [Repository](https://github.com/CiscoISE/ciscoisesdk)
- [`cisco.ise` Ansible Modules](https://galaxy.ansible.com/cisco/ise) : [Documentation](https://ciscoise.github.io/ansible-ise/main/html/plugins/index.html) | [Repository](https://github.com/CiscoISE/ansible-ise)
- [Cisco DevNet Sandbox: ISE with Ansible Automation](https://devnetsandbox.cisco.com/RM/Diagram/Index/ad4bb2ae-bb67-4d93-9f0d-2a6a04792e2e?diagramType=Topology)
- [ISE APIs, Ansible, and Automation DevNet Learning Lab](https://developer.cisco.com/learning/modules/ise-automation)


## License

The examples in this repository are licensed under the [Cisco Sample Code License](https://developer.cisco.com/site/license/cisco-sample-code-license/).

