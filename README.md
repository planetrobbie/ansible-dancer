## Author:

  Sébastien Braun
  E-mail: sebbraun AT gmail.com

## License:

  This projected is licensed under the terms of the MIT license.

## Dependencies:

  This repository requires the following components:

  - Ansible 1.5+
  
## Usage:

First edit your Ansible Inventory which should be located in `/etc/ansible/hosts` to add sections for web and db hosts

  [web]
  192.168.100.10
  192.168.100.11

  [db]
	192.168.200.10

You can now run the dancer Playbook, from your admin node run: 

  # ansible-playbook dancer.yml

It's also possible to use Ansible Pull mode instead, to do so you just need to run the following command from each node :

  # ansible-pull -C head -d /home/nicira -U git://github.com/planetrobbie/ansible-dancer >> /var/log/ansible-pull.log 2>&

`-C` define which repository branch to pull  
`-d` directory to checkout git repository into.  
`-U` url of git repository to clone  

## Description:

When running the provided Ansible Playbooks, you should get a fully running 2-tier Web Application.

## Version History:

* 0.1 11-February-2015	First Commit
