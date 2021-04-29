ELKpi
=====

*note: This is a work-in-progress forked from surfuga/elkpi and using info from jogalt/elkpi fork for the password authentication.  I am working to install an ELK-stack on Raspberry Pi 4 in order to analyze my network logs.  Stretch-goal is to use docker to run in a container. 

This is an ansible playbook for installing an ELK stack on Raspberry pi 2, 3 or 4.
Please change the values in [vars-rpi.yml](vars/vars-rpi.yml) then launch with the following command: 
```ansible-playbook -i hosts elk-rpi.yml```

OR, if your Raspberry Pi requires password authentication, use:
```ansible-playbook -i hosts -v -b -c paramiko --ask-pass elk-rpi.yml```
NOTE: Depending on your version of Ansible, you may need to do an extra step to install `paramiko` connection plugin or modules that require `paramiko`.  [Ansible Reference](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-with-pip)

Prerequisites:
1. Python Installation
2. Ansible Installed
	2a. If needed, `paramiko` install.


Troubleshoot
----------

Kibana service is not always starting. I suggest you launch it with
```
cd /opt/kibana/bin
sudo ./kibana "-c /opt/kibana/config/kibana.yml
```

Issues are welcome.

Additional References:
------------
<https://ackcent.com/elk-on-a-raspberry-pi/>
[jogalt -Useful Fork - elkpi](https://github.com/jogalt/elkpi)
<https://gist.github.com/vjm/d206171be8971294f98b>
[Original Project - elkpi](https://github.com/surfuga/elkpi)
