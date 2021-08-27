# Learning Links
* [Ansible Full Course | Ansible Tutorial For Beginners | Learn Ansible Step By Step | Simplilearn](https://www.youtube.com/watch?v=EcnqJbxBcM0)
* [Ansible Course in Udemy](https://www.udemy.com/course/learn-ansible/)
* [Ansible Docs](https://docs.ansible.com/)

## To check syntax of YAML files
[yamllint - check yaml files syntax](http://www.yamllint.com/)


## Ansible Modules
[Introduction to modules](https://docs.ansible.com/ansible/latest/user_guide/modules_intro.html)

Modules (also referred to as “task plugins” or “library plugins”) are discrete units of code that can be used from the command line or in a playbook task. Ansible executes each module, usually on the remote target node, and collects return values.
```
$ ansible-doc script
$ ansible-doc -l
$ ansible-doc -l | grep script
```

## Ansible Patterns
When you execute Ansible through an ad-hoc command or by running a playbook, you must choose which managed nodes or groups you want to execute against. Patterns let you run commands and playbooks against specific hosts and/or groups in your inventory. An Ansible pattern can refer to a single host, an IP address, an inventory group, a set of groups, or all hosts in your inventory. Patterns are highly flexible - you can exclude or require subsets of hosts, use wildcards or regular expressions, and more. Ansible executes on all inventory hosts included in the pattern.

[intro_patterns](https://docs.ansible.com/ansible/latest/user_guide/intro_patterns.html)

## Ansible Galaxy
Jump-start your automation project with great content from the Ansible community. Galaxy provides pre-packaged units of work known to Ansible as roles.

[Ansible Galaxy](https://galaxy.ansible.com/)
