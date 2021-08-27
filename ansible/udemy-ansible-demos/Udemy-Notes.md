# Commands
```
$ mkdir test-proj
$ pwd
  /home/osboxes/test-project
$ cat > inventory.txt
target1 ansible_host=192.168.1.19 ansible_ssh_pass=osboxes.org
ctrl +

$ssh 192.168.1.19
$ ansible target1 -m ping -i inventory.txt

$ vi inventory.txt
  target1 ansible_host=192.168.1.19 ansible_ssh_pass=osboxes.org
  target2 ansible_host=192.168.1.20 ansible_ssh_pass=osboxes.org
$ ansible target2 -m ping -i inventory.txt
$ cd /etc/ansible/ansible.cfg
  search for "host_key" and uncomment it
$ ansible target2 -m ping -i inventory.txt
```

```
$ cd test-project
$ cat inventory.txt
  target1 ansible_host=192.168.1.19 ansible_ssh_pass=osboxes.org
  target2 ansible_host=192.168.1.20 ansible_ssh_pass=osboxes.org
$ ansible all -m ping -i inventory.txt
    Note: By default, ansible creates a group called "all", which contains all the hosts(servers) defined in our inventory file
```
